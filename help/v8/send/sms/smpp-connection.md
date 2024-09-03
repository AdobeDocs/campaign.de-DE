---
title: Überprüfen einer SMPP-Verbindung
description: Erfahren Sie, wie Sie eine SMPP-Verbindung überprüfen
feature: SMS
role: User
level: Intermediate
badge: label="Eingeschränkte Verfügbarkeit" type="Informative"
source-git-commit: dde669980493b996c80baacc8726db87353585ad
workflow-type: tm+mt
source-wordcount: '4445'
ht-degree: 16%

---


# Überprüfen einer SMPP-Verbindung {#validate-smpp-connection}

Im Folgenden finden Sie einige Prüfungen, um sicherzustellen, dass Ihre SMPP-Verbindung in Ordnung ist.

## Was vor der Live-Schaltung zu überprüfen ist {#check-go-live}

Stellen Sie vor der Live-Schaltung sicher, dass Ihr SMPP-Setup mit der folgenden Checkliste Ok ist.

>[!IMPORTANT]
>
>Diese Checkliste ist nicht vollständig. Je mehr Prüfungen du machst, desto besser.

>[!NOTE]
>
>Aktivieren Sie ausführliche SMPP-Traces während der Prüfungen. Dies hilft Ihnen und dem Supportteam, die Fehlerbehebungen zu verstehen.

### Prüfen auf Konflikte mit externen Konten {#sms-external-accounts-check}

Vergewissern Sie sich, dass Sie über keine externen SMS-Konten verfügen. Löschen Sie die Testkonten, um potenzielle Konflikte zu vermeiden.

Vergewissern Sie sich, dass keine andere Instanz eine Verbindung zum externen Konto herstellt. Stellen Sie insbesondere sicher, dass die preprod-Umgebung keine Verbindung zum externen Konto prod herstellt.

Wenn Sie mehrere Konten für dieselbe Campaign-Instanz benötigen, die sich mit demselben Provider verbinden, wenden Sie sich an den Provider, um sicherzustellen, dass er tatsächlich zwischen den Verbindungen zwischen diesen Konten unterscheidet. Für mehrere Konten mit denselben Anmeldedaten ist eine zusätzliche Konfiguration erforderlich.

Vergewissern Sie sich, dass für alle aktivierten externen SMS-Konten die dedizierte Prozesseinstellung aktiviert ist. Sie können nicht zwischen den beiden Arten von Konten (mit und ohne dedizierten Prozess) auf derselben Instanz mischen.

### Führen Sie einen realen Test durch {#real-test}

Versuchen Sie, einige SMS auf verschiedenen Mobiltelefonen zu senden.

**SMS mit allen möglichen Zeichen senden**

Wenn Sie SMS mit Nicht-GSM- oder Nicht-ASCII-Zeichen senden müssen, versuchen Sie, einige Nachrichten mit möglichst unterschiedlichen Zeichen zu senden. Wenn Sie eine benutzerdefinierte Zeichenzuordnungstabelle einrichten, senden Sie mindestens eine SMS für alle möglichen data_coding -Werte.

**Überprüfen, ob SR ordnungsgemäß verarbeitet werden**

Die SMS sollte im Versandlog als empfangen gekennzeichnet werden. Das Versandlog sollte erfolgreich sein und wie folgt aussehen: &quot;*SR yourProvider stat=DELIVRD err=000|#MESSAGE#*&quot;.

Vergewissern Sie sich, dass Sie das Feld &quot;*Name der SMSC-Implementierung*&quot; richtig eingerichtet haben: Das Versandlog darf in Produktionsumgebungen niemals &quot;*SR Generic*&quot; enthalten.

**Überprüfen, ob MO verarbeitet werden**

Senden Sie einige SMS für alle automatischen Antwort-Keywords und vergewissern Sie sich, dass die Antwort schnell erfolgt (maximal einige Sekunden).

Vergewissern Sie sich, dass die MOs in die Datenbank *nms:inSms* eingefügt wurden. Wenn Sie benutzerdefinierte TLVs haben, stellen Sie sicher, dass diese ebenfalls korrekt eingefügt und korrekt formatiert sind.

Überprüfen Sie im Protokoll, ob Campaign mit einer erfolgreichen *DELIVER_SM_RESP (command_status=0)* antwortet.

**Führen Sie einen Belastungstest durch**

Dies ist besonders wichtig, wenn Sie viele Nachrichten senden oder Echtzeit-Nachrichten verwenden.

Führen Sie einen Test durch, bei dem die Verbindung mindestens 5 Sekunden lang zu 100 % geladen wird. Sie müssen echte Nachrichten senden, wenn der Provider keine Möglichkeit hat, sich für Tests mit einem gefälschten Konto zu verbinden. Eine Möglichkeit, dies zu erreichen, besteht darin, den ersten ausreichend großen Versand mit aktivierten ausführlichen SMPP-Nachrichten genau zu überwachen.

Die Mindestanzahl an zu sendenden Nachrichten kann wie folgt berechnet werden:

*Max. MT-Durchsatz * Gesamtzahl der Transmitter-/Transceiver-Verbindungen * 5*

Überprüfen Sie nach Abschluss des Versands die folgenden Punkte:

* Überprüfen Sie, ob alle Nachrichten gesendet wurden (nicht unbedingt empfangen wurden).
* PDU muss absolut null mit command_status sein, nicht 0x0000000, es sei denn, dies wird vom Provider ausdrücklich als normaler Betrieb angegeben
* Verbindungen müssen während des gesamten Versandvorgangs absolut stabil bleiben (keine BIND PDU).
* Überprüfen Sie, ob alle Nachrichten einen SR aufweisen und ob dieser korrekt verarbeitet wurde (siehe [Überprüfen, ob der SR ordnungsgemäß verarbeitet wurde](#real-test)). Wenn ein kleiner Prozentsatz Fehler aufweist, überprüfen Sie, ob es sich um tatsächliche SR-Fehler handelt, die beim Versand oder bei der Verarbeitung in Campaign zurückgegeben werden, und nicht um Fehler beim Versand oder bei der Verarbeitung.
* Wenn Sie sich bezüglich der Leistung nicht sicher sind, stellen Sie sicher, dass Latenzzeiten angemessen sind, insbesondere zwischen einer PDU und der zugehörigen RESP. Eine Latenz von mehr als 500 ms kann ein Problem für hohen Durchsatz sein. Verwenden Sie diese Latenz, um die Formel für das Übertragungsfenster zu überprüfen (weitere Informationen finden Sie in der Einstellung für das Übertragungsfenster ).

### Überprüfen der PDUs {#pdu}

Überprüfen Sie, ob PDUs korrekt formatiert sind.

>[!IMPORTANT]
>
>Dieser Schritt wird dringend empfohlen, wenn eine Verbindung zu einem Provider hergestellt wird, der zuvor nicht mit Campaign verbunden war.

**BIND**

Überprüfen Sie, ob BIND_* PDUs korrekt gesendet werden. Am wichtigsten ist es zu überprüfen, dass der Provider immer erfolgreiche BIND_*_RESP PDUs zurückgibt (command_status = 0).

Vergewissern Sie sich, dass nicht zu viele BIND_* PDUs vorhanden sind. Wenn zu viele vorhanden sind, kann dies darauf hinweisen, dass die Verbindung instabil ist. Weitere Informationen dazu finden Sie im Abschnitt Fehlerbehebung bei instabilen Verbindungen unten.

**INQUIRE_LINK**

Vergewissern Sie sich, dass INQUIRE_LINK-PDUs regelmäßig ausgetauscht werden, wenn die Verbindung inaktiv ist.

**SUBMIT_SM / DELIVER_SM**

Senden Sie eine Nachricht und suchen Sie dann in den Protokollen nach den entsprechenden PDUs SUBMIT_SM, SUBMIT_SM_RESP, DELIVER_SM und DELIVER_SM_RESP .

Mit der *SUBMIT_SM PDU*:

* Überprüfen Sie, ob data_coding korrekt ist (standardmäßig 0).
* Vergewissern Sie sich, dass short_message korrekt kodiert ist: Dekodieren Sie diese mit einem hexadezimalen Konverter, der mehrere Kodierungen unterstützt (einige sind online verfügbar).
* Wenn Sie message_payload für lange Nachrichten verwenden, überprüfen Sie, ob der Inhalt im optionalen Feld und nicht im Feld short_message vorhanden ist.

Mit der *SUBMIT_SM_RESP PDU*:

* Überprüfen Sie, ob sie erfolgreich war (command_status = 0).
* Vergewissern Sie sich, dass der Hauptteil eine ordnungsgemäß formatierte ID und anschließend ein 0-Byte enthält.

Mit der *DELIVER_SM PDU*:

* Dekodieren Sie das hexadezimale short_message -Feld (dafür gibt es Online-Tools).
* Überprüfen Sie mit einem Regex-Überprüfungstool, ob der im Regex zur ID-Extraktion im SR definierte Regex genau eine Erfassungsgruppe zurückgibt und die gesamte ID in der Nachricht erfasst.
* Überprüfen Sie, ob die extrahierte ID mit der in SUBMIT_SM_RESP übereinstimmt.
* Vergewissern Sie sich, dass der in Extraktionsregex des Status im SR definierte Regex den Inhalt des stat-Felds zurückgibt.
* Überprüfen Sie, ob der im Regex zur Extraktion des Fehlers im SR definierte Regex den Inhalt des err-Felds zurückgibt.

Mit der *DELIVER_SM_RESP PDU*:

* Vergewissern Sie sich, dass die Nachricht nach Erhalt der DELIVER_SM-PDU schnell gesendet wurde (normalerweise weniger als 1 Sekunde).
* Überprüfen Sie, ob sie erfolgreich war (command_status = 0).

### Live-Test mit dem Provider {#sms-live-test}

Eine Best Practice vor der Live-Schaltung besteht darin, einen Live-Test mit dem Provider durchzuführen, wobei sich beide Seiten während der Ausführung die Protokolle ansehen.

>[!IMPORTANT]
>
>Dieser Schritt wird dringend empfohlen, wenn eine Verbindung zu einem Provider hergestellt wird, der noch nie zuvor mit Campaign verbunden war.

### Deaktivieren der ausführlichen SMPP-Verfolgung {#sms-disable-smpp}

Sobald alle Prüfungen abgeschlossen sind, besteht die letzte Aktion darin, die ausführliche SMPP-Verfolgung zu deaktivieren, damit nicht zu viele Protokolle generiert werden.

## SMS-Fehlerbehebung {#sms-troubleshooting}

### Allgemeine Fehlerbehebung {#sms-general-troubleshooting}

Der SMS-Connector umfasst drei Entitäten: den SMPP-Provider, die Adobe und Sie.
Der wichtigste SMS-Experte ist der SMPP-Provider, daher sollten diese für alle SMS-Traffic-bezogenen Probleme (Verbindungsprobleme, verlorene Nachrichten, Kodierungsprobleme, länderspezifische Regeln usw.) einbezogen werden.

#### Dedizierten Prozess aktivieren {#sms-dedicated-process}

>[!IMPORTANT]
>
>Stellen Sie sicher, dass in allen aktiven SMS-Konten der Typ **[!UICONTROL Nachrichten über einen dedizierten Prozess senden]** aktiviert ist.

Wenn Sie Probleme mit dem älteren (MTA-basierten) Connector haben (dedizierter Prozess deaktiviert), sollten Sie eine Migration zum dedizierten Prozess-Connector in Erwägung ziehen. Es leistet viel bessere Ergebnisse, ist stabiler und liefert viel besseres Feedback in seinen Protokollen.

#### Konflikt zwischen verschiedenen externen Konten {#sms-conflict-external-accounts}

Wenn die Instanz über mehrere externe SMS-Konten verfügt, überprüfen Sie, ob Probleme nicht durch einen Kontokonflikt verursacht werden.

So isolieren Sie das externe Konto, das Probleme verursacht:

1. Alle externen Konten deaktivieren
1. Ein externes Konto aktivieren
1. Versuchen Sie, das Problem zu reproduzieren
1. Wenn das Problem bei diesem einzelnen Konto nicht auftritt, deaktivieren Sie es und starten Sie es beim nächsten Konto mit Schritt 2 neu. Nachdem Sie alle Konten einzeln geprüft haben, gibt es zwei mögliche Szenarien:

**Das Problem trat bei einem oder mehreren Konten auf**

In diesem Fall können Sie für jedes Konto andere Verfahren zur Fehlerbehebung anwenden. Es ist am besten, andere Konten bei der Diagnose eines Kontos zu deaktivieren, um den Netzwerk-Traffic und die Anzahl der Protokolle zu reduzieren.

**Das Problem trat nicht auf, wenn jeweils nur ein Konto aktiv war**

Es gibt einen Konflikt zwischen den Konten. Adobe Campaign behandelt Konten einzeln, doch der Provider behandelt sie möglicherweise als ein einziges Konto.

*Sie verwenden unterschiedliche Anmelde-/Kennwortkombinationen zwischen all Ihren Konten*
Sie müssen sich an den Provider wenden, um mögliche Konflikte auf seiner Seite zu diagnostizieren.

*Einige der externen Konten verwenden dieselbe Anmelde-/Kennwortkombination*
Der Provider kann nicht feststellen, von welchem externen Konto die BIND PDU stammt. Daher werden alle Verbindungen von mehreren Konten als eine einzige behandelt, sodass sie wahrscheinlich MO und SR zufällig über die beiden Konten weiterleiten, was scheinbar zufällige Probleme verursacht.

Wenn der Provider mehrere Kurzwahlnummern für dieselbe Anmelde-/Kennwortkombination unterstützt, müssen Sie ihn fragen, wo diese Kurzwahlnummer in die BIND PDU eingefügt werden soll. Beachten Sie, dass diese Information in die BIND PDU und nicht in SUBMIT_SM eingefügt werden muss, da die BIND PDU der einzige Ort ist, der ein korrektes Routing von MOs ermöglicht.

Lesen Sie den Abschnitt [Informationen in den einzelnen PDU-Typen](#pdu) weiter oben, um zu erfahren, welche Felder in der BIND PDU verfügbar sind. Im Allgemeinen würden Sie die Kurzwahlnummer in *address_range* ablegen, dies erfordert jedoch besondere Unterstützung durch den Provider. Kontaktieren Sie sie, um zu erfahren, wie sie erwarten, mehrere Kurzwahlnummern unabhängig voneinander zu leiten.

Adobe Campaign unterstützt die Verarbeitung mehrerer Kurzwahlnummern innerhalb desselben externen Kontos, sodass oft nur die Verwendung eines einzigen Kontos für den gesamten Traffic problemlos funktioniert.

#### Ein externes Konto funktionierte nicht mehr {#sms-external-account-not-working}

Im Allgemeinen sind SMPP-Verbindungen im Laufe der Zeit tendenziell sehr stabil. Sobald sie korrekt konfiguriert sind, sollten sie weiterhin funktionieren.

* Untersuchen Sie, ob und von wem der Connector kürzlich geändert wurde (überprüfen Sie die externen Konten als Gruppe).
* Untersuchen Sie, ob und wann das System aktualisiert wurde.
* Untersuchen Sie, ob möglicherweise Pakete, die SMS betreffen, kürzlich aktualisiert wurden.

Wenn keine dieser Prüfungen zu einer Grundursache führt, wenden Sie sich an den Provider. Manchmal verhalten sich Anbieter beim Aktualisieren ihrer Plattformen etwas anders, wenn sie ihre Plattformen aktualisieren. Dies kann die Feineinstellungen beeinträchtigen und Regressionen bewirken.

Es wird empfohlen, mit dem Provider in Kontakt zu bleiben. Häufig werden wichtige Änderungen im Voraus mitgeteilt.

#### Problem mit Mid-Sourcing (gehostet)  {#sms-issue-hosted}

* Wenn das Problem in einer Mid-Sourcing-Umgebung auftritt, stellen Sie sicher, dass die Versand- und Broadlogs ordnungsgemäß auf dem Mid-Sourcing-Server erstellt und aktualisiert wurden. Ist dies nicht der Fall, handelt es sich bei dem Problem nicht um ein SMS-Problem.
* Achten Sie darauf, dass der Name des Mid-Operators in Kleinbuchstaben streng ist. Andernfalls bleibt der Versand im Status &quot;Ausstehend&quot;.
* Wenn alles auf dem Mid-Server funktioniert und SMS ordnungsgemäß gesendet werden, die Marketing-Instanz jedoch nicht ordnungsgemäß aktualisiert wird, liegt ein Problem mit der Mid-Synchronisierung vor.

#### Problem beim Herstellen einer Verbindung zum Provider {#sms-issue-connection}

* Wenn die BIND PDU einen nicht null *command_status* -Code zurückgibt (was bedeutet, dass ein Fehler vorliegt) oder wenn keine BIND_RESP PDU vorhanden ist, fragen Sie den Provider, warum dies passiert.
* Überprüfen Sie, ob das Netzwerk ordnungsgemäß konfiguriert ist, damit die TCP-Verbindung zum Provider hergestellt werden kann.
* Bitten Sie den Provider, zu überprüfen, ob die IP-Adressen der Adobe Campaign-Instanz ordnungsgemäß zugelassen wurden (die meisten Provider erfordern dies).
* Überprüfen Sie die Einstellungen für externe Konten. Fragen Sie den Provider, falls Sie Zweifel am Wert einiger Felder haben.
* Wenn die Verbindung erfolgreich, aber instabil ist, überprüfen Sie die [Probleme mit instabilen Verbindungen](#unstable-connections). unten.
* Wenn Verbindungsprobleme schwer zu diagnostizieren sind, bringt Ihnen eine Netzwerkaufzeichnung viele Informationen. Stellen Sie sicher, dass die Netzwerkaufzeichnung gleichzeitig ausgeführt wird, während das Problem auftritt, damit es effizient analysiert werden kann. Sie sollten auch den genauen Zeitpunkt notieren, zu dem das Problem auftritt, damit es einfacher ist, das Problem in Netzwerkaufnahmen zu finden.

#### Probleme mit instabilen Verbindungen {#unstable-connections}

**Diagnose instabiler Verbindungen:**

Eine Verbindung wird als instabil betrachtet, wenn eines dieser Dinge geschieht:

* Die Verbindung dauert weniger als eine Stunde.
* Beim Neustart des SMS-Prozesses werden die Dinge vorübergehend &quot;korrigiert&quot;. Wahrscheinlich bedeutet dies, dass eine instabile Verbindung den Trigger drosselt, der SMS-Prozess neu gestartet wird, die Drosselung löscht und dann erneut ausgeführt wird, bis die Grundursache gefunden wird.
* Der Provider sendet UNBIND-PDUs. Der Provider sollte UNBIND-PDUs nie im normalen Betrieb senden.
* *inquire_link* ist mit einem Timeout verbunden, entweder auf der Kampagnenseite oder auf der Seite des Providers. Möglicherweise wird Ihnen INQUIRE_LINK_RESP mit einem Fehler-Code ungleich null angezeigt.
* Es gibt viele BIND-PDUs. Es sollte nicht mehr als ein paar an einem Tag geben (es hängt von der Anzahl der Verbindungen ab). Mehr als 1 BIND PDU pro Stunde und pro Verbindung sollte eine Warnung sein.

**Beheben von Problemen mit der Verbindungsstabilität:**

* Instabile Verbindungen sind selten die eigentliche Ursache. Sie sind häufig das Ergebnis eines anderen Problems, das eine Verbindungsabbrüche auslöst. Die Suche nach der eigentlichen Ursache hat Priorität.
* Aktivieren Sie die ausführliche SMPP-Verfolgung. Sie benötigen sie, um zu sehen, was beim Neustart der Verbindung passiert.
* Wenn der Provider UNBIND-PDUs sendet, macht er wahrscheinlich etwas falsch. Fragen Sie sie, warum sie UNBIND senden und dies wird wahrscheinlich zur eigentlichen Ursache führen.
* Eine Netzwerkaufzeichnung ist manchmal die einzige Möglichkeit, um zu sehen, wie die Verbindung geschlossen wird.
* Wenn der Provider die Verbindungen schließt (indem er entweder ein TCP FIN- oder ein TCP RST-Paket sendet), fragen Sie ihn, warum er dies tut. Dies sollte Ihnen die Ursache des Problems mitteilen.
* Wenn der Provider die Verbindung schließt, nachdem er einen ordnungsgemäßen Fehler gesendet hat (z. B. DELIVER_SM_RESP mit einem Fehlercode), muss er seinen Connector reparieren, da dies verhindert, dass andere Arten von Nachrichten übertragen werden, und Trigger-MTA-Drosselung auslöst. Dies ist besonders im Transceiver-Modus wichtig, wo sich das Schließen der Verbindung sowohl auf MT als auch auf SR auswirkt.
* Bei Timeouts (BIND-Timeouts, SUBMIT_SM-Timeouts) sendet Campaign möglicherweise zu schnell Nachrichten für diesen Provider. Versuchen Sie, die Einstellung für den *maximalen MT-Durchsatz* zu senken, und überprüfen Sie, ob das Problem dadurch behoben wird.

#### Problem beim Senden von MT (reguläre SMS an einen Endbenutzer)

* Prüfen Sie, ob die Verbindung stabil ist: Eine SMPP-Verbindung sollte mindestens eine Stunde lang kontinuierlich aufrechterhalten bleiben. Siehe oben den Abschnitt &quot;Problem mit instabilen Verbindungen&quot;.
* Wenn der SMS-Prozess nach dem Neustart den MT-Versand für einen kurzen Zeitraum wieder funktionsfähig macht, haben Sie wahrscheinlich eine Drosselung aufgrund einer instabilen Verbindung. Siehe oben den Abschnitt &quot;Problem mit instabilen Verbindungen&quot;.
* Überprüfen Sie, ob das Broadlog vorhanden ist und den richtigen Status mit den richtigen Daten aufweist. Ist dies nicht der Fall, handelt es sich nicht um ein SMS-Problem, sondern um ein Versandproblem oder ein Problem bei der Versandvorbereitung (das liegt außerhalb des Anwendungsbereichs dieses Dokuments).
* Prüfen Sie, ob der SMS-Connector tatsächlich mit den Geräten des Providers verbunden ist. Bitten Sie den Provider um Rückmeldung, um sicherzustellen, dass alle Systeme richtig kommunizieren. Informationen zum Bindungsprozess finden Sie unter BIND_TRANSMITTER und BIND_TRANSCEIVER PDUs . Möglicherweise müssen Sie SMPP-Traces aktivieren, um eine ordnungsgemäße Fehlerbehebung zu ermöglichen.
* Überprüfen Sie bei aktivierten SMPP-Traces, ob die SUBMIT_SM-PDU die richtigen Informationen enthält (siehe die Dokumentation oben).
* Überprüfen Sie, ob der Provider mit einer SUBMIT_SM_RESP PDU mit dem Wert &quot;OK&quot; (Code 0) antwortet. Stellen Sie sicher, dass die PDU mit einer angemessenen Verzögerung eintrifft: Alles, was länger als 1 Sekunde ist, ist misstrauisch und muss mit dem Provider besprochen werden. Normalerweise kommt sie in weniger als 100 ms an.
* Wenn alle diese Schritte funktionieren, können Sie sicher sein, dass das Problem auf der Seite des Providers liegt. Er muss dann die Fehlersuche auf seiner Plattform durchführen.
* Wenn es funktioniert, der Durchsatz jedoch inkonsistent ist, versuchen Sie, das Übertragungsfenster anzupassen und den MT-Durchsatz zu verringern. Für diese Anpassung müssen Sie mit dem Provider zusammenarbeiten. Campaign kann Nachrichten sehr schnell senden, sodass Leistungsprobleme auf den Geräten des Providers auftreten können.

#### MT wird dupliziert (dieselbe SMS wird mehrmals hintereinander gesendet)

Duplikate werden häufig durch Wiederholungsversuche verursacht. Es ist normal, dass beim Wiederholen von Nachrichten Duplikate auftreten. Konzentrieren Sie sich also auf die Eliminierung der eigentlichen Ursache für weitere Zustellversuche.

* Wenn Sie sehen, dass Duplikate im Abstand von genau 60 Sekunden gesendet werden (oder ein anderer verdächtig &quot;regulärer&quot;Zeitraum), ist dies wahrscheinlich ein Problem auf der Provider-Seite, da sie SUBMIT_SM_RESP nicht schnell genug senden.
* Wenn Sie viele BIND/UNBIND sehen, haben Sie eine instabile Verbindung: Lesen Sie den Abschnitt [Probleme mit instabilen Verbindungen](#unstable-connections) für Lösungen, bevor Sie versuchen, Probleme mit doppelten Nachrichten zu lösen.
* Vergewissern Sie sich, dass alle SUBMIT_SM PDUs kurz danach die entsprechenden SUBMIT_SM_RESP aufweisen. Wenn dies nicht der Fall ist oder SUBMIT_SM_RESP zu langsam ist, liegt das Problem auf der Seite des Providers.

Verringerung der Anzahl von Duplikaten bei einem erneuten Versuch:

* Reduzieren Sie das *Übertragungsfenster*. Das Übertragungsfenster sollte groß genug sein, um die Latenz von SUBMIT_SM_RESP abzudecken, aber nicht zu groß. Sein Wert stellt die maximale Anzahl von Nachrichten dar, die dupliziert werden können, wenn ein Fehler auftritt, während das Fenster voll ist.

#### Problem bei der Verarbeitung von SR (Empfangsbestätigungen)

* Sie müssen SMPP-Traces aktivieren, um jegliche Art von SR-Fehlerbehebung durchzuführen.
* Überprüfen Sie, ob die DELIVER_SM-PDU vom Provider stammt und korrekt formatiert ist.
* Überprüfen Sie, ob Campaign rechtzeitig mit einer erfolgreichen DELIVER_SM_RESP-PDU antwortet. Dadurch wird sichergestellt, dass der SR zur verzögerten Verarbeitung durch den SMS-Prozess in die Tabelle providerMsgStatus eingefügt wurde.

Wenn die DELIVER_SM-PDU nicht erfolgreich quittiert wurde, müssen Sie einige Punkte überprüfen:

* Überprüfen Sie den Regex im Zusammenhang mit der ID-Extraktion und der Fehlerverarbeitung im externen Konto. Möglicherweise müssen Sie sie anhand des Inhalts der DELIVER_SM-PDU überprüfen.
* Überprüfen Sie, ob die Fehler ordnungsgemäß in der Tabelle broadLogMsg bereitgestellt wurden (in der Campaign-Dokumentation wird dies im Detail erläutert).

Wenn die DELIVER_SM-PDU vom erweiterten ACC-SMPP-Connector quittiert wurde, das broadLog jedoch nicht ordnungsgemäß aktualisiert wird, überprüfen Sie den im Abschnitt Abgleichen von MT-, SR- und broadLog-Einträgen oben beschriebenen Prozess zur ID-Abstimmung.

Wenn Sie alle Probleme behoben haben, die Puffer des Providers jedoch noch einige ungültige SR enthalten, können Sie diese mit der Option &quot;Zählung der &#39;ungültige ID&#39; Antworten&quot; überspringen. Dies sollte mit Vorsicht verwendet und so schnell wie möglich auf 0 zurückgesetzt werden, nachdem die Puffer bereinigt wurden.

Wenn die SR-Verarbeitung langsam ist, versuchen Sie, die häufigsten Statusmeldungen in der BroadLogMsg-Tabelle zu qualifizieren.

Wenn nur einige SR empfangen werden, aber nicht alle, stellen Sie sicher, dass kein anderes System eine Verbindung zum Konto Ihres Providers herstellt, z. B. ein Testsystem. SR können bei jeder Verbindung weitergeleitet werden, sodass einige von ihnen an dieses andere System weitergeleitet werden können. Der Provider kann Ihnen dabei helfen, herauszufinden, wo sich dieses andere System befindet, das mit dem Konto verbunden ist.

#### Problem bei der Verarbeitung von MO (und Quarantäne/automatische Antwort)

* Aktivieren Sie SMPP-Traces während der Tests. Wenn Sie TLS nicht aktivieren, sollten Sie bei der Fehlerbehebung bei MO immer eine Netzwerkaufzeichnung durchführen, um zu überprüfen, ob die PDUs die richtigen Informationen enthalten und korrekt formatiert sind.
* Achten Sie bei der Erfassung von Netzwerk-Traffic oder der Analyse von SMPP-Traces darauf, die gesamte Konversation mit dem MO und dessen Antwort-MT zu erfassen (wenn eine Antwort konfiguriert ist).
* Wenn die MO (DELIVER_SM PDU) nicht in den Traces angezeigt wird, können Sie sicher sein, dass das Problem auf der Seite des Providers liegt. Er muss dann die Fehlersuche auf seiner Plattform durchführen.
* Wenn die DELIVER_SM PDU angezeigt wird, überprüfen Sie, ob sie von Campaign mit einer erfolgreichen DELIVER_SM_RESP PDU (Code 0) quittiert wird. Diese RESP garantiert, dass die gesamte Verarbeitungslogik von Campaign angewendet wurde (automatische Antwort und Quarantäne). Wenn dies nicht der Fall ist, überprüfen Sie die Logs des SMS-Prozesses auf eine Fehlermeldung.
* Wenn automatische Antworten aktiviert sind, überprüfen Sie, ob SUBMIT_SM an den Provider gesendet wurde. Ist das nicht der Fall, können Sie davon ausgehen, dass die Logs des SMS-Prozesses eine Fehlermeldung enthalten.
* Wenn die SUBMIT_SM MT PDU, die die Antwort enthält, in den Traces gefunden wird, aber die SMS nicht auf das Mobiltelefon gelangt, müssen Sie sich an den Provider wenden, um Unterstützung bei der Fehlerbehebung zu erhalten, da das Problem wahrscheinlich auf ihrer Seite liegt.

#### Problem bei der Versandvorbereitung, die Empfänger unter Quarantäne nicht ausschließt (durch die automatische Antwortfunktion in Quarantäne gestellt)

* Überprüfen Sie, ob die Telefonnummern in der Quarantänetabelle und im Versand-Log im exakt gleichen Format vorliegen. Ist dies nicht der Fall, lesen Sie die obige Einstellung &quot;Vollständige Telefonnummer senden&quot;, wenn Sie Probleme mit dem Pluszeichen des internationalen Telefonnummernformats haben.
* Kurzwahlnummern überprüfen: Ausnahmen treten auf, wenn die Kurzwahlnummer des Empfängers entweder mit der im externen Konto definierten identisch ist oder leer ist (leer = beliebige Kurzwahlnummer). Wenn nur eine Kurzwahlnummer für die gesamte Campaign-Instanz verwendet wird, ist es einfacher, alle Felder mit Kurzwahlnummer leer zu lassen.

#### Kodierungsprobleme  {#sms-encoding-issues}

Kodierungsprobleme treten häufig in SMS auf. Im Folgenden finden Sie einige grundlegende Schritte.

**Schritt 1: Kontaktaufnahme mit dem Provider**

Der Provider ist der Experte, der weiß, wie SMS funktioniert. Kontaktieren Sie sie und sehen Sie mit ihnen, was falsch ist. Sie sollten Ihnen mitteilen können, ob das Problem auf ihrer Seite oder in Campaign liegt. Wenn das Problem in Campaign auftritt, sollte es Ihnen genau sagen können, welches Feld falsch ist, was sehr hilfreich ist.

**Schritt 2: Inhalt Ihrer Nachricht überprüfen**

Du musst wissen, was in deiner Nachricht ist. Dieser Satz mag leicht klingen, aber er ist es nicht. Unicode ermöglicht so viele Varianten für ähnliche Zeichen, dass Campaign sie nicht alle verarbeiten kann.

Die häufigste Ursache für Probleme ist das Kopieren und Einfügen aus einem Textverarbeitungsprogramm, das übliche Zeichen in typografisch korrekte Versionen ändert: Leerzeichen in feste Leerzeichen, doppelte Anführungszeichen in öffnende und schließende Anführungszeichen, Minuszeichen in verschiedene Arten von Bindestrichen ...

Kopieren Sie Ihre Nachricht beim Testen nicht, sondern geben Sie sie immer direkt in die Benutzeroberfläche ein.

**Nicht durch Hexadezimalwert** einschüchtern lassen. Hexadezimal sieht seltsam und unnatürlich aus, hat aber eine sehr deutliche Qualität: Man kann den Unterschied zwischen ähnlichen Zeichen erkennen. Ein Kleinbuchstabe L, ein Großbuchstabe I, O, 0, alle verschiedenen Arten von Anführungszeichen, nicht-lateinische Kodierungen oder sogar verschiedene Arten von Leerzeichen können alle gleich aussehen (oder überhaupt nicht angezeigt werden). Hexadezimal zeigt alles und hilft beim Vergleichen von Dingen.

Um Unicode in Hexadezimalcode zu konvertieren, können Sie Online-Tools verwenden.

**Beim Öffnen von Tickets** über Kodierungsprobleme, ob mit dem Provider oder der Campaign-Unterstützung, enthält **eine hexadezimale**-Version dessen, was Sie eingeben und was Sie sehen.

**Schritt 3: Überprüfen, was Sie senden sollten**

Legen Sie die Kodierung fest, die Sie voraussichtlich verwenden werden, und suchen Sie online nach der Zeichentabelle. Vergewissern Sie sich, dass die Zeichen, die Sie senden möchten, tatsächlich in dieser Zeichenumsetztabelle verfügbar sind. Überprüfen Sie, ob das Feld data_coding korrekt ist und mit dem übereinstimmt, was Sie und der Provider erwarten.

**Schritt 4: Überprüfen, was Sie tatsächlich gesendet haben**

Sie benötigen die Debug-Ausgabe des Connectors, um genau zu sehen, welche Bytes Sie an den Provider senden. Kodierungsprobleme treten in SUBMIT_SM PDUs auf. Erfassen Sie sie daher unbedingt. Senden Sie gut erkennbare Nachrichten, die im Log leicht zu finden sind.

Zögern Sie nicht, beim Testen verschiedene Sonderzeichen zu senden. Beispielsweise verfügt die GSM7-Kodierung über erweiterte Zeichen, die sich in ihrer hexadezimalen Form sehr unterscheiden, sodass sie leicht zu erkennen sind, da sie in keiner anderen Kodierung vorkommen.

#### Leistungsprobleme {#sms-performance-issues}

>[!NOTE]
>
>Leistung ist ein sehr breites Thema. In diesem Abschnitt finden Sie einige grundlegende Prüfungen, die durchgeführt werden müssen, bevor Sie versuchen, andere große Projekte zu skalieren oder durchzuführen.

**Leistungsprobleme beim Senden von MT**

* Überprüfen Sie, ob alle Einstellungen im Abschnitt Durchsatz und Verzögerungen des externen Kontos korrekt sind und mit den vom Provider zulässigen Einstellungen übereinstimmen.
* Vergewissern Sie sich, dass keine weiteren Zustellversuche unternommen werden.
* Vergewissern Sie sich, dass die Infrastruktur des Providers nicht ausgelastet ist. Suchen Sie in den RESP-PDUs nach RMSGQFUL- oder RTHROTTLED-Fehlern.
* Überprüfen Sie die serverConf-Einstellungen. Beginnen Sie mit den Standardwerten und erhöhen Sie die Parameter langsam und einzeln.
* Vergewissern Sie sich, dass der SMS-Prozess beim Laden nicht immer neu gestartet wird. Ist dies der Fall, müssen Sie möglicherweise *maxSMSMemoryMb*, *maxProcessMemoryAlertMb* und *maxProcessMemoryWarningMb* in der Datei serverConf erhöhen.

**Leistungsprobleme beim Empfang von SR**

Wenn der Provider sich über eine Pufferüberlastung auf seiner Seite beschwert, liegt dies möglicherweise daran, dass Campaign keine SR schnell genug erhält.

* Vergewissern Sie sich, dass die Instanzdatenbank nicht überlastet ist. Die SR-Verarbeitung hängt stark von der Datenbankleistung ab.
* Bitten Sie den Provider, das Übertragungsfenster für DELIVER_SM auf seiner Seite zu vergrößern. Idealerweise sollte sie so groß sein wie die Einstellung *batchUpdateSize* in serverConf.

### Elemente, die bei der Kommunikation über ein SMS-Problem berücksichtigt werden müssen

Wenn Sie Unterstützung bei einem SMS-Problem anfordern (unabhängig davon, ob ein Support-Ticket für Adobe Campaign, den SMS-Provider oder eine Art Kommunikation zu diesem Problem geöffnet wird), müssen Sie mindestens die folgenden Informationen angeben, um sicherzustellen, dass es ordnungsgemäß qualifiziert wird. Richtig qualifizierte Probleme sind der Schlüssel zur schnelleren Lösung von Problemen, sodass ein wenig mehr Zeit benötigt wird, um die Situation zu verstehen und sinnvolle Informationen zu geben, zu einem gigantischen Effizienzsprung führt.

* Aktivieren Sie ausführliche SMPP-Nachrichten während der Zeit, in der das Problem auftritt. Die meisten SMS-Probleme lassen sich ohne diese Probleme praktisch nicht lösen.
* Wenn das Problem mit dem SMS-Traffic zusammenhängt, wenden Sie sich zuerst an den Provider. Sie sind am besten geeignet und ihre Plattform ist in der Regel für eine effiziente Diagnose von SMS-Traffic-Problemen in Echtzeit geeignet.
* Fügen Sie eine kurze, sachliche Beschreibung des Problems bei.
* Fügen Sie eine Beschreibung des erwarteten Ergebnisses bei.
* Schließen Sie alle Feedbacks des Providers ein.
* Fügen Sie relevante Logs und/oder Netzwerkaufzeichnungen bei. Achten Sie bei der Aufnahme darauf, das Problem während der Erfassung zu reproduzieren, da es sonst nutzlos sein wird.
* Wenn Sie Protokolle, Traces oder Captures einschließen, bestimmen Sie den genauen Speicherort in der Datei, an dem das Problem auftritt, sowie den genauen Speicherort eines funktionierenden Beispiels, falls vorhanden. Aufnahmen oder Spuren können groß und mühsam sein, sich anzuschauen, sodass alles, was dabei hilft, Informationen in ihnen zu finden, hilfreich ist.
* Wenn Sie auf Nachrichten, PDUs oder Protokolle verweisen, geben Sie deren Zeitstempel klar an, damit sie von anderen Personen leicht zu finden sind.
* Versuchen Sie, das Problem in einer Testumgebung zu reproduzieren. Wenn Sie sich bei einer Einstellung nicht sicher sind, versuchen Sie sie in der Testumgebung und überprüfen Sie das Ergebnis mit SMPP-Traces. In der Regel ist es besser, in Testumgebungen replizierte Probleme zu melden, als Probleme in Produktionsumgebungen direkt zu melden.
* Schließen Sie alle Änderungen oder Änderungen ein, die auf der Plattform vorgenommen wurden: selbst eine kleine Änderung kann enorme Auswirkungen haben. Schließen Sie auch alle Änderungen ein, die der Provider möglicherweise auf seiner Seite vorgenommen hat.

#### Wann ist eine Netzwerkaufzeichnung nützlich?

Eine Netzwerkaufzeichnung ist nicht immer erforderlich. Sehr oft reichen ausführliche SMPP-Meldungen aus. Im Folgenden finden Sie einige Richtlinien, anhand derer Sie feststellen können, ob die Netzwerkaufzeichnung den Aufwand wert ist:

* Verbindungsprobleme, aber in den ausführlichen Meldungen wird keine BIND_RESP PDU angezeigt.
* Ungeklärte Verbindungsabbrüche ohne Fehlermeldung (d. h. das Verhalten des Connectors bei der Erkennung eines Protokollfehlers niedriger Ebene).
* Der Provider beschwert sich über den Prozess der Aufhebung der Bindung/Trennung.
* Es gibt Kodierungsprobleme in optionalen TLV-Feldern.
* Es wird vermutet, dass der Traffic zwischen verschiedenen Verbindungen vermischt ist.

Versuchen Sie in allen anderen Situationen, zuerst ausführliche SMPP-Meldungen zu analysieren, und fordern Sie nur dann eine Netzwerkaufzeichnung an, wenn klar ist, dass Informationen in den ausführlichen Logs fehlen.

#### Wann ist eine Netzwerkaufzeichnung nutzlos?

In einigen Fällen ist die Erfassung von Netzwerk-Traffic nutzlos oder nur Zeitverschwendung. Die häufigsten Situationen sind:

* TLS aktiviert: Der TLS-Traffic ist von vornherein verschlüsselt, sodass er nicht aufgezeichnet werden kann.
* Performance-Probleme: Die Logs enthalten alle erforderlichen Informationen zum Verfolgen von Performance-Problemen.
* Timing-Probleme (Wiederholungszeitpunkt, Zeitraum inquire_link, Durchsatzbegrenzung usw.)
* SR-Analyse und -Verarbeitung: Ausführliche Logs bieten viel mehr Kontext und eine bessere Darstellung.
* MO-Verarbeitung (automatische Antworten, Quarantäne).
* Fehler ohne tatsächlichen SMPP-Traffic: Versandvorbereitung, Message Center-API-Probleme, Workflow-Probleme, ...
