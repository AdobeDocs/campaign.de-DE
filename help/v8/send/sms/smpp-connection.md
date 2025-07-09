---
title: Validieren einer SMPP-Verbindung
description: Erfahren Sie, wie Sie eine SMPP-Verbindung validieren
feature: SMS
role: User
level: Intermediate
exl-id: eda6934a-e48a-4932-8c88-588f661005d6
source-git-commit: 6f29a7f157c167cae6d304f5d972e2e958a56ec8
workflow-type: tm+mt
source-wordcount: '4443'
ht-degree: 100%

---

# Validieren einer SMPP-Verbindung {#validate-smpp-connection}

Im Folgenden finden Sie einige Möglichkeiten, um zu überprüfen, ob Ihre SMPP-Verbindung in Ordnung ist.

## Vor der Live-Schaltung zu überprüfende Punkte {#check-go-live}

Stellen Sie anhand der folgenden Prüfpunkte vor der Live-Schaltung sicher, dass Ihr SMPP-Setup in Ordnung ist.

>[!IMPORTANT]
>
>Diese Checkliste ist nicht vollständig. Je mehr Punkte Sie überprüfen, desto besser.

>[!NOTE]
>
>Aktivieren Sie ausführliche SMPP-Protokolle während der Prüfungen. Dies hilft Ihnen und dem Support, die Fehlerbehebungen zu verstehen.

### Prüfen auf Konflikte mit externen Konten {#sms-external-accounts-check}

Vergewissern Sie sich, dass Sie keine übrig gebliebenen externen SMS-Konten haben. Löschen Sie die Testkonten, um potenzielle Konflikte zu vermeiden.

Vergewissern Sie sich, dass keine andere Instanz eine Verbindung zu dem externen Konto herstellt. Achten Sie insbesondere darauf, dass die Preprod-Umgebung keine Verbindung zum externen Konto herstellt.

Wenn Sie mehrere Konten in derselben Campaign-Instanz haben müssen, die eine Verbindung zu demselben Provider herstellen, wenden Sie sich an den Provider, um sicherzustellen, dass tatsächlich zwischen den Verbindungen dieser Konten unterschieden wird. Für mehrere Konten mit denselben Anmeldedaten ist eine zusätzliche Konfiguration erforderlich.

Vergewissern Sie sich, dass für alle aktivierten externen SMS-Konten die dedizierte Prozesseinstellung aktiviert ist. Sie können nicht beide Arten von Konten (mit und ohne dedizierten Prozess) auf derselben Instanz verwenden.

### Führen Sie einen realen Test durch {#real-test}

Versuchen Sie, einige SMS an verschiedene Mobiltelefone zu senden.

**Senden von SMS mit allen möglichen Zeichen**

Wenn Sie eine SMS mit Nicht-GSM- oder Nicht-ASCII-Zeichen senden müssen, versuchen Sie, einige Nachrichten mit möglichst vielen verschiedenen Zeichen zu senden. Wenn Sie eine benutzerdefinierte Zeichen-Mapping-Tabelle einrichten, senden Sie mindestens eine SMS für alle möglichen data_coding-Werte.

**Überprüfen, ob SR ordnungsgemäß verarbeitet werden**

Die SMS sollte im Versandlog als empfangen gekennzeichnet werden. Das Versandlog sollte erfolgreich sein und wie folgt aussehen: „*SR yourProvider stat=DELIVRD err=000|#MESSAGE#*“.

Vergewissern Sie sich, dass Sie das Feld „*Name der SMSC-Implementierung*“ richtig festgelegt haben: Das Versandlog darf in Produktionsumgebungen niemals „*SR Generic*“ enthalten.

**Überprüfen, ob MO verarbeitet werden**

Senden Sie ein paar SMS für alle automatischen Antwort-Keywords und prüfen Sie, ob die Antwort schnell erfolgt (nicht länger als ein paar Sekunden).

Vergewissern Sie sich, dass die MOs in die Datenbank *nms:inSms* eingefügt wurden. Wenn Sie über benutzerdefinierte TLVs verfügen, stellen Sie sicher, dass diese ebenfalls korrekt eingefügt und ordnungsgemäß formatiert sind.

Prüfen Sie im Protokoll, ob Adobe Campaign mit einem erfolgreichen *DELIVER_SM_RESP (command_status=0)* antwortet.

**Durchführen eines Belastungstests**

Dies ist besonders wichtig, wenn Sie sehr viele Nachrichten senden oder Echtzeit-Messaging verwenden.

Führen Sie einen Test durch, bei dem die Verbindung mindestens 5 Sekunden lang zu 100 % ausgelastet wird. Sie müssen echte Nachrichten senden, wenn der Provider keine Möglichkeit hat, sich für Tests mit einem Fake-Konto zu verbinden. Eine Möglichkeit, dies zu erreichen, besteht in der genauen Überwachung des ersten ausreichend großen Versands mit aktivierten ausführlichen SMPP-Nachrichten.

Die Mindestanzahl an zu sendenden Nachrichten kann wie folgt berechnet werden:

*Max. MT-Durchsatz × Gesamtanzahl der Transmitter-/Transceiver-Verbindungen × 5*

Überprüfen Sie nach Abschluss des Versands die folgenden Punkte:

* Überprüfen Sie, ob alle Nachrichten gesendet (nicht unbedingt empfangen) wurden.
* Es darf absolut keine PDU geben, deren command_status nicht 0x00000000 ist, es sei denn, dies wird vom Provider ausdrücklich als normaler Vorgang angegeben.
* Verbindungen müssen während des gesamten Versandvorgangs absolut stabil bleiben (keine BIND-PDU).
* Überprüfen Sie, ob alle Nachrichten einen SR aufweisen und ob dieser korrekt verarbeitet wurde (siehe [Überprüfen, ob der SR ordnungsgemäß verarbeitet wurde](#real-test)). Wenn ein kleiner Prozentsatz Fehler aufweist, überprüfen Sie, ob es sich um tatsächliche SR-Rückgabefehler handelt und nicht um Fehler beim Versand oder bei der Verarbeitung auf der Campaign-Seite.
* Wenn Sie sich bezüglich der Leistung nicht sicher sind, stellen Sie sicher, dass die Latenzen angemessen sind, insbesondere zwischen einer PDU und der zugehörigen RESP. Eine Latenz von mehr als 500 ms kann ein Problem für einen hohen Durchsatz darstellen. Verwenden Sie diese Latenz, um die Formel für das Übertragungsfenster zu überprüfen (weitere Informationen finden Sie in der Einstellung für das Übertragungsfenster).

### Überprüfen der PDUs {#pdu}

Überprüfen Sie, ob PDUs korrekt formatiert sind.

>[!IMPORTANT]
>
>Dieser Schritt ist erforderlich, wenn eine Verbindung zu einem Provider hergestellt wird, der zuvor nicht mit Campaign verbunden war.

**BIND**

Vergewissern Sie sich, dass BIND_*-PDUs korrekt gesendet werden. Am wichtigsten ist es zu prüfen, dass der Provider immer erfolgreiche BIND_*_RESP-PDUs zurückgibt (command_status = 0).

Stellen Sie sicher, dass nicht zu viele BIND_*-PDUs vorhanden sind. Wenn es zu viele sind, kann das darauf hinweisen, dass die Verbindung instabil ist. Weitere Informationen finden Sie unten im Abschnitt zu Fehlerbehebungen unter „Probleme mit instabilen Verbindungen“.

**ENQUIRE_LINK**

Vergewissern Sie sich, dass ENQUIRE_LINK-PDUs regelmäßig ausgetauscht werden, wenn die Verbindung inaktiv ist.

**SUBMIT_SM / DELIVER_SM**

Senden Sie eine Nachricht und suchen Sie dann in den Logs nach den zugehörigen SUBMIT_SM-, SUBMIT_SM_RESP-, DELIVER_SM- und DELIVER_SM_RESP-PDUs.

Mit *SUBMIT_SM-PDU*:

* Überprüfen Sie, ob data_coding korrekt ist (standardmäßig „0“).
* Vergewissern Sie sich, dass short_message korrekt codiert ist: Decodieren Sie dies mit einem Hexadezimal-Konvertierer, der mehrere Codierungen unterstützt (online sind verschiedene verfügbar).
* Wenn Sie message_payload für lange Nachrichten verwenden, überprüfen Sie, ob der Inhalt im optionalen Feld und nicht im Feld „short_message“ vorhanden ist.

Mit *SUBMIT_SM_RESP-PDU*:

* Vergewissern Sie sich, dass dies erfolgreich war (command_status = 0).
* Vergewissern Sie sich, dass der Hauptteil eine ordnungsgemäß formatierte ID und anschließend ein Byte „0“ enthält.

Mit *DELIVER_SM-PDU*:

* Decodieren Sie das hexadezimale Feld „short_message“ (dafür gibt es Online-Tools).
* Überprüfen Sie mit einem Regex-Überprüfungs-Tool, ob der unter „Regex zur ID-Extraktion im SR“ definierte Regex genau eine Erfassungsgruppe zurückgibt und die gesamte ID in der Nachricht erfasst.
* Überprüfen Sie, ob die extrahierte ID mit der in SUBMIT_SM_RESP übereinstimmt.
* Vergewissern Sie sich, dass der unter „Regex zur Status-Extraktion im SR“ definierte Regex den Inhalt des stat-Felds zurückgibt.
* Vergewissern Sie sich, dass der unter „Regex zur Fehlercode-Extraktion im SR“ definierte Regex den Inhalt des err-Felds zurückgibt.

Mit *DELIVER_SM_RESP-PDU*:

* Vergewissern Sie sich, dass sie nach Empfang der DELIVER_SM-PDU schnell gesendet wurde (in der Regel in weniger als 1 Sekunde).
* Vergewissern Sie sich, dass dies erfolgreich war (command_status = 0).

### Live-Test mit dem Provider {#sms-live-test}

Eine Best Practice vor der Live-Schaltung besteht darin, einen Live-Test mit dem Provider durchzuführen, wobei sich beide Seiten während der Ausführung die Logs ansehen.

>[!IMPORTANT]
>
>Dieser Schritt ist erforderlich, wenn eine Verbindung zu einem Provider hergestellt wird, der zuvor nicht mit Campaign verbunden war.

### Deaktivieren der ausführlichen SMPP-Verfolgung {#sms-disable-smpp}

Sobald alle Überprüfungen abgeschlossen sind, müssen Sie als Letztes die ausführliche SMPP-Verfolgung deaktivieren, um nicht zu viele Logs zu generieren.

## SMS-Fehlerbehebung {#sms-troubleshooting}

### Allgemeine Fehlerbehebung {#sms-general-troubleshooting}

Der SMS-Connector bezieht drei Entitäten ein: SMPP-Provider, Adobe und Sie.
Die wichtigste SMS-Instanz ist der SMPP-Provider. Daher sollte dieser für alle SMS-Traffic-bezogenen Probleme (Verbindungsprobleme, verlorene Nachrichten, Kodierungsprobleme, länderspezifische Regeln usw.) eingebunden werden.

#### Aktivieren der Option für spezielle Prozesse {#sms-dedicated-process}

>[!IMPORTANT]
>
>Stellen Sie sicher, dass in allen aktiven SMS-Konten die Option **[!UICONTROL Nachrichten über einen speziellen Prozess senden]** aktiviert ist.

Wenn Sie Probleme mit dem älteren (MTA-basierten) Connector haben (spezieller Prozess deaktiviert), sollten Sie eine Migration zum dedizierten Prozess-Connector in Erwägung ziehen. Dieser zeigt eine deutlich bessere Leistung, ist stabiler und liefert viel besseres Feedback in seinen Logs.

#### Konflikt zwischen verschiedenen externen Konten {#sms-conflict-external-accounts}

Wenn die Instanz über mehrere externe SMS-Konten verfügt, müssen Sie sicherstellen, dass keine Probleme durch einen Konflikt zwischen externen Konten verursacht werden.

So isolieren Sie das externe Konto, das Probleme verursacht:

1. Deaktivieren Sie alle externen Konten.
1. Aktivieren Sie ein externes Konto.
1. Versuchen Sie, das Problem zu reproduzieren.
1. Wenn das Problem bei diesem einen Konto nicht auftritt, deaktivieren Sie es und beginnen Sie erneut mit Schritt 2 beim nächsten Konto. Nachdem Sie jedes Konto einzeln geprüft haben, gibt es zwei mögliche Szenarien:

**Das Problem trat bei einem oder mehreren Konten auf**

In diesem Fall können Sie für jedes Konto andere Verfahren zur Fehlerbehebung anwenden. Es ist am besten, andere Konten zu deaktivieren, während Sie eine Kontodiagnose durchführen, um den Netzwerk-Traffic und die Anzahl der Logs zu reduzieren.

**Das Problem trat nicht auf, wenn jeweils nur ein Konto aktiv war**

Es gibt einen Konflikt zwischen den Konten. Adobe Campaign behandelt die Konten einzeln, aber der Provider behandelt sie möglicherweise als ein einziges Konto.

*Sie verwenden unterschiedliche Benutzernamen-/Passwortkombinationen für all Ihre Konten*
Sie müssen sich an den Provider wenden, damit er mögliche Konflikte auf seiner Seite diagnostiziert.

*Einige der externen Konten verwenden dieselbe Benutzernamen-/Passwortkombination*
Der Provider kann nicht feststellen, von welchem externen Konto die BIND-PDU stammt. Daher werden alle Verbindungen von mehreren Konten als eine einzige behandelt, sodass wahrscheinlich MO und SR zufällig über die beiden Konten weitergeleitet wird, was zu scheinbar zufälligen Problemen führen kann.

Wenn der Provider mehrere Kurzwahlnummern für dieselbe Benutzernamen-/Passwortkombination unterstützt, müssen Sie ihn fragen, wo diese Kurzwahlnummer in die BIND-PDU eingefügt werden soll. Beachten Sie, dass diese Information in die BIND-PDU und nicht in SUBMIT_SM eingefügt werden muss, da nur in der BIND-PDU eine korrekte Weiterleitung von MOs möglich ist.

Weiter oben unter [Informationen in den verschiedenen PDU-Arten](#pdu) erfahren Sie, welche Felder in der BIND-PDU verfügbar sind. Normalerweise fügen Sie die Kurzwahlnummer in *address_range* hinzu. Dies erfordert jedoch besondere Unterstützung durch den Provider. Wenden Sie sich an diesen, um zu erfahren, wie er mehrere Kurzwahlnummern unabhängig voneinander weiterleiten wird.

Adobe Campaign unterstützt die Verarbeitung mehrerer Kurzwahlnummern in demselben externen Konto, sodass es häufig problemlos funktioniert, nur ein einziges Konto für den gesamten Traffic zu verwenden.

#### Ein externes Konto funktioniert nicht mehr {#sms-external-account-not-working}

Im Allgemeinen sind SMPP-Verbindungen im Laufe der Zeit tendenziell sehr stabil. Wenn sie einmal korrekt konfiguriert sind, sollten sie auch zukünftig weiter funktionieren.

* Untersuchen Sie, ob und von wem der Connector kürzlich geändert wurde (überprüfen Sie die externen Konten als Gruppe).
* Untersuchen Sie, ob und wann das System aktualisiert wurde.
* Untersuchen Sie, ob Pakete, die sich auf SMS auswirken, kürzlich aktualisiert wurden.

Wenn keine dieser Prüfungen zu einer Grundursache führt, wenden Sie sich an den Provider. Wenn Provider ihre Plattformen aktualisieren, verhalten sich ihre Connectoren geringfügig anders. Dies kann die Feineinstellungen beeinträchtigen und Regressionsprobleme nach sich ziehen.

Es wird empfohlen, mit dem Provider in Kontakt zu bleiben, denn häufig werden wichtige Änderungen im Voraus mitgeteilt.

#### Problem mit Mid-Sourcing (gehostet)  {#sms-issue-hosted}

* Wenn das Problem in einer Mid-Sourcing-Umgebung auftritt, stellen Sie sicher, dass die Versand- und Broadlogs ordnungsgemäß auf dem Mid-Sourcing-Server erstellt und aktualisiert werden. Wenn das nicht der Fall ist, liegt kein SMS-Problem vor.
* Achten Sie darauf, dass der Mid-Operator-Name ausschließlich Kleinbuchstaben umfasst. Andernfalls bleibt der Versand im Status „Ausstehend“.
* Wenn auf dem Mid-Sourcing-Server alles funktioniert und SMS ordnungsgemäß gesendet werden, die Marketing-Instanz jedoch nicht ordnungsgemäß aktualisiert wird, liegt ein Problem mit der Mid-Synchronisation vor.

#### Problem beim Herstellen einer Verbindung zum Provider {#sms-issue-connection}

* Wenn die BIND-PDU als *command_status*-Code nicht null zurückgibt (was bedeutet, dass ein Fehler vorliegt) oder wenn keine BIND_RESP-PDU vorhanden ist, erkundigen Sie sich beim Provider nach dem Grund.
* Überprüfen Sie, ob das Netzwerk ordnungsgemäß konfiguriert ist, damit die TCP-Verbindung zum Provider hergestellt werden kann.
* Bitten Sie den Provider, zu überprüfen, ob die IP-Adressen der Adobe Campaign-Instanz ordnungsgemäß zugelassen wurden (bei den meisten Providern erforderlich).
* Überprüfen Sie die Einstellungen für externe Konten. Fragen Sie den Provider, falls Sie beim Wert bestimmter Felder unsicher sind.
* Wenn die Verbindung erfolgreich, aber instabil ist, finden Sie nachstehend unter [Probleme mit instabilen Verbindungen](#unstable-connections) weitere Informationen.
* Wenn Verbindungsprobleme schwer zu diagnostizieren sind, liefert Ihnen eine Netzwerkaufzeichnung viele Informationen. Achten Sie darauf, dass die Netzwerkaufzeichnung während des Auftretens des Problems durchgeführt wird, damit es effizient analysiert werden kann. Sie sollten auch den genauen Zeitpunkt notieren, zu dem das Problem auftritt, damit das Problem einfacher in der Netzwerkaufzeichnung gefunden werden kann.

#### Probleme mit instabilen Verbindungen {#unstable-connections}

**Diagnostizieren instabiler Verbindungen:**

Eine Verbindung wird als instabil angesehen, wenn eine der folgenden Situationen eintritt:

* Die Verbindung besteht für weniger als eine Stunde.
* Durch einen Neustart des SMS-Prozesses werden die Probleme zwar behoben, aber nur vorübergehend. Dies bedeutet wahrscheinlich, dass es wegen einer instabilen Verbindung zu einer Drosselung kommt und die Drosselung durch einen Neustart des SMS-Prozesses aufgehoben wird. Dies geschieht dann so lange immer wieder, bis die Grundursache gefunden wird.
* Der Provider sendet UNBIND-PDUs. Der Provider sollte UNBIND-PDUs nie im normalen Betrieb senden.
* Das *enquire_link*-Zeitlimit wird entweder auf der Campaign-Seite oder auf der Provider-Seite überschritten. Möglicherweise wird in dem Fall ENQUIRE_LINK_RESP mit einem von null verschiedenen Fehler-Code angezeigt.
* Es gibt viele BIND-PDUs. Im Laufe eines Tages sollten nicht mehr als ein paar vorhanden sein (abhängig von der Anzahl der Verbindungen). Mehr als eine BIND-PDU pro Stunde und pro Verbindung sollte aufhorchen lassen.

**Beheben von Problemen mit der Verbindungsstabilität:**

* Instabile Verbindungen sind selten die eigentliche Ursache. Sie sind häufig das Ergebnis eines anderen Problems, das einen Verbindungsabbruch in irgendeiner Form auslöst. Die Suche nach der eigentlichen Ursache hat Priorität.
* Aktivieren Sie die ausführliche SMPP-Verfolgung. Sie benötigen diese, um zu sehen, was passiert, wenn die Verbindung neu gestartet wird.
* Wenn der Provider UNBIND-PDUs sendet, macht er wahrscheinlich etwas falsch. Fragen Sie ihn, warum er UNBIND sendet. Dies wird wahrscheinlich zur eigentlichen Ursache führen.
* Eine Netzwerkaufzeichnung ist manchmal die einzige Möglichkeit, um zu sehen, wie die Verbindung geschlossen wird.
* Wenn der Provider die Verbindungen schließt (indem er entweder ein TCP FIN- oder ein TCP RST-Paket sendet), fragen Sie ihn nach dem Grund dafür. Hierdurch sollten Sie die Ursache des Problems erfahren.
* Wenn der Provider die Verbindung schließt, nachdem er einen ordnungsgemäßen Fehler (wie DELIVER_SM_RESP mit einem Fehler-Code gesendet hat), muss er seinen Connector reparieren. Dieses Schließen verhindert nämlich, dass andere Arten von Nachrichten übertragen werden, und löst die MTA-Drosselung aus. Dies ist besonders im Transceiver-Modus wichtig, wo sich das Schließen der Verbindung sowohl auf MT als auch auf SR auswirkt.
* Bei Timeouts (BIND-Timeouts, SUBMIT_SM-Timeouts) sendet Campaign möglicherweise zu schnell Nachrichten für diesen Provider. Versuchen Sie, die Einstellung für den *maximalen MT-Durchsatz* zu senken, und überprüfen Sie, ob das Problem sich dadurch beheben lässt.

#### Problem beim Senden von MT (reguläre SMS an eine Endbenutzerin oder einen Endbenutzer)

* Prüfen Sie, ob die Verbindung stabil ist: Eine SMPP-Verbindung sollte mindestens eine Stunde lang kontinuierlich aufrechterhalten bleiben. Weitere Informationen finden Sie im Abschnitt „Probleme mit instabilen Verbindungen“.
* Wenn durch einen Neustart des SMS-Prozesses das Senden von MT für einen kurzen Zeitraum wieder funktioniert, besteht wahrscheinlich eine Drosselung aufgrund einer instabilen Verbindung. Weitere Informationen finden Sie im Abschnitt „Probleme mit instabilen Verbindungen“.
* Überprüfen Sie, ob das Broadlog vorhanden ist und den richtigen Status mit den richtigen Daten aufweist. Ist dies nicht der Fall, handelt es sich nicht um ein SMS-Problem, sondern um ein Versandproblem oder ein Problem bei der Versandvorbereitung (dies liegt außerhalb des Rahmens dieses Dokuments).
* Prüfen Sie, ob der SMS-Connector tatsächlich mit den Geräten des Providers verbunden ist. Bitten Sie den Provider um Rückmeldung, um sicherzustellen, dass alle Systeme richtig kommunizieren. Informationen zum Bindungsprozess finden Sie unter BIND_TRANSMITTER- und BIND_TRANSCEIVER-PDUs. Möglicherweise müssen Sie die SMPP-Verfolgung aktivieren, um eine ordnungsgemäße Fehlerbehebung zu ermöglichen.
* Überprüfen Sie bei aktivierter SMPP-Verfolgung, ob die SUBMIT_SM-PDU die richtigen Informationen enthält (siehe die obige Dokumentation).
* Stellen Sie sicher, dass der Provider mit einer SUBMIT_SM_RESP-PDU mit dem Wert „OK“ (Code 0) antwortet. Stellen Sie sicher, dass die PDU mit einer angemessenen Verzögerung eintrifft: Alles, was länger als 1 Sekunde dauert, ist verdächtig und muss mit dem Provider besprochen werden. Sie kommt normalerweise in weniger als 100 ms an.
* Wenn alle diese Schritte funktionieren, können Sie sicher sein, dass das Problem auf der Seite des Providers liegt. Er muss dann die Fehlersuche auf seiner Plattform durchführen.
* Wenn es funktioniert, der Durchsatz jedoch inkonsistent ist, versuchen Sie, das Übertragungsfenster anzupassen und den MT-Durchsatz zu verringern. Für diese Anpassung müssen Sie mit dem Provider zusammenarbeiten. Campaign kann Nachrichten sehr schnell senden, sodass Leistungsprobleme auf den Geräten des Providers auftreten können.

#### MT wird dupliziert (dieselbe SMS wird mehrmals hintereinander gesendet)

Duplikate werden häufig durch Wiederholungsversuche verursacht. Es ist normal, dass Duplikate auftreten, wenn Nachrichten erneut zugestellt werden. Sie sollten sich daher darauf konzentrieren, die Ursache für die weiteren Zustellversuche zu beseitigen.

* Wenn Sie sehen, dass Duplikate im Abstand von genau 60 Sekunden (oder in einem verdächtig „regelmäßigen“ Zeitraum) gesendet werden, ist dies wahrscheinlich ein Problem auf der Seite des Providers, der die SUBMIT_SM_RESP nicht schnell genug sendet.
* Wenn Sie viele BIND/UNBIND sehen, haben Sie eine instabile Verbindung: Lesen Sie den Abschnitt [Probleme mit instabilen Verbindungen](#unstable-connections) für Lösungen, bevor Sie versuchen, Probleme mit doppelten Nachrichten zu lösen.
* Vergewissern Sie sich, dass alle SUBMIT_SM-PDUs kurz danach die entsprechenden SUBMIT_SM_RESP aufweisen. Wenn dies nicht der Fall ist oder die SUBMIT_SM_RESP zu langsam sind, liegt das Problem auf der Seite des Providers.

Minimierung der Anzahl von Duplikaten bei einer Wiederholung:

* Reduzieren Sie das *Übertragungsfenster*. Das Übertragungsfenster sollte groß genug sein, um die Latenz der SUBMIT_SM_RESP abzudecken. Es sollte aber auch nicht zu groß sein. Sein Wert stellt die maximale Anzahl von Nachrichten dar, die dupliziert werden können, wenn ein Fehler auftritt, während das Fenster voll ist.

#### Problem bei der Verarbeitung von SR (Empfangsbestätigungen)

* Sie müssen die SMPP-Verfolgung aktivieren, um jegliche Art von SR-Fehlerbehebung durchzuführen.
* Überprüfen Sie, ob die DELIVER_SM-PDU vom Provider kommt und korrekt formuliert ist.
* Überprüfen Sie, ob Campaign rechtzeitig mit einer erfolgreichen DELIVER_SM_RESP-PDU antwortet. Diese gewährleistet, dass der SR in die Tabelle „providerMsgStatus“ eingefügt wurde, um die verzögerte Verarbeitung durch den SMS-Prozess zu ermöglichen.

Wenn die DELIVER_SM-PDU nicht erfolgreich quittiert wurde, müssen Sie einige Punkte überprüfen:

* Überprüfen Sie den Regex für die ID-Extraktion und die Fehlerverarbeitung im externen Konto. Möglicherweise müssen Sie diese anhand des Inhalts der DELIVER_SM-PDU validieren.
* Überprüfen Sie, ob die Fehler ordnungsgemäß in der Tabelle „broadLogMsg“ bereitgestellt wurden (in der Dokumentation zu Campaign wird dies im Detail erläutert).

Wenn die DELIVER_SM-PDU vom erweiterten SMPP-Connector in ACC quittiert wurde, das broadLog jedoch nicht ordnungsgemäß aktualisiert wird, überprüfen Sie den im Abschnitt „Abgleichen von MT-, SR- und broadLog-Einträgen“ beschriebenen Prozess zur ID-Abstimmung.

Wenn Sie alle Probleme behoben haben, die Puffer des Providers jedoch noch einige ungültige SR enthalten, können Sie diese mit der Option &quot;Zählung der &#39;ungültige ID&#39; Antworten&quot; überspringen. Dies sollte mit Vorsicht verwendet und so schnell wie möglich auf 0 zurückgesetzt werden, nachdem die Puffer bereinigt wurden.

Wenn die SR-Verarbeitung langsam ist, versuchen Sie, die häufigsten Statusmeldungen in der Tabelle „BroadLogMsg“ zu qualifizieren.

Wenn nur einige SR empfangen werden, aber nicht alle, stellen Sie sicher, dass kein anderes System eine Verbindung zum Konto Ihres Providers herstellt, z. B. ein Testsystem. SR können bei jeder Verbindung weitergeleitet werden, sodass einige von ihnen an dieses andere System weitergeleitet werden. Der Provider kann Ihnen dabei helfen, herauszufinden, wo sich dieses andere System befindet, das eine Verbindung zu dem Konto herstellt.

#### Problem bei der Verarbeitung von MO (und Quarantäne/automatische Antwort)

* Aktivieren Sie die SMPP-Verfolgung während der Tests. Wenn Sie TLS nicht aktivieren, ist es immer besser, während der Fehlerbehebung bei MO eine Netzwerkaufzeichnung durchführen, um zu überprüfen, ob die PDUs die richtigen Informationen enthalten und ordnungsgemäß formatiert sind.
* Wenn Sie Netzwerk-Traffic aufzeichnen oder SMPP-Protokolle analysieren, stellen Sie sicher, dass Sie die gesamte Konversation mit dem MO und seiner Antwort-MT erfassen (wenn eine Antwort konfiguriert ist).
* Wenn MO (DELIVER_SM-PDU) nicht in den Protokollen angezeigt wird, können Sie sicher sein, dass das Problem auf der Seite des Providers liegt. Er muss dann die Fehlersuche auf seiner Plattform durchführen.
* Wenn die DELIVER_SM-PDU angezeigt wird, überprüfen Sie, ob sie von Campaign mit einer erfolgreichen DELIVER_SM_RESP-PDU (Code 0) quittiert wird. Diese RESP garantiert, dass die gesamte Verarbeitungslogik von Campaign angewendet wurde (automatische Antwort und Quarantäne). Wenn dies nicht der Fall ist, überprüfen Sie die Logs des SMS-Prozesses auf eine Fehlermeldung.
* Wenn automatische Antworten aktiviert sind, überprüfen Sie, ob SUBMIT_SM an den Provider gesendet wurde. Ist das nicht der Fall, können Sie davon ausgehen, dass die Logs des SMS-Prozesses eine Fehlermeldung enthalten.
* Wenn die SUBMIT_SM MT PDU, die die Antwort enthält, in den Protokollen gefunden wird, die SMS aber nicht auf dem Mobiltelefon ankommt, müssen Sie sich an den Provider wenden, um Unterstützung bei der Fehlerbehebung zu erhalten, da das Problem wahrscheinlich auf seiner Seite liegt.

#### Problem bei der Versandvorbereitung, die Empfänger unter Quarantäne nicht ausschließt (durch die automatische Antwortfunktion in Quarantäne gestellt)

* Überprüfen Sie, ob die Telefonnummern in der Quarantänetabelle und im Versand-Log im exakt gleichen Format vorliegen. Ist dies nicht der Fall, sehen Sie sich oben die Informationen zur Einstellung „Vollständige Telefonnummer senden“ an, wenn Sie Probleme mit dem „+“-Präfix des internationalen Telefonnummernformats haben.
* Überprüfen von Kurzwahlnummern: Es kann zu Ausschlüssen kommen, wenn die Kurzwahlnummer der Empfängerin bzw. des Empfängers entweder dieselbe ist, wie im externen Konto definiert, oder wenn sie leer ist (leer = beliebige Kurzwahlnummer). Falls nur eine Kurzwahlnummer für die gesamte Campaign-Instanz verwendet wird, ist es einfacher, alle Felder mit Kurzwahlnummern leer zu lassen.

#### Codierungsprobleme  {#sms-encoding-issues}

Codierungsprobleme treten häufig in SMS auf. Im Folgenden finden Sie einige grundlegende Schritte:

**Schritt 1: Kontaktaufnahme mit dem Provider**

Der Provider ist der Experte, der weiß, wie SMS funktioniert. Nehmen Sie Kontakt mit ihm auf und ermitteln Sie gemeinsam mit ihm das Problem. Er sollte Ihnen mitteilen können, ob das Problem auf seiner Seite oder auf der Seite von Campaign liegt. Wenn das Problem in Campaign auftritt, sollte er Ihnen genau mitteilen können, welches Feld falsch ist. Dies ist eine enorme Hilfe.

**Schritt 2: Inhalt Ihrer Nachricht überprüfen**

Sie müssen den Inhalt Ihrer Nachricht kennen. Dieser Satz mag leicht klingen, aber das ist es nicht. Unicode erlaubt mehrere Varianten für ähnlich aussehende Zeichen, und Campaign kann nicht alle verarbeiten.

Die häufigste Ursache für Probleme ist das Kopieren und Einfügen aus einem Textverarbeitungsprogramm, bei dem übliche Zeichen in typografisch korrekte Versionen geändert werden: Leerzeichen in geschützte Leerzeichen, doppelte Anführungszeichen in öffnende und schließende Anführungszeichen oder Minuszeichen in verschiedene Arten von Bindestrichen.

Kopieren Sie Ihre Nachricht beim Testen nicht, sondern geben Sie sie immer direkt in die Benutzeroberfläche ein.

**Lassen Sie sich nicht durch hexadezimale Werte verunsichern**. Hexadezimale Werte sehen ungewohnt und unnatürlich aus, haben jedoch den Vorteil, dass Sie den Unterschied zwischen ähnlichen Zeichen erkennen können. Ein kleines L, ein großes I, O, 0, alle verschiedenen Arten von Anführungszeichen, nicht-lateinische Codierungen oder sogar verschiedene Arten von Leerzeichen können jeweils gleich aussehen (oder gar nicht sichtbar sein). Hexadezimale Werte zeigen alles und helfen beim Vergleichen von Dingen.

Um Unicode in hexadezimale Werte zu konvertieren, können Sie Online-Tools verwenden.

Geben Sie **beim Eröffnen von Tickets** für Codierungsprobleme, sei es beim Provider oder beim Campaign-Support, **eine hexadezimale** Version Ihrer Eingabe und Ihrer Anzeige an.

**Schritt 3: Überprüfen, was Sie senden sollten**

Legen Sie die Kodierung fest, die Sie voraussichtlich verwenden werden, und suchen Sie online nach der Zeichentabelle. Vergewissern Sie sich, dass die Zeichen, die Sie senden möchten, tatsächlich in dieser Zeichenumsetztabelle verfügbar sind. Überprüfen Sie, ob das Feld „data_coding“ korrekt ist und mit dem übereinstimmt, was Sie und der Provider erwarten.

**Schritt 4: Überprüfen, was Sie tatsächlich gesendet haben**

Sie benötigen die Debug-Ausgabe des Connectors, um genau zu sehen, welche Bytes Sie an den Provider senden. Codierungsprobleme treten in SUBMIT_SM-PDUs auf. Zeichnen Sie sie daher unbedingt auf. Senden Sie gut erkennbare Nachrichten, die im Log leicht zu finden sind.

Senden Sie beim Testen ruhig verschiedene Sonderzeichen. Zum Beispiel enthält die GSM7-Codierung erweiterte Zeichen, deren hexadezimale Form sich von anderen stark unterscheidet. Sie sind daher leicht zu erkennen, denn sie kommen in keiner anderen Codierung vor.

#### Leistungsprobleme {#sms-performance-issues}

>[!NOTE]
>
>Das Thema Leistung ist ein sehr weites Feld. In diesem Abschnitt werden verschiedene grundlegende Prüfvorgänge beschrieben, die vor einer Skalierung oder anderen großen Projekten durchgeführt werden sollten.

**Leistungsprobleme beim Senden von MT**

* Überprüfen Sie, ob alle Einstellungen im Abschnitt „Durchsatz und Verzögerungen“ des externen Kontos korrekt sind und mit den laut Provider zulässigen Einstellungen übereinstimmen.
* Vergewissern Sie sich, dass keine Wiederholungen vorhanden sind.
* Vergewissern Sie sich, dass die Infrastruktur des Providers nicht überlastet ist. Suchen Sie in den RESP-PDUs nach RMSGQFUL- oder RTHROTTLED-Fehlern.
* Überprüfen Sie die serverConf-Einstellungen. Beginnen Sie mit den Standardwerten und erhöhen Sie die Parameter langsam und einzeln.
* Vergewissern Sie sich, dass der SMS-Prozess unter Last nicht immer wieder neu gestartet wird. Ist dies der Fall, müssen Sie ggf. *maxSMSMemoryMb*, *maxProcessMemoryAlertMb* und *maxProcessMemoryWarningMb* in der serverConf-Datei erhöhen.

**Leistungsprobleme beim Empfang von SR**

Wenn der Provider von einer Pufferüberlastung berichtet, liegt dies möglicherweise daran, dass Campaign SR nicht schnell genug erhält.

* Vergewissern Sie sich, dass die Instanzdatenbank nicht überlastet ist. Die SR-Verarbeitung hängt in hohem Maße von der Leistung der Datenbank ab.
* Bitten Sie den Provider, das Sendefenster für DELIVER_SM auf seiner Seite zu vergrößern. Idealerweise sollte es so groß sein wie die Einstellung *batchUpdateSize* in serverConf.

### Elemente, die bei der Kommunikation über ein SMS-Problem berücksichtigt werden müssen

Wann immer Sie um Unterstützung bei einem SMS-Problem bitten (sei es durch das Eröffnen eines Support-Tickets bei Adobe Campaign, beim SMS-Provider oder bei jeder Art von Kommunikation im Zusammenhang mit dem Problem), müssen Sie zumindest die folgenden Informationen angeben, damit das Problem richtig eingeordnet werden kann. Die korrekte Einordnung von Problemen ist entscheidend für eine schnelle Problemlösung. Sich also etwas mehr Zeit zu nehmen, um die Situation zu verstehen und aussagekräftige Informationen bereitzustellen, ist mit einer enormen Effizienzsteigerung verbunden.

* Aktivieren Sie ausführliche SMPP-Nachrichten, wenn das Problem auftritt. Die meisten SMS-Probleme lassen sich praktisch nur damit lösen.
* Wenn das Problem mit dem SMS-Traffic zusammenhängt, wenden Sie sich zuerst an den Provider. Dieser weiß in diesem Fall am besten Bescheid, und die Plattform des Providers ist in der Regel auf eine effiziente Diagnose von SMS-Traffic-Problemen in Echtzeit ausgelegt.
* Fügen Sie eine kurze, sachliche Beschreibung des Problems bei.
* Fügen Sie eine Beschreibung des erwarteten Ergebnisses bei.
* Fügen Sie das Feedback des Providers bei.
* Fügen Sie relevante Logs und/oder Netzwerkaufzeichnungen bei. Achten Sie bei der Aufzeichnung darauf, das Problem während der Aufzeichnung zu reproduzieren. Andernfalls ist diese nutzlos.
* Wenn Sie Logs, Traces oder Aufzeichnungen beifügen, geben Sie genau an, wo das Problem in der Datei auftritt und auch wo sich ggf. ein funktionierendes Beispiel befindet. Aufzeichnungen oder Traces können umfangreich und ihre Durchsicht entsprechend mühsam sein. Daher ist alles, was dabei hilft, darin Informationen zu finden, nützlich.
* Wenn Sie auf Nachrichten, PDUs oder Logs verweisen, geben Sie deren Zeitstempel an, damit sie von anderen Personen leichter zu finden sind.
* Versuchen Sie, das Problem in einer Testumgebung zu reproduzieren. Wenn Sie sich bei einer Einstellung nicht sicher sind, versuchen Sie sie in der Testumgebung und überprüfen Sie das Ergebnis mit SMPP-Traces. In der Regel ist es besser, in Testumgebungen replizierte Probleme zu melden, als Probleme in Produktionsumgebungen direkt zu melden.
* Schließen Sie alle Änderungen oder Optimierungen ein, die auf der Plattform vorgenommen wurden: Selbst eine kleine Änderung kann enorme Auswirkungen haben. Schließen Sie auch alle Änderungen ein, die der Provider möglicherweise auf seiner Seite vorgenommen hat.

#### Wann ist eine Netzwerkaufzeichnung nützlich?

Eine Netzwerkaufzeichnung ist nicht immer erforderlich. Sehr oft reichen ausführliche SMPP-Nachrichten aus. Im Folgenden finden Sie einige Richtlinien, anhand derer Sie feststellen können, ob sich eine Netzwerkaufzeichnung lohnt:

* Es gibt Verbindungsprobleme, aber in den ausführlichen Meldungen werden keine BIND_RESP-PDUs angezeigt.
* Ungeklärte Verbindungsabbrüche ohne Fehlermeldung (so verhält sich der Connector, wenn er einen Protokollfehler auf niedriger Ebene erkennt).
* Der Provider reklamiert Verbindungsabbrüche.
* Es gibt Codierungsprobleme in optionalen TLV-Feldern.
* Es wird vermutet, dass der Traffic zwischen verschiedenen Verbindungen vermischt ist.

Versuchen Sie in allen anderen Situationen, zuerst ausführliche SMPP-Meldungen zu analysieren, und fordern Sie nur dann eine Netzwerkaufzeichnung an, wenn klar ist, dass Informationen in den ausführlichen Logs fehlen.

#### Wann ist eine Netzwerkaufzeichnung nutzlos?

In einigen Fällen ist die Aufzeichnung von Netzwerk-Traffic nutzlos oder reine Zeitverschwendung. Die häufigsten Situationen sind:

* TLS aktiviert: Der TLS-Traffic ist von vornherein verschlüsselt, sodass er nicht aufgezeichnet werden kann.
* Performance-Probleme: Die Logs enthalten alle erforderlichen Informationen zum Verfolgen von Performance-Problemen.
* Timing-Probleme (Wiederholungszeitpunkt, enquire_link-Zeitraum, Durchsatzbegrenzung usw.).
* SR-Analyse und -Verarbeitung: Ausführliche Logs bieten viel mehr Kontext und eine bessere Darstellung.
* MO-Verarbeitung (automatische Antworten, Quarantäne).
* Fehler, die nicht den eigentlichen SMPP-Traffic betreffen: Versandvorbereitung, Probleme mit der Message Center-API, Workflow-Probleme usw.
