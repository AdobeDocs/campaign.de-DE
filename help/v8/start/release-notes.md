---
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 074a35acdeb45574f38247156ce777ae149e36f7
workflow-type: tm+mt
source-wordcount: '3835'
ht-degree: 92%

---

# Aktuelle Version{#latest-release}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der **aktuellen Campaign v8-Version** aufgelistet.

## Version 8.4.3 {#release-8-4-3}

>[!CAUTION]
>
> Die Aktualisierung der Client-Konsole ist obligatorisch. Auf dieser [Seite](../start/connect.md#download-ac-console) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.

_27. Januar 2023_

**Verbesserungen**

* Fehlerkorrektur - Es wurde ein Synchronisierungsproblem mit Versandindikatoren zwischen dem Marketing-Server und dem Mid-Sourcing-Server behoben. (NEO-50724) <!--OKKKK-->
* Fehlerkorrektur - Beim Export von Workflows tritt jetzt kein Fehler mehr auf. (NEO-50555) <!--OKKKK-->
* Fehlerkorrektur - Es wurde ein Problem beim Erweitern eines zuvor erweiterten Schemas behoben. (NEO-49118) <!--OKKKK-->
* Fehlerkorrektur - Bei der Verwendung von zwei Anreicherungsaktivitäten mit derselben Kennung in der Linkdefinition tritt jetzt kein Fehler mehr auf. (NEO-48851)
* Fehlerkorrektur - bei der Versandvorbereitung treten jetzt keine Fehler mehr auf. Die Versandvorbereitung konnte fehlschlagen, wenn die Anzahl der zu bearbeitenden potenziellen Angebote zu hoch war. Das zweite Problem trat auf, wenn die Bild-URLs als URLs definiert wurden, die in einem Textformat-Versand verfolgt werden sollen. (NEO-48807) <!--OKKKK-->
* Fehlerkorrektur - Workflow-Fehler werden jetzt nicht mehr dadurch verursacht, dass der im externen Konto definierte Warehouse-Name für Nicht-FFDA-Konten von einem Workflow überschrieben wird. (NEO-43209) <!--OKKKK-->
* Verbesserte Sicherheit für Webanwendungen, um DDoS-Angriffe zu verhindern. (NEO-50757) <!--OKKKK-->
* Die Verwaltung konsolidierter Tracking-Daten wurde im **[!UICONTROL Konsolidiertes Tracking]** (nms:trackingStats) FFDA-Tabelle, um Duplikate zu vermeiden. (NEO-46409)
* Fehlerkorrektur - In Workflow-Abfragen tritt bei der Verwendung von `enableIf` in einer logischen Operatorbedingung. Die vorherige logische Bedingung wurde überschrieben. (NEO-45815)  <!--OKKKK-->
* Die Erstellung aktiver Profile wurde im Abrechnungs-Workflow optimiert, um die Leistung zu verbessern. (NEO-47658) <!--OKKKK-->
* Fehlerkorrektur: Beim HTML-Dateiimport tritt jetzt kein Fehler mehr auf, wenn Bildknoten (img) URLs mit Personalisierungsfeldern enthalten. (NEO-48396)
* Es wurde ein Problem mit Snowflake (allen Implementierungen) bei der Verwendung des Sortierparameters in einer **Aufspaltung** Workflow-Aktivität. (NEO-45899) <!--OKKKK-->
* Fehlerkorrektur: Jetzt tritt kein Fehler mehr auf, wenn ein Benutzer bzw. eine Benutzerin mit Lesezugriffsrechten für den Ordner &quot;nmsDeliveryMapping&quot; versucht, eine Kampagne oder einen Workflow auszuführen. (NEO-48230)
* Fehlerkorrektur: Bei umfangreichem HTML-Code in der HTML-Tabelle eines Versands tritt jetzt kein Leistungsproblem mehr auf. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* Fehlerkorrektur - Benutzer können jetzt die **Ausgewählte Zeilen zusammenführen** Workflow-Option. (NEO-48488)
* Fehlerkorrektur - Im Snowflake-FDA-Connector werden Datensätze jetzt nicht mehr gelöscht, wenn während der Anreicherung die Option &quot;Einfache Verknüpfung mit Kardinalität 0 oder 1&quot; verwendet wird. (NEO-48737)
* Die verbleibenden Verweise auf die log4j-Bibliothek wurden aus der Campaign-Installation unter Windows entfernt. (NEO-44851)
* Fehlerkorrektur: Beim Hinzufügen des Indikators **Empfänger, die geöffnet haben** (estimatedRecipientOpen) zu den Zusatzdaten einer **Abfrage**-Workflow-Aktivität tritt kein Fehler mehr auf. (NEO-46665)
* Die Verwaltung von Tracking-URLs in Workflows mit mehreren Sendungen wurde verbessert, um die Leistung zu verbessern. (NEO-50894) <!--OKKKK-->
* Fehlerkorrektur - Die Replikation von Schemas, die Xtkfolder verwenden, schlägt jetzt nicht mehr fehl. (NEO-46787) <!--OKKKK-->
* Fehlerkorrektur - Die benutzerdefinierte Spalte &quot;lastModified&quot; wird jetzt in der NmsSubscription-Tabelle abgelegt. (NEO-48402)

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

## Version 8.2.8 {#release-8-2-8}

_Donnerstag, 28. Oktober 2021_

<table>
<thead>
<tr>
<th><strong>Eingehende Interaktionen</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Die Interaktionsverwaltung in Echtzeit ist jetzt für eingehende Kanäle verfügbar. Verwenden Sie das Modul "Inbound Interaction" in Campaign, um Ihren Kunden das beste Angebot zu unterbreiten, wenn sie Ihre Website besuchen oder sich an Ihr Callcenter wenden. Diese Funktion ist im Lieferumfang von Campaign v8 enthalten und erfordert eine spezifische Konfiguration für Ihre Instanz. Wenden Sie sich an Ihren Adobe-Support-Mitarbeiter, um Zugriff auf das Modul "Inbound Interaction" zu erhalten.</p>
<p>Weitere Informationen finden Sie in der <a href="../interaction/interaction-architecture.md">entsprechenden Dokumentation</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Kampagnenoptimierung</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Das Modul "Kampagnenoptimierung" ist jetzt verfügbar. Mit diesem Modul können Sie den Versand von Nachrichten steuern, filtern und überwachen. Um Konflikte zwischen Kampagnen zu vermeiden, kann Adobe Campaign verschiedene Kombinationen durch Anwendung spezifischer Beschränkungsregeln testen. Auf diese Weise werden ein ideal auf Kundenbedürfnisse abgestimmter Nachrichtenversand sowie eine kohärente Unternehmenskommunikation sichergestellt.</p>
<p>Weitere Informationen finden Sie in der <a href="https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=de#campaign-optimization">entsprechenden Dokumentation</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Unicity Service</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Unicity Service ist eine neue Komponente von Cloud Database Manager. Sie hilft Benutzern, die Integrität von Einschränkungen eindeutiger Schlüssel in Cloud-Datenbanktabellen zu wahren und zu überwachen. Dies hilft Ihnen zu verhindern, dass doppelte Schlüssel eingefügt werden.
<p>Da in der Cloud-Datenbank keine Einschränkungen hinsichtlich der Einheitlichkeit erzwungen werden, führt Unicity Service auf Anwendungsebene Folgendes ein: <b>eine Reihe neuer Limits</b>, um das Risiko von Duplikaten bei der Datenverwaltung mit Adobe Campaign zu verringern.</p> 
<p>Unicity Service startet einen neuen integrierten Workflow namens <b>ffdaUnicity</b>, durch den die Einheitlichkeitsbeschränkungen überwacht werden und ein Warnhinweis ausgegeben wird, wenn Duplikate erkannt werden.</p>
<p>Weitere Informationen finden Sie im <a href="../architecture/keys.md">entsprechenden Handbuch</a>.</p>
</td> </tr> 
</tbody> 
</table>


**Verbesserungen**

* Der Snowflake-Connector wurde hinsichtlich der Leistung verbessert.
* Zu Überwachungs- und Testzwecken enthalten die Prüfprotokolle des Workflows **[!UICONTROL Replizieren von Staging-Daten]** jetzt die Anzahl der Datensätze, die an die FFDA-Datenbank (Full Federated Data Access) gesendet wurden.
* Die SQL-Code-Aktivität ermöglicht jetzt die Auswahl der Datenbank, in der das SQL-Skript gespeichert wird: die Standarddatenquelle oder ein ausgewähltes aktives externes FDA-Konto.
* Eine Reihe vordefinierter Warehouses ist jetzt verfügbar und kann verwendet werden, um verschiedene Abfragen parallel auszuführen, wie Segmentierung, ETL oder Spitzen. [Weitere Informationen](../config/workflows.md)

**Sonstige Änderungen**

* Das Feld **[!UICONTROL Verschlüsselte Kennung]** wurde zum Besucherschema hinzugefügt (`nms:visitor`). Dieses Feld wird berechnet und ist für Web-Programme vorgesehen.
* Es wurde ein Problem behoben, das dazu führte, dass die Versandanalyse fehlschlug, wenn einige IP-Affinitäten in einigen Mid-Sourcing-Containern vorhanden waren, aber nicht in allen. Jetzt werden alle IP-Affinitäten in der Datenbank gespeichert, sodass jeder Container auf die Affinitäten zugreifen kann, die in allen anderen Containern vorhanden sind. (NEO-37564)
* Sie können jetzt ein Paket mit mehreren Schemata und Navigationsbaum-Knoten importieren.

**Patches**

* Nachdem ein Benutzer in einem Datenschema das `<autoStg>`-Attribut aus einem Tabellendefinitionselement entfernt hatte oder dessen Wert von `true` in `false` geändert wurde, wurde die zugehörige Staging-Tabelle nicht gelöscht. Dieses Problem wurde behoben.
* Es wurde ein Problem behoben, das bei der Erstellung von Datensätzen mit einem speziellen Formular aufgrund der ID-Verwaltung mit einer FFDA-Datenquelle einen Fehler verursachte.
* Es wurde ein Problem behoben, das das Einfügen von Angeboten in einen Versand verhindern konnte, wenn die Angebote durch eine Anreicherungsaktivität in einem Workflow verwaltet wurden.
* Es wurde ein Problem behoben, das den Import von Packages verlangsamen konnte.
* Es wurde ein Problem behoben, das verhindern konnte, dass E-Mail-Sendungen an Testadressen durchgeführt wurden.
* Es wurde ein Problem behoben, das verhindern konnte, dass Vorschläge in der Tabelle mit den Angebotsvorschlägen gespeichert wurden.
* Es wurde ein Fehler behoben, der dazu führte, dass Probleme mit Netzwerküberschreitungen fälschlicherweise als Skriptunterbrechungsprobleme anstatt als Netzwerkfehler protokolliert wurden. Dieses Problem trat bei HTTP-Anfragen auf, die in JavaScript-Aktivitäten enthalten waren.
* Es wurde ein Problem behoben, durch das Angebote nicht in die Live-Angebotsumgebung auf Snowflake repliziert werden konnten.
* Es wurde ein Problem behoben, durch das das Attribut &quot;autoStg&quot; für nicht erweiterte integrierte Schemata ignoriert wurde.
* Es wurde ein Problem behoben, das verhinderte, dass Benutzer bei der Vorschau eines Profils den Link **[!UICONTROL Land/Region]** auswählen konnten.
* Es wurde ein Fehler behoben, der dazu führte, dass die Datumsauswahl in benutzerdefinierten Berichten zu einem Skriptfehler führte. (NEO-36345)
* Es wurde ein Problem behoben, das zum Absturz des Systems führte, wenn die Konfiguration im Falle von fehlerhaften Konfigurationsdateien neu generiert wurde.
* Es wurde ein Problem behoben, das verhinderte, dass die Marketing- und Kontrollinstanzen erfolgreich aktualisiert werden konnten.
* Es wurde ein Problem behoben, das zum Absturz des Abrechnungs-Workflows bei Marketing-Instanzen führen konnte.
* Es wurde ein Problem behoben, das zu doppelten Schlüsseln in nativen FFDA-Snowflake-Tabellen führen konnte. (NEO-38583)
* Es wurde ein Problem behoben, das dazu führen konnte, dass temporäre Workflow-Schemata verloren gingen, wenn zwei Deduplizierungsaktivitäten nacheinander bearbeitet wurden. (NEO-34063)
* Es wurde ein Problem behoben, durch das beim Ausführen der HoursDiff- und MinutesDiff-Funktionen von Amazon Redshift beim Versuch, die Zeitkomponente zu extrahieren, falsche Ergebnisse ausgegeben wurden.(NEO-31673)
* Es wurde ein Problem behoben, das dazu führen konnte, dass sich Benutzer aufgrund eines Proxy-Konfigurationsproblems nicht an der Konsole anmelden konnten. (NEO-38388)
* Es wurde ein Regressionsproblem behoben, das dazu führte, dass die Funktion **Ordner bereinigen** nicht ordnungsgemäß funktionierte. (NEO-37459)
* Es wurde ein Problem behoben, das dazu führen konnte, dass die Vorschau von Mobile-Sendungen, die mit einem Workflow verbunden waren, nicht angezeigt wurde.
* Es wurde ein Problem behoben, das dazu führen konnte, dass die Workflow-Aktivität **Liste lesen** nicht funktionierte, wenn die Liste in der Datenbank mit einer negativen ID identifiziert wurde. (NEO-39607)

## Version 8.1.20 {#release-8-1-20}

_Dienstag, 7. September 2021_

**Verbesserungen bei der Sicherheit**

* Es wurde ein Sicherheitsproblem behoben, um den Schutz vor Directory Traversal-Angriffen zu verbessern. (NEO-28547)

**Verbesserungen**

* Nach seinem End-of-Life wurde Flash aus allen damit verbundenen Campaign-Funktionen und -Komponenten entfernt und durch HTML5 ersetzt. Der Diagrammtyp **Tacho** wurde entfernt. (NEO-30330) [Mehr dazu](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=de)
* Bei der Installation der Client-Konsole unter Windows überprüft das Installationsprogramm jetzt, ob ein übergeordneter Registrierungsknoten vorhanden ist, und erstellt einen, wenn er fehlt. Dadurch werden potenzielle Probleme beim Starten der Konsole verhindert. (NEO-34854)
* Die Tracking-Signatur-Funktion wurde verbessert, um Fehler zu verhindern, die in Zusammenhang mit der Art und Weise stehen, in der Drittanbieter-Tools (E-Mail-Clients, Internet-Browser usw.) Sonderzeichen verarbeiten. URL-Parameter sind jetzt codiert.

**Sonstige Änderungen**

* Veraltete Microsoft CRM-Connectoren (Office 365- und On-Premise-Implementierungen) wurden aus der Benutzeroberfläche entfernt. [Mehr dazu](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=de#configure-acc-for-microsoft)
* Nach der Migration zu Tomcat 8 wurde das IIS-Setup-Skript aktualisiert, um Probleme mit der IIS-Integration zu beheben. (NEO-31019)
* Es wurde ein Schutzmechanismus hinzugefügt, mit dem nur der [technische Workflow &quot;Abrechnung&quot;](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=de#billing-report) auf der Marketing-Instanz ausgeführt werden kann.
* In den Daten- und Schema-Tabs des Fensters **Population ansehen** der Workflow-Transitionen wurde die Identifizierung der Datenquelle verbessert.
* Fehlende Datenbankindizes wurden den folgenden Schemata hinzugefügt, um Probleme bei der Datenbankaktualisierung zu vermeiden: xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**Korrekturen**

* Fehlerkorrektur – Der Bericht **Klickposition** funktioniert jetzt, wenn Angebote mit dem Versand verknüpft sind. (NEO-26295)
* Fehlerkorrektur – Die Aktivität **Unter-Workflow** erzeugt bei ihrer Ausführung jetzt zuverlässig eine Ausgabetabelle. (NEO-36242)
* Das Exportieren des Berichts **Deskriptive Analyse** in PDF funktioniert jetzt problemlos. (NEO-25847)
* Fehlerkorrektur – Sendungen können jetzt problemlos über einen externen E-Mail-Versand durchgeführt werden. (NEO-37435)
* Fehlerkorrektur – Die Verbindung mit Microsoft CRM über die Web-API funktioniert jetzt fehlerfrei. Die Fehlermeldung wurde entfernt, da keine Funktionen betroffen waren.
* Fehlerkorrektur – Wenn der Mid-Server als Relais zwischen Tracking- und Marketing-Servern festgelegt wird, funktioniert die Trackinglog-Deduplizierung jetzt problemlos. (NEO-36285)
* Fehlerkorrektur – Bei einer Regression kann Vault als spezifischer Code-Store verwendet werden.
* Fehlerkorrektur – In der Workflow-Aktivität **Anreicherung** können jetzt Variablen verwendet werden, wenn die eingehende Transition aus einer FDA-Datenquelle stammt.
* Fehlerkorrektur – Die ordnungsgemäße Replikation von Benutzergruppen und Berechtigungen wird nicht mehr durch ein Problem mit FFDA verhindert.
* Fehlerkorrektur – Jetzt wird kein falscher Abmelde-Link mehr über den Versand gesendet.
* Fehlerkorrektur – Die Replikationsverwaltung wirkt sich jetzt nicht mehr auf die Dauer des Postupgrades aus.
* Fehlerkorrektur – Die **Klickposition** wird jetzt angezeigt.
* Fehlerkorrektur – URLs in E-Mail-Nachrichten werden jetzt fehlerfrei angezeigt.

## Version 8.1.14 {#release-8-1-14}

_Freitag, 23. Juli 2021_

**Neue Funktionen**

<table>
<thead>
<tr>
<th><strong>Neue Workflow-Aktivität: Datenquelle ändern</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Mit der neuen Workflow-Aktivität <b>Datenquelle ändern</b> können Sie die Datenquelle der Arbeitstabelle eines Workflows ändern. Dies bietet eine höhere Flexibilität bei der Verwaltung von Daten in verschiedenen Datenquellen (FDA, FFDA und lokale Datenbanken).</p>
<p>In Adobe Campaign-Workflows werden Daten mithilfe von Arbeits- (oder temporären) Tabellen verwaltet. Während der Workflow-Ausführung geben Arbeitstabellen Daten für Workflow-Aktivitäten frei. Standardmäßig werden die Arbeitstabellen auf derselben Datenbank erstellt wie die Quelle der Daten, die abgefragt werden.</p>
<p>In Campaign v8 wird die wichtigste Profiltabelle direkt in der Cloud-Datenbank gespeichert. Wenn Sie also die Profiltabelle abfragen, wird auch eine Arbeitstabelle in der Cloud-Datenbank erstellt. In bestimmten Fällen kann es sinnvoll sein, die Arbeitstabelle in eine andere Datenquelle zu verschieben, um bestimmte Vorgänge auszuführen.</p>
<p>Weitere Informationen finden Sie im <a href="../config/workflows.md#change-data-source-activity">entsprechenden Handbuch</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Verfügbarkeit des LINE-Kanals</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Der <a href="../send/line.md">LINE-Kanal</a> ist jetzt in Campaign v8 verfügbar, einschließlich der folgenden Verbesserungen in Kombination mit dem Modul <a href="../send/transactional.md">Transaktionsnachrichten</a>:
<ul> 
<li><p>Fehlerkorrektur – Jetzt können Besucher in einem LINE-Versand als Ziel ausgewählt werden. 
</p></li>
<li><p>Fehlerkorrektur – Beim Abrufen von Besuchern aus der Ausführungsinstanz und deren Übertragung in die Marketing-Instanz treten jetzt keine Fehler mehr auf.
</p></li>
<li><p>Fehlerkorrektur – Echtzeit-Ereignisse werden jetzt korrekt verarbeitet.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>


**Sonstige Verbesserungen**

* Fehlerkorrektur – Der **Klicks**-Bericht wird jetzt für alle Sendungen zuverlässig angezeigt.
* Fehlerkorrektur – Bei der Workflow-Aktivität **Deduplizierung** tritt jetzt kein Fehler mehr auf, der zu ungenauer Duplikatzählung führt.
* Fehlerkorrektur – Bei der Verwendung einer Workflow-Abfrage mit dem Filter &quot;ID ist nicht leer&quot; wird in der Population einer Transition kein leeres Element mehr angezeigt.
* Fehlerkorrektur – In einem neuen Zielgruppen-Mapping können jetzt zusätzliche Felder erstellt werden.
