---
title: Versionshinweise 2022 zu Campaign v8
description: Liste der Funktionen und Verbesserungen in Campaign v8-Versionen 2022
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
source-git-commit: e7f4982a9b13fe5413b6cce0a1cc58e2b3a6afa4
workflow-type: tm+mt
source-wordcount: '1845'
ht-degree: 100%

---

# Versionshinweise 2022{#2022-rn}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der **Campaign v8-Versionen 2022** aufgelistet.

## Version 8.4.2 {#release-8-4-2}

_28. Oktober 2022_

**Verbesserungen**

* Fehlerkorrektur – Der Indikator „Erfolg Auslieferungsrate“ wird jetzt korrekt aktualisiert, wenn Adobe Campaign Enhanced MTA verwendet wird. (NEO-50462)

## Version 8.4.1 {#release-8-4-1}

_30. September 2022_

**Neue Funktionen**

<table> 
<thead>
<tr> 
<th> <strong>Integration von Adobe Campaign mit Adobe Experience Platform</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Neue Ziel- und Quell-Connectoren sind jetzt verfügbar, um eine nahtlose Integration zwischen Adobe Campaign und Adobe Experience Platform zu ermöglichen:</p>
<ul><li>Verwenden Sie den Ziel-Connector von Adobe Campaign Managed Cloud, um Experience Platform-Segmente zur Aktivierung an Adobe Campaign zu senden.</li>
<li>Verwenden Sie den Quell-Connector von Adobe Campaign Managed Cloud, um die Versand- und Trackinglogs von Adobe Campaign an Adobe Experience Platform zu senden.</li>
</ul>
<p>Weitere Informationen finden Sie in der <a href="../connect/ac-aep.md">entsprechenden Dokumentation</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Verfügbarkeit des Twitter-Kanals</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Der <a href="../send/twitter.md">Twitter-Kanal</a> ist jetzt in Campaign v8 verfügbar. Sie haben folgende Möglichkeiten:</p>
<ul> 
<li><p>Nachrichten auf Twitter senden: Mit Adobe Campaign können Sie Nachrichten direkt in Ihrem Twitter-Konto posten. Sie können auch Direktnachrichten an all Ihre Follower senden.
</p></li>
<li><p>Neue Kontakte erfassen: Adobe Campaign kann automatisch Profildaten erfassen, sodass Sie Zielgruppen-Kampagnen durchführen und Cross-Channel-Strategien umsetzen können.
</p></li>
</ul>
<p>In der <a href="../connect/ac-tw.md">entsprechenden Dokumentation</a> erfahren Sie, wie Sie Campaign und Twitter miteinander verbinden.</p>
<p>Auf <a href="../connect/ac-tw.md">dieser Seite</a> erfahren Sie, wie Sie mit Campaign Tweets posten und Direktnachrichten versenden können.</p>
</td> 
</tr> 
</tbody> 
</table>

**Sicherheitsverbesserung**

Um die Sicherheit zu optimieren, wurden Sicherheits-Token aus den von Campaign generierten URLs entfernt:

* Diese Änderung gilt nur für GET-URLs. Andere Typen, einschließlich POST-URLs, sind davon nicht betroffen.
* Wenn Sie benutzerdefinierten Code verwenden, werden keine Sicherheits-Token mehr aus dem GET-URL-Sicherheits-Token-Parameter abgerufen. Sie müssen ein neues Sicherheits-Token mit folgendem JSSP-Code generieren:

   ```getNewSecurityToken(jsspContext.getSessionToken(), jsspContext.getSecurityToken(), true);```

   Sie können auch die Anmelde-API verwenden, um Sicherheits-Token abzurufen.
* Bei der Verwaltung von Sitzungs-Tokens gibt es keine Änderungen.

**Verbesserungen**

* Nach dem Auslaufen von Microsoft Internet Explorer 11 verwendet die HTML-Rendering-Engine in der Konsole nun **Microsoft Edge Chromium**. Außerdem ist die Installation der **Microsoft Edge WebView 2**-Laufzeitumgebung jetzt für jede Client-Konsolen-Installation erforderlich.
* Die Ausführung des Workflows wurde durch Workflow-Hochverfügbarkeit verbessert, sodass Sie Workflows gleichzeitig in verschiedenen Containern ausführen können, um den Verlust des Workflow-Service zu verhindern und damit verbundene Ausführungsfehler zu vermeiden. **Hinweis**: Diese neue Funktion steht nur einer begrenzten Anzahl von Kunden zur Verfügung.
* Datenschutzanfragen werden jetzt im Batch-Modus für einen bestimmten Datenschutz-Namespace ausgeführt. Durch diese Verbesserung wird die Ausführungszeit für DSGVO-/Datenschutz-Löschanfragen verkürzt.

**Aktualisierungen zur Kompatibilität**

* Das Campaign v8-SDK unterstützt jetzt iOS 16 für Push-Benachrichtigungen.

Weitere Informationen finden Sie in der [Kompatibilitätsmatrix für Campaign](compatibility-matrix.md).

**Patches**

* Es wurde ein Problem behoben, das sich auf die Statusaktualisierungen des Versandlogs auf der MID-Instanz auswirkte, wenn die Option &quot;FeatureFlag_GZIP_Compression&quot; aktiviert war. (NEO-49183)
* Es wurde ein Problem behoben, das dazu führen konnte, dass Sendungen im Status **Ausstehend** blieben, auch wenn das Kontaktdatum erreicht war. (NEO-48079)
* Es wurde ein Problem in Workflows behoben, das dazu führen konnte, dass Dateien auf dem Server nicht aktualisiert wurden, wenn die Aktivität **Laden (Datei)** verwendet wurde. Der Prozess wurde bei 100 % angehalten, aber nie beendet. (NEO-47269)
* Fehlerkorrektur – Jetzt tritt kein Problem mehr während des Postupgrades in japanischen Umgebungen auf. (NEO-46640)
* Es wurde ein Problem behoben, das auftreten konnte, wenn ein Versand während des MTA-Prozesses eine bestimmte Größe erreichte. (NEO-46097)
* Es wurde ein Problem behoben, das verhinderte, dass Trackinglogs Daten über den Browser des Empfängers zurückgaben. (NEO-46612)
* Es wurde ein Problem behoben, das zu Personalisierungsproblemen beim Versand von SMS-Nachrichten über einen externen Versandmodus führte. (NEO-46415)
* Es wurde ein Problem behoben, das zu Duplikaten in Trackinglogs führen konnte. (NEO-46409)
* Es wurde ein Problem behoben, das verhinderte, dass der technische Workflow **[!UICONTROL Staging-Daten replizieren]** (ffdaReplicateStagingData) gestoppt wurde, selbst wenn während seiner Ausführung ein Fehler auftrat. (NEO-46280)
* Um einen zu langsamen Testversand an Testadressen zu verhindern, werden nun alle aufeinanderfolgenden Replikationen von Testempfängern und -empfängerinnen zu einer einzigen Replikationsanfrage zusammengefasst. (NEO-44844)
* Es wurde ein Problem behoben, bei dem ein Fehler angezeigt wurde, wenn die Vorschau eines Versands in einem archivierten Ereignis des Message Centers aufgerufen wurde. (NEO-43620)
* Es wurde ein Problem behoben, das bei der Eingabe von Daten in die Snowflake-Cloud-Datenbank mithilfe der Campaign-Aktivität **Abfrage** und **Datenquelle ändern** auftrat: Der Prozess schlug fehl, wenn ein umgekehrter Schrägstrich in den Daten vorhanden war. Die Quellzeichenfolge wurde nicht escaped, wodurch die Daten von Snowflake nicht korrekt verarbeitet wurden. (NEO-45549)
* Es wurde ein Problem bei der Verwendung der **Abfrage**-Aktivität und der Filterung einer Tabelle behoben. Wenn ein Spaltenname das Wort &quot;Update&quot; enthielt, kam es zu einem Kompilierungsfehler mit einer ungültigen Kennung und folgender Meldung: &quot;Anzahl der Zeilen aktualisiert&quot;. (NEO-46485)
* Der technische Workflow **Datenbankbereinigung** kann jetzt auch für benutzerdefinierte Staging-Schemata verwendet werden. (NEO-48974)
* Fehlerkorrektur – Die Versandanalyse ist jetzt während des Ausschlusses von auf die Blockierungsliste gesetzten Empfängern nicht mehr verlangsamt, wenn die Zielgruppe aus einer großen Mengen von Empfängern besteht. (NEO-48019)
* Die Stabilität bei der Verarbeitung ungültiger XML-Zeichenfolgen während SOAP-Aufrufen wurde verbessert. (NEO-48027)
* Fehlerkorrektur – Jetzt werden keine unnötigen Versandkontingente mehr erstellt, wenn für den Versand Kalender- und Aufspaltungsmodi verwendet werden. (NEO-48634)
* Es wurde ein Leistungsproblem bei der Verwendung von auf Kalendern basierenden Schüben behoben. (NEO-48451)
* Fehlerkorrektur – Im Bildschirm der Versandliste wird jetzt nach der Erstellung eines neuen Zielgruppen-Mappings für ein benutzerdefiniertes Schema keine Fehlermeldung mehr angezeigt. (NEO-49237)
* Fehlerkorrektur – Jetzt gehen keine Daten mehr verloren, wenn der Staging-Workflow fehlerhaft ist und die Aufbewahrungsfrist vollständig abgelaufen ist. (NEO-48975)

## Version 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> Die Aktualisierung der Client-Konsole ist obligatorisch. Auf dieser [Seite](../start/connect.md#download-ac-console) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.

_7. Oktober 2022_

**Verbesserungen**

* Es wurde ein Problem behoben, das sich auf die Statusaktualisierungen des Versandlogs auf der MID-Instanz auswirkte, wenn die Option &quot;FeatureFlag_GZIP_Compression&quot; aktiviert war. (NEO-49183)
* Der technische Workflow **Datenbankbereinigung** kann jetzt auch für benutzerdefinierte Staging-Schemata verwendet werden. (NEO-48974)
* Fehlerkorrektur – Sendungen bleiben jetzt nicht mehr im Status **Ausstehend**, wenn das Kontaktdatum erreicht ist. (NEO-48079, NEO-48251)
* Die Stabilität bei der Verarbeitung ungültiger XML-Zeichenfolgen während SOAP-Aufrufen wurde verbessert. (NEO-48027)
* Fehlerkorrektur – Die Versandanalyse ist jetzt während des Ausschlusses von auf die Blockierungsliste gesetzten Empfängern nicht mehr verlangsamt, wenn die Zielgruppe aus einer großen Mengen von Empfängern besteht. (NEO-48019)
* Um einen zu langsamen Testversand an Testadressen zu verhindern, werden nun alle aufeinanderfolgenden Replikationen von Testempfängern und -empfängerinnen zu einer einzigen Replikationsanfrage zusammengefasst. (NEO-44844)
* Es wurde ein Problem behoben, das zu Personalisierungsproblemen beim Versand von SMS-Nachrichten über einen externen Versandmodus führte. (NEO-46415)
* Es wurde ein Problem behoben, bei dem ein Fehler angezeigt wurde, wenn die Vorschau eines Versands in einem archivierten Ereignis des Message Centers aufgerufen wurde. (NEO-43620)
* Es wurde ein Problem in Workflows behoben, das dazu führen konnte, dass Dateien auf dem Server nicht aktualisiert wurden, wenn die Aktivität **Laden (Datei)** verwendet wurde. Der Prozess wurde bei 100 % angehalten, aber nie beendet. (NEO-47269)
* Fehlerkorrektur – Jetzt werden keine unnötigen Versandkontingente mehr erstellt, wenn für den Versand Kalender- und Aufspaltungsmodi verwendet werden. (NEO-48634)
* Es wurde ein Leistungsproblem bei der Verwendung von auf Kalendern basierenden Schüben behoben. (NEO-48451)
* Fehlerkorrektur – Im Bildschirm der Versandliste wird jetzt nach der Erstellung eines neuen Zielgruppen-Mappings für ein benutzerdefiniertes Schema keine Fehlermeldung mehr angezeigt. (NEO-49237)
* Fehlerkorrektur – Jetzt tritt kein Problem mehr auf, wenn ein Versand während des MTA-Prozesses eine bestimmte Größe erreicht. (NEO-46097)
* Es wurde ein Problem behoben, das verhinderte, dass Trackinglogs Daten über den Browser des Empfängers zurückgaben. (NEO-46612)
* Fehlerkorrektur – Jetzt tritt kein Problem mehr während des Postupgrades in japanischen Umgebungen auf. (NEO-46640)
* Fehlerkorrektur – Jetzt tritt kein Problem mehr bei der Verwendung der **Abfrage**-Aktivität und der Filterung einer Tabelle auf. Wenn ein Spaltenname das Wort &quot;Update&quot; enthielt, kam es zu einem Kompilierungsfehler mit einer ungültigen Kennung und folgender Meldung: &quot;Anzahl der Zeilen aktualisiert&quot;. (NEO-46485)
* Es wurde ein Problem behoben, das verhinderte, dass der technische Workflow **[!UICONTROL Staging-Daten replizieren]** (ffdaReplicateStagingData) gestoppt wurde, selbst wenn während seiner Ausführung ein Fehler auftrat. (NEO-46280)
* Fehlerkorrektur – Jetzt gehen keine Daten mehr verloren, wenn der Staging-Workflow fehlerhaft ist und die Aufbewahrungsfrist vollständig abgelaufen ist. (NEO-48975)
* Es wurde ein Problem behoben, das bei der Eingabe von Daten in die Snowflake-Cloud-Datenbank mithilfe der Campaign-Aktivität **Abfrage** und **Datenquelle ändern** auftrat: Der Prozess schlug fehl, wenn ein umgekehrter Schrägstrich in den Daten vorhanden war. Die Quellzeichenfolge wurde nicht escaped, wodurch die Daten von Snowflake nicht korrekt verarbeitet wurden. (NEO-45549)

## Version 8.3.8 {#release-8-3-8}

_18. Mai 2022_

**Neue Funktionen**

<table> 
<thead>
<tr> 
<th> <strong>Zeitkritische Benachrichtigungen</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>In iOS 15 fügte Apple das Konzept der „Dringlichen Mitteilungen“ hinzu, das dem App-Entwickler die Möglichkeit gibt, den Fokusmodus zu umgehen, wenn eine Benachrichtigung als dringlich eingestuft wird und den Benutzer in Echtzeit erreichen muss.</p>
<p>Weitere Informationen finden Sie in der <a href="../send/push.md#send-notifications-on-ios">entsprechenden Dokumentation</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Integration des Core Privacy Service</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Campaign v8 ist jetzt mit dem Adobe Privacy Core Service integriert. Die von Privacy Core Service an alle Experience Cloud-Lösungen übertragenen Datenschutzanfragen werden von Campaign mithilfe eines speziellen Workflows automatisch verarbeitet.</p>
<p>Weitere Informationen finden Sie in der <a href="privacy.md">entsprechenden Dokumentation</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table>
<thead>
<tr>
<th><strong>Reaktionsverwaltung</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Mit Campaign Response Management können Sie den Erfolg und den ROI Ihrer Marketing-Kampagnen oder Angebotsvorschläge über alle Kanäle hinweg messen: E-Mail, Mobile, Briefpost usw.</p>
<p>Weitere Informationen finden Sie in der <a href="../start/campaigns.md#response-manager-add-on">entsprechenden Dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Distributed Marketing</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Das verteilte Marketing in Campaign ermöglicht die Implementierung kollaborativer Kampagnen zwischen zentralen Entitäten (Hauptsitz, Marketing-Abteilungen usw.) und lokalen Stellen (Verkaufsstellen, regionale Agenturen usw.). Über einen freigegebenen Arbeitsbereich (Kampagnenkits) können Sie Kampagnenvorlagen erstellen und diese Ihren lokalen Entitäten vorschlagen.</p>
<p>Weitere Informationen finden Sie in der <a href="../start/campaigns.md#distributed-marketing-add-on">entsprechenden Dokumentation</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Aktualisierungen zur Kompatibilität**

* Das Campaign v8-SDK unterstützt jetzt Android 12 und iOS 15 für Push-Benachrichtigungen.
* Campaign v8 ist jetzt mit Windows 11 kompatibel.

Weitere Informationen finden Sie in der [Kompatibilitätsmatrix für Campaign](compatibility-matrix.md).

**Verbesserungen**

* Die Microsoft Exchange Online OAuth 2.0-Authentifizierung für POP3 wird jetzt in Campaign unterstützt. [Mehr dazu](../config/external-accounts.md#bounce-mails-external-account)
* Es wurden kritische Fehlerbehebungen bei der Web-API des Microsoft Dynamics-Connectors vorgenommen.
* Das neue Schreibrecht für Benutzer- und Gruppenschemas (operatorWrite) wurde hinzugefügt, um Benutzern das Einfügen, Aktualisieren und Löschen von Benutzer- (xtk:operator) und Benutzergruppen- (xtk:group)-Schemata zu ermöglichen.

<!--* You can now enable the Email BCC (blind carbon copy) capability to store emails sent by Campaign at the delivery level, through the dedicated option in the delivery properties. [Read more](../config/email-settings.md#email-bcc)-->
<!--* To ensure better performances, a new "Split" option is now activated by default in the Routing external account. This option allows messages to be automatically split across your mid-sourcing instances in order to be delivered faster to the recipients.-->
* Mehrere aktive LINE-Konten können jetzt auf einer einzigen Mid-Sourcing-Lösung konfiguriert werden.
* Die Anzahl der Standardverbindungen für den Webprozess wurde von 50 auf 150 erhöht.
* Campaign verfügt über eine Reihe neuer Schutzmechanismen, um das Einfügen duplizierter Schlüssel in eine Snowflake-Datenbank zu verhindern. [Mehr dazu](../architecture/keys.md)

**Patches**

* Fehlerkorrektur: Bei der Verwendung von Testadressen und Kontrollgruppen im selben wiederkehrenden Versand tritt jetzt kein Fehler mehr auf. (NEO-41197)
* Fehlerkorrektur: Bei FFDA wird der E-Mail-Versand für alle Empfänger, die zum selben deliveryPart gehören, während des Sendevorgangs (bis zu 256) nicht mehr blockiert, wenn Personalisierungsblöcke eines der folgenden Zeichen enthalten: `' & < > "`. Diese Zeichen werden jetzt in Personalisierungsblöcken unterstützt (Beispiel: firstname=&quot;Brian O&#39;Neil&quot;). (NEO-43184)
* Fehlerkorrektur: Jetzt schlägt der Tracking-Workflow bei der Verwendung eines benutzerdefinierten Schemas als Zielgruppen-Mapping nicht mehr fehl. Beim Generieren des broadLog-Schemas über den Zielgruppen-Mapping-Assistenten stellen wir nun sicher, dass der Typ des Fremdlinks zu einem benutzerdefinierten Zielgruppenschema korrekt ist. (NEO-43506)
* Fehlerkorrektur: Die FFDA-Implementierungs-Workflows schlagen jetzt in anderen Sprachen als Englisch nicht mehr fehl. (NEO-44561)

## Version 8.2.10 {#release-8-2-10}

_2. Februar 2022_

**Patches**

* Fehlerkorrektur – Die Versandvorbereitung schlägt jetzt nicht mehr fehl, wenn die in der Typologieregel definierte maximale Nachrichtenanzahl erreicht ist.
* Fehlerkorrektur – Bei der Konfiguration des Adobe Analytics-Connectors tritt jetzt kein Fehler mehr auf, wenn die E-Mail-Adresse das Zeichen &quot;s&quot; enthält.
* Fehlerkorrektur – Die deliveryMapping-Tabelle verliert jetzt nicht mehr Daten aus einem benutzerdefinierten Versand-Mapping.
* Fehlerkorrektur – Empfänger erhalten jetzt nicht mehr dieselbe Nachricht für denselben Versand mehrmals, wenn die E-Mail-Adresse ein einzelnes Anführungszeichen (&#39;) enthält. Dieses Zeichen ist jetzt mit Escape-Zeichen versehen. (NEO-41198)
* Fehlerkorrektur – Es wurde ein ID-Generierungsproblem beim Senden von Testsendungen mit Seed- oder Substitutionsadressen behoben. (NEO-42637)
* Fehlerkorrektur – Testsendungen können jetzt mit der Methode der Adressersetzung durchgeführt werden. (NEO-40417)
* Fehlerkorrektur – Das LINE-Package kann jetzt installiert werden. (NEO-42503)
