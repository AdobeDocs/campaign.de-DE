---
title: Versionshinweise 2025 zu Campaign v8 (Konsole)
description: Liste der Funktionen und Verbesserungen in Campaign v8-Versionen 2025
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: 981fa2029528cac5806da7c39aec3a2e6de0bf56
workflow-type: tm+mt
source-wordcount: '3477'
ht-degree: 33%

---

# Versionshinweise 2025 {#2025-rn}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der **Campaign v8-Versionen 2025** aufgelistet. Die neueste Version finden Sie auf [dieser Seite](release-notes.md).

Installieren Sie für jede neue Implementierung oder jedes Upgrade auf eine vorhandene Umgebung [die neueste Version](release-notes.md).

>[!BEGINSHADEBOX]

**Auf dieser Seite**

* [Version 8.8.2](#release-8-8-2)
* [Version 8.6.5](#release-8-6-5)
* [Version 8.6.4](#release-8-6-4)
* [Version 8.7.4](#release-8-7-4)
* [Version 8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]

## Version 8.8.2 {#release-8-8-2}

_9. Okt. 2025_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. 

### Neue Funktionen {#features-8-8-2}

Der **neue SMS-**-Connector) ist jetzt für [Campaign FFDA-Bereitstellungen](../architecture/enterprise-deployment.md) verfügbar. Weiterführende Informationen finden Sie im [entsprechenden Handbuch](../send/sms/sms.md).

Diese Version enthält auch eine Reihe von Funktionen, die in der Web-Benutzeroberfläche von Campaign verfügbar sind:

* [Profilanreicherung in Transaktionsnachrichten](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Mehrsprachige Funktionen für Transaktionsnachrichten, Push-Benachrichtigungen und SMS](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}

Weitere Informationen finden Sie in den Versionshinweisen zur [&#x200B; Web-Benutzeroberfläche von Campaign](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=de){target="_blank"}

### Fehlerbehebungen {#fixes-8-8-2}

<!--
* Fixed an issue which prevented dynamic reporting from being available for transactional messages.
-->
* Fehlerkorrektur - Der Datenbankbereinigungs-Workflow schlägt jetzt nicht mehr fehl. (NEO-87949)
* Fehlerkorrektur - Im verteilten Marketing werden jetzt Tracking-Daten für den Versand über partizipative Kampagnen erfasst. (NEO-86836)
<!--
* Issue SMS2.0 with FFDA Continuous Deliveries (NEO-88785)
-->
* Fehlerkorrektur - Die Personalisierung in Fragmenten funktioniert jetzt einwandfrei. (NEO-88161)
* Fehlerkorrektur - Nach der Migration zum neuen Redshift ODBC-Connector schlägt die Workflow-Aktivität Aufspaltung jetzt nicht mehr mit SQL-Fehlern fehl. (NEO-87466)
* Fehlerkorrektur - Die Anzahl der Ausschlüsse in Workflows ist jetzt korrekt. (NEO-89207)
* Fehlerkorrektur - Die Klickindikatoren für Push-Benachrichtigungen sind jetzt korrekt. (NEO-89503)
* Fehlerkorrektur - Die SMS-Versandlogs werden jetzt korrekt aktualisiert, was die Statusberichterstattung in Adobe Campaign verhindert. (NEO-88479)
* Es wurde ein Problem behoben, bei dem französische Anführungszeichen im Versandinhalt fälschlicherweise in englische Anführungszeichen konvertiert wurden. (NEO-89631)
* Es wurde ein Problem behoben, bei dem der Echtzeit-Server stattdessen einen falschen Antwort-Code für ungültige IMS-Token zurückgab. (NEO-87428)
* Fehlerkorrektur - Die Versandstatistiken für E-Mail und SMS werden jetzt vollständig neu berechnet, was zu ungenauen Erfolgsindikatoren führt. (NEO-88106)
* Fehlerkorrektur - Beim neuen SMS-Versand-Connector wird Versandlogs jetzt für eine kleine Teilmenge von Nachrichten kein Versandstatus mehr zugewiesen. (NEO-89581)
* Fehlerkorrektur - Beim neuen SMS-Versand-Connector werden die Erfolgsmetriken und Sendungen auf Marketing- und Mid-Server jetzt korrekt aktualisiert. (NEO-89850)
* Fehlerkorrektur - Es wurde ein Synchronisierungsproblem zwischen der Echtzeit- und der Marketing-Instanz behoben, das zu fehlenden Trackinglogs und falschen Berichten führte. (NEO-90247)
* Fehlerkorrektur: Es wurde ein Workflow-Anreicherungsproblem behoben, das zu Fehlern bei der Auswahl von Feldern über zwei aufeinander folgende 1-N-Links in benutzerdefinierten Schemata führen konnte. (NEO-87682)

## Version 8.8.1 {#release-8-8-1}

_Donnerstag, 9. Juli 2025_

### Neue Funktionen {#features-8-8-1}

Die zuvor für einige wenige Kunden veröffentlichte Funktion ist jetzt für alle Campaign FDA-Umgebungen verfügbar:

* **Neuer SMS-Versand-Connector** - Der SMS-Versand-Connector wurde modernisiert und verbessert, um SMPP-Verbindungen im Transceiver-Modus zu ermöglichen, persistente SMPP-Verbindungen zu aktivieren und eine bessere Kompatibilität sicherzustellen. Für alle neuen SMS-Implementierungen ist jetzt ein neues externes SMS-Konto verfügbar. Bestehende Implementierungen werden weiterhin unterstützt, es wird jedoch empfohlen, zu diesem neuen, modernen und erweiterten Connector zu wechseln. Wenden Sie sich an Adobe, wenn Sie zum neuen Connector wechseln möchten. [Weitere Informationen](../send/sms/sms.md)

  >[!NOTE]
  >
  >Diese Funktion ist **nicht** für [Campaign FFDA-Bereitstellungen](../architecture/enterprise-deployment.md) verfügbar.

<!-- (from ACC rn, aleady in the product, to remove?) -->

<!-- * **Enrichment in transactional messages** (to remove?) -->

<!--
* **Multilingual delivery creation** in the Web UI - You can now send multiple email deliveries in different languages in Adobe Campaign Web User Interface. The Multilingual delivery feature allows you to choose the default language of your delivery as well as the different languages in which the delivery can be sent. You can also preview these deliveries in the languages you have chosen. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html)

ACC - Multilingual deliveries - Starting Campaign Web User interface April release, you will be able to send multiple email deliveries in different languages, and access the related dynamic reports. This capability will only be available in Adobe Campaign Web User Interface at the end of April, and require a server update to Campaign v8.7.4.
-->

<!--
*  **Visual fragments** in the Web UI - You can now create, use and archive content fragments. Visual fragments are pre-defined visual blocks that you can reuse across multiple email deliveries, or in content templates. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments.html){target="_blank"}

(already available in console and web, to remove?) 
web - * Visual fragments - You can now archive visual content fragments. Learn more
-->

<!--
* **Delivery alerting** in the Web UI - The Delivery alerting feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html){target="_blank"}
-->

<!--
* **Landing pages improvements**  in the Web UI- The following improvements to landing pages are now available:

    * You can now reference a default subscription/unsubscription landing page when configuring a service. When designing an email, if you define a link to that landing page, users submitting the landing page form are automatically subscribed to or unsubscribed from this service. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/audiences/work-with-services/manage-services.html#create-service){target="_blank"}
    * A new option in the landing page configuration allows anonymous visitors to access the landing page. If you unselect this option, only identified users can access and submit the form. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#create-landing-page){target="_blank"}
    * A new option in the landing page configuration allows to store additional internal data when the landing page is being submitted. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#create-landing-page){target="_blank"}
    * A new option enables to use a landing page for several services, making it dynamic. When adding a link to an email, if you select a dynamic landing page, you can select any service. If you select a landing page that has a specific service associated, this service will be automatically used (you cannot select another one). [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#define-actions-on-form-submission){target="_blank"}
    * Conditional content is now supported in landing pages. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html){target="_blank"}
    * You can link a landing page to a service, and send a confirmation message when users validate it. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html#lp-message){target="_blank"}
    * You can add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#captcha){target="_blank"}

web - * **Subscriptions with Landing pages** - You can now link a landing page to a service, and send a confirmation message when users validate it. [Learn more](../landing-pages/lp-content.md#lp-message){target="_blank"}.
Web - * **Captcha in landing pages** - You can now add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](../landing-pages/create-lp.md#captcha)
-->

<!--
* (from ACC rn, already in product, to remove?) **Rich Push Notification (GA)** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push-android.md). 
ACC * Rich Push Notification templates - You can now send rich push notifications via Android. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. Read more.
-->

Zuvor war die Funktion in eingeschränkter Verfügbarkeit verfügbar. Jetzt ist **on demand)**:

<!--
* **Dynamic Reporting** - You can now access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Dynamic reporting is also available for multilingual email deliveries and transactional messages. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html){target="_blank"}

ACC **Dynamic Reporting for Transactional messages** - You can now monitor your transactional messages in the Dynamic Reporting user interface. These reports provide the ability to the marketer to view the all the reporting metrics and dimensions of transactional messages, breakdown of deliveries sent through a template in real time. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}
ACC - Dynamic Reporting - As a Campaign Standard migrated user, you can access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Read more
* **Dynamic Reporting for Multilingual** - Dynamic reporting is now available for multilingual email deliveries. For more information, refer to the [detailed documentation](../reporting/global-reports.md).
-->

* **REST-APIs** - Sie können jetzt REST-APIs verwenden, um Integrationen für Adobe Campaign zu erstellen und Ihr eigenes Ökosystem zu erstellen, indem Sie Adobe Campaign mit dem von Ihnen verwendeten Technologiebereich verbinden. Die Transaktionsnachrichten-REST-API ist auch für den SMS-Kanal verfügbar. Wenn sowohl „email“ als auch „mobilePhone“ in der Payload vorhanden sind, können Sie den Kanal über das Feld „wishedChannel“ angeben. Ohne Angabe wird standardmäßig „email“ verwendet, es sei denn, „wishedChannel“ fordert explizit SMS an. Ereignisbasierte Transaktions-APIs sind auch für E-Mails verfügbar. [Weitere Informationen](../dev/api/get-started-apis.md)

  >[!NOTE]
  >
  >Diese Funktion ist **nicht** für [Campaign FFDA-Bereitstellungen](../architecture/enterprise-deployment.md) verfügbar.

* **Liste mit einem Klick - Abmelden** - Bei wichtigen ISPs, bei denen Absender verlangen, dass Empfänger sich mit einem einzigen Klick sofort abmelden können, können Sie jetzt die Kopfzeile „Liste mit einem Klick - Abmelden“ in der Benutzeroberfläche direkt in der E-Mail-Vorlage oder in den Versandeigenschaften aktivieren. Diese Option ist standardmäßig aktiviert. [Weitere Informationen](../send/email-parameters.md#one-click-list-unsubscribe)

<!--
ACC - Rest APIs - As a Campaign Standard migrated user, you can use Rest APIs to create integrations for Adobe Campaign and build your own ecosystem by interfacing Adobe Campaign with the panel of technologies that you use. Read more
* **SMS REST API support (LA)** - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS. For more information, refer to the [detailed documentation](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target=_blank}.
ACC - SMS REST API support - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS.
ACC * **Transactional messaging REST APIs** - Event-based Transactional APIs are now available for Emails. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}
-->

Zusätzlich zu den oben aufgeführten Funktionen bietet diese Version auch eine Reihe von Funktionen, die in der Web-Benutzeroberfläche von Campaign verfügbar sind:

* [Erstellung eines mehrsprachigen Versands](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html#multilingual-delivery){target="_blank"}
* [Versandwarnungen](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html){target="_blank"}
* [Verbesserungen bei Landingpages](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/get-started-lp.html){target="_blank"}
* [Dynamisches Reporting](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"} (bei Bedarf)
* [Zentrales Branding](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html?lang=de){target="_blank"} (bei Bedarf, neue Implementierungen)

Weitere Informationen finden Sie in den Versionshinweisen zur [&#x200B; Web-Benutzeroberfläche von Campaign](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=de){target="_blank"}

### Allgemeine Verbesserungen {#improvements-8-8-1}

* Microsoft Fabrics wird jetzt als externe Datenbank mit Adobe Campaign Federated Data Access (FDA) unterstützt. [Weitere Informationen](../config/external-accounts.md#transfer-data-external-accounts)
* Campaign v8 unterstützt jetzt Android 15 und iOS 18 für Push-Benachrichtigungen. [Weitere Informationen](../start/compatibility-matrix.md#MobileSDK)
* Cloud-Datenbanken werden jetzt zusätzlich zu den On-Premise-Datenbanken für das Secure Virtual Private Network-Tunneling unterstützt. [Weitere Informationen](../config/enhanced-security.md#vpn-databases)
* Im Abschnitt „Eingehender Traffic“ des SMS 2.0-Connectors wurde ein neuer Satz von Feldern „Provider-ID“ hinzugefügt. [Weitere Informationen](../send/sms/smpp-external-account.md#incoming-traffic)
* Abgemeldete Empfänger über die „mailto“-Abmeldemethode werden nicht mehr unter Quarantäne gestellt. Sie werden entweder vom mit dem Versand verbundenen Service abgemeldet oder an die Blockierungsliste gesendet (Abschnitt „Nicht mehr kontaktieren“ des Profils), wenn für den Versand kein Service definiert wurde. [Weitere Informationen](../send/quarantines.md)
* Eine überarbeitete Version des Inbox Rendering-Berichts ist jetzt in der Adobe Campaign-Client-Konsole verfügbar.
* Die `setup-client.exe`-Datei wurde durch eine `ac-client.msi`-Datei ersetzt, was eine einfachere Methode für Administratoren bietet, um Massenaktualisierungen durchzuführen, ohne dass der Benutzer eingreifen muss.

### Fehlerbehebungen {#fixes-8-8-1}

* Es wurde ein Problem behoben, bei dem automatische Antworten aufgrund eines ungültigen Gültigkeitszeitraums in SMS 2.0 nicht empfangen wurden. Dadurch wird ein ordnungsgemäßer Nachrichtenversand nach der Migration sichergestellt. (NEO-88088)
* Es wurde ein Problem in SMS 2.0 behoben, bei dem bestimmte Felder in der `inSms`-Tabelle nicht korrekt aktualisiert wurden, was eine genaue Dateneinfügung für SMS-Funktionen sicherstellte. (NEO-87906)
<!--
* NOOOO Addressed delivery preparation failures for IndiGo Aviation after upgrading to v7.4.2. This fix resolves personalization and deduplication-related errors, enabling smooth delivery workflows. (NEO-87693)
* NOOOO Corrected Redshift database function definitions in version 8.6.4, ensuring proper execution of functions like `AddDays`, `AddHours`, `AddMinutes`, and `AddSeconds`. (NEO-87305)
* Provided a silent installation mechanism for the client console to facilitate mass upgrades without user intervention. This resolves challenges with manual installations. (NEO-69772)
-->
* Fehlerkorrektur - Der Datenbankbereinigungs-Workflow funktioniert jetzt fehlerfrei, wenn in SQL-Abfragen Spaltenverweise fehlen oder falsch sind. Dadurch wird eine ordnungsgemäße Bereinigung von Protokollen und Besucherdaten sichergestellt. (NEO-86813)
* Fehlerkorrektur - In Versandlogs fehlen jetzt keine Ereignisdaten mehr. Diese Fehlerbehebung stellt eine präzise Ereignisdatumsauffüllung sicher, die für geplante Trigger und Workflows von entscheidender Bedeutung ist. (NEO-86708)
* Fehlerkorrektur - Das Einfügen von SMS-Versandprotokollen in SMS 2.0 wird jetzt behoben, um eine ordnungsgemäße Protokollierung in der `nmsBroadLogMid` sicherzustellen. (NEO-86556)
* Behebung von Problemen bei der Dateiextraktion mit dem externen Versandmodus in Briefpostvorlagen, um Kompatibilität und Funktionalität sicherzustellen. (NEO-86520)
* Es wurden Probleme bei der Versandverarbeitung behoben, einschließlich des Aufspaltungs-Routings über mehrere MID-Instanzen hinweg, wodurch genaue Versandstatusaktualisierungen und ein genauer Durchsatz sichergestellt wurden. (NEO-86500)
* Fehlende Tracking-Daten in dynamischen Berichten wurden nach der Migration von Campaign Standard zu Campaign v8 behoben, wodurch eine genaue Berichterstellung für Versand-Tracking-Logs sichergestellt wurde. (NEO-86419)
* Fehlerkorrektur - Beim Auslösen von Workflow-Problemen wurden Workflows zweimal ausgeführt, was zu Verstößen gegen doppelte Schlüssel führte. Diese Fehlerbehebung stellt eine ordnungsgemäße Ereignisverarbeitung und -ausführung sicher. (NEO-86154)
* Es wurden Kompatibilitätsprobleme mit OOTB-SQL-Funktionen von Redshift nach der Bereitstellung behoben, wodurch die ordnungsgemäße Ausführung von Funktionen wie `GetDate()` in Workflows sichergestellt wurde. (NEO-85834)
* Korrektur von Rendering-Problemen in E-Mail-Builds, in denen Bilder verschwanden, als URLs angehängt wurden. Diese Fehlerbehebung stellt sicher, dass Bilder in der Vorschau des Posteingangs korrekt angezeigt werden. (NEO-85716)
* Korrektur der Darstellung geschweifter schließender Anführungszeichen in der Web-Benutzeroberfläche, um eine genaue Zeichenanzeige in E-Mail-Sendungen sicherzustellen. (NEO-85687)
* Fehlerkorrektur - Die Funktion für Mirrorseiten-Links sorgt für eine ordnungsgemäße Navigation zwischen Sprachvarianten innerhalb von Mirrorseiten. (NEO-85625)
* Es wurden Datumsformatprobleme in der Datumsauswahl der Web-Anwendung behoben, um die Kompatibilität mit japanischen Datumsformaten (`yyyy-mm-dd`) sicherzustellen. (NEO-85234)
* Fehlerkorrektur: Es wurden Probleme mit Nachbearbeitungs-Workflows bei alternativen Routing-Setups in Mid-Sourcing behoben, wodurch eine ordnungsgemäße Ausführung des Workflows sichergestellt wurde. (NEO-85111)
* Verbesserter Android-Versanddurchsatz bei der Verwendung von Schüben, um sicherzustellen, dass Versandteile basierend auf der Planung in der richtigen Reihenfolge verarbeitet werden. (NEO-84324)
* Fehlerkorrektur - Die Versandvorbereitung in `to_varchar` Funktion funktioniert jetzt fehlerfrei und gewährleistet so einen reibungslosen Kampagnenstart. (NEO-84108)
* Es wurden SFTP-Verbindungsprobleme behoben, die durch veraltete `libcurl`- und `libssh2`-Versionen verursacht wurden, um die Kompatibilität mit von Azure gehosteten SFTP-Servern sicherzustellen. (NEO-84038)
* Es wurden Snowflake FDA-Connector-Probleme im Zusammenhang mit Schlüsselpaar-Authentifizierungsfehlern behoben, wodurch eine erfolgreiche Datenbankverbindung sichergestellt wurde. (NEO-84024)
* Behebung von Problemen mit der Funktionalität von Typologieregeln, um die ordnungsgemäße Anwendung von Druckregeln in PUSH-Sendungen sicherzustellen. (NEO-84010)
* Behobene BigQuery-Fehler, die durch nicht übereinstimmende Datums- und Zeitstempelvergleiche nach dem Upgrade verursacht wurden, um Kompatibilität mit Filterbedingungen sicherzustellen. (NEO-83826)
* Es wurde ein Problem behoben, bei dem Versandaktivitäten bei der Wiederaufnahme pausierter Sendungen aufgrund von Personalisierungsfehlern fehlschlugen. Diese Fehlerbehebung sorgt für reibungslosere Versand-Workflows und verhindert Fehler im Zusammenhang mit ausgesetzten Aktivitäten. (NEO-83809)
* Fehlerkorrektur - Bei der Verwendung der Option „Laden des Zieldatensatzes“ tritt in FFDA jetzt kein Fehler mehr auf. Es wurde Unterstützung für die Klauseln „order by“ und „where“ hinzugefügt. (NEO-83793)
* Behebung von wiederkehrenden Versandfehlern, die dadurch verursacht wurden, dass Nullwerte in die Spalten der broadLogRcp-Tabelle geschrieben wurden, die keine NULL-Werte zulassen. Diese Fehlerbehebung verbessert die Versandzuverlässigkeit und verhindert Fehler während Live-Kampagnen. (NEO-83729)
* Es wurde ein Problem behoben, bei dem Testadressen während der Versandvorbereitung dupliziert wurden, was zu Diskrepanzen bei der Nachrichtenanzahl führte. Diese Fehlerbehebung stellt eine präzise Zielgruppenerfassung sicher und verhindert Duplizierungsfehler. (NEO-83703)
* Es wurde ein kritisches Problem behoben, bei dem Produktionslieferungen nach ihrem Gültigkeitszeitraum gesendet wurden, was möglicherweise zu rechtlichen Bedenken führte. Sendungen halten sich jetzt strikt an ihre definierten Gültigkeitszeiträume. (NEO-83350)
* Es wurde ein Speicherplatzproblem behoben, das beim Laden großer Datenmengen in Teradata-Tabellen auftrat. Diese Fehlerbehebung optimiert die Datenverarbeitung und behebt zeitweise auftretende Fehler in Produktionsumgebungen. (NEO-83252)
* Es wurde ein technischer Workflow-Fehler im Zusammenhang mit SendMetricsToNewRelic-Fehlern behoben, der zu Verzögerungen bei der RT-Ereignisverarbeitung führte. Diese Fehlerbehebung sorgt für eine reibungslosere Workflow-Ausführung und verhindert Ereignisrückstände. (NEO-83143)
* Fehlerkorrektur - Der Datenbankbereinigungs-Workflow funktioniert jetzt problemlos, wenn in FFDA-Interaktionsinstanzen Konversionsprobleme von ID zu UUID auftreten. Diese Aktualisierung stellt ordnungsgemäße Bereinigungsvorgänge sicher und reduziert die Systemlast. (NEO-83138)
* Fehlgeschlagene Sendungen wurden behoben, die durch Einschränkungen der internen Namenslängen von Testempfängern verursacht wurden. Diese Korrektur ermöglicht längere interne Namen, ohne dass sich dies auf die Versandpersonalisierung auswirkt. (NEO-83044)
* Fehlerkorrektur - Sendungen bleiben jetzt nicht mehr aufgrund von zufälligen Fehlern in der Personalisierung hängen. Diese Aktualisierung sorgt für reibungslosere Personalisierungsprozesse und eine zuverlässige Versandausführung. (NEO-82781)
* Es wurde ein Problem behoben, bei dem Angebotsvorschläge aufgrund von API-Fehlern und Langsamkeit nicht in der Konsole geprüft werden konnten. Diese Fehlerbehebung verbessert die Reaktionsfähigkeit der Benutzeroberfläche und stellt eine ordnungsgemäße Angebotsfunktionalität sicher. (NEO-82742)
* Zeitweise auftretende Abstürze in der Adobe Campaign-Konsole bei Verwendung benutzerdefinierter Versandobjekte wurden behoben. Diese Fehlerbehebung gewährleistet Stabilität und Zuverlässigkeit beim Arbeiten mit benutzerdefinierten Workflows. (NEO-82675)
* Fehlerkorrektur - Nach der Migration von v7 zu v8 kommt es jetzt nicht mehr zu langsamen Verarbeitungs- und Workflow-Fehlern. Diese Aktualisierung optimiert die Kampagnen-Workflows und sorgt für eine zeitnahe Ausführung. (NEO-82665)

<!--
* Resolved an issue where sysfilters were generating incorrect SQL queries after upgrading to v8.6.3. This fix ensures proper query generation and restores sysfilter functionality. (NEO-82591)
-->

* Fehlerkorrektur - Untergeordnete MTA-Prozesse bleiben jetzt nicht mehr hängen und blockieren Push- und WhatsApp-Sendungen. Diese Aktualisierung sorgt für reibungslosere Kommunikations-Workflows und verhindert Lieferengpässe. (NEO-82351)
* Es wurde ein Datenmigrationsproblem behoben, bei dem Zeichenfolgenfelder aus GCP-Tabellen Fehler während Aktualisierungen für Teradata verursachten. Durch diese Fehlerbehebung werden Umgehungslösungen überflüssig und die Workflow-Effizienz verbessert. (NEO-82260)
* Die Datenbankbereinigungslogik wurde aktualisiert, um primäre Datenbanken in FFDA-Instanzen zu berücksichtigen und unnötige Versuche zum Bereinigen nicht vorhandener Tabellen zu verhindern. Diese Fehlerbehebung optimiert Bereinigungsvorgänge. (NEO-81879)
* Behobene Konsolenabstürze, die durch die Verwendung von Unter-Workflows in Kombination mit Aufzählungsfeldern verursacht wurden. Diese Fehlerbehebung gewährleistet Stabilität bei der Arbeit mit erweiterten Workflows. (NEO-81864)
* Es wurde ein Problem behoben, bei dem Felder mit Unteraffinität in Zielgruppen-Mappings nach der Duplizierung des Versands fälschlicherweise geändert wurden, was zu Workflow-Fehlern führte. Diese Aktualisierung stellt konsistente Werte für die Unteraffinität sicher. (NEO-81809)
* Es wurde Unterstützung für Platzhalterzeichen bei Dateiübertragungsaktivitäten in Adobe Campaign Classic v8 hinzugefügt, sodass Benutzende Dateien mit dynamischen Namen (z. B. `abc_*`) in Workflows hochladen können. (NEO-81758)
* Es wurde eine Option zur Aktivierung des `content-available`-Flags in iOS-Push-Benachrichtigungen für Adobe Campaign Classic v8 eingeführt. Diese Verbesserung ermöglicht es mobilen Apps, Benachrichtigungen im Posteingang zu speichern, und unterstützt Hintergrundaktualisierungen, um Versandverwerfungsprobleme zu beheben, die durch APNS-Einschränkungen verursacht werden. (NEO-81721)

<!--
* Updated the Campaign 7.4.1 release upgrade process to require manual installation of dependencies. Documentation has been provided to guide users on installing required libraries such as `epel-release`, `java-11-openjdk-headless`, and others. (NEO-81433)
-->

* Es wurde eine Zeitüberschreitungskonfigurationsoption für BigQuery-Verbindungen in Adobe Campaign Classic v8 hinzugefügt. Diese Verbesserung ermöglicht es Benutzenden, den Timeout-Zeitraum für Abfragen anzupassen und Probleme mit Abfragefehlern aufgrund von standardmäßigen Timeout-Beschränkungen zu beheben. (NEO-81222)
* Fehlerkorrektur - Es wurde ein zeitweiliges Problem behoben, bei dem Mirrorseiten-URLs für Sendungen, die nach der v8-Migration über aufgeteilte und alternative Routing-externe Konten gesendet wurden, fehlschlugen. Die darunter liegenden Versandkontingente werden nun korrekt in `mirrorPageInfo` kopiert. (NEO-81105)

<!--
* Resolved an authentication failure issue with inMail caused by token expiration. Restarting the `nlserver` process now resolves the error. (NEO-80683)
-->

* Die Schaltfläche „Zugriff auf die neue Web-Benutzeroberfläche“ in der Client-Konsole wurde korrigiert, sodass sie auf die richtige URL (`https://experience.adobe.com`) für Produktionsinstanzen verweist. Dadurch werden Probleme mit ungültigen URLs in Produktionsumgebungen behoben. (NEO-80673)
* Fehlerkorrektur - In der Aufspaltungsaktivität treten jetzt keine SQL-Fehler mehr auf, wenn sowohl Sortierung als auch Größe (als Prozentsatz des Segments) verwendet werden. Die Funktion funktioniert jetzt ordnungsgemäß. (NEO-80432)
* Behebung eines Absturzproblems in Workflows mithilfe von `CCurlAzureBlobStorage::UploadStream`. Die Workflows werden jetzt während des Hochladens von Azure Blob Storage ohne Segmentierungsfehler ausgeführt. (NEO-79598)
* Es wurde ein Problem behoben, bei dem in Produktionsumgebungen keine Mirrorseiten von der Client-Konsole aus angezeigt werden konnten. Mirrorseiten-Links funktionieren jetzt sowohl in der E-Mail- als auch in der Konsolenansicht ordnungsgemäß. (NEO-78946)
* Fehlerkorrektur - Im Versandprotokoll wurden einige Protokolle trotz erfolgreicher Nachrichtenzustellung nicht korrekt als „Versand abgebrochen“ gekennzeichnet. Die Grundursache für Diskrepanzen beim Kontakt- und Ereignisdatum wurde behoben. (NEO-78933)
* Die `com.google.code.gson:gson`-Bibliothek wurde aktualisiert, um die Sicherheit zu verbessern. (NEO-78299)
* Fehlerkorrektur - Doppelte Schlüssel-Einschränkungsfehler in FDA-Verbindungsprotokollen (`nmsconnectionlogs`), die zu Workflow-Fehlern führten, wurden behoben. Die Einfügelogik wurde angepasst, um doppelte IDs zu vermeiden. (NEO-78050)
* Fehlerkorrektur - E-Mail-Adressen in Quarantäne werden in der Adresstabelle jetzt nicht mehr fälschlicherweise als mobil gekennzeichnet, was zu Fehlern bei der Versandanalyse führt. Die Abstimmlogik zwischen Versandobjekten wurde korrigiert. (NEO-76986)
* Fehlerkorrektur - Die Versandvorbereitung bei der Verwendung von Kontrollgruppen in einer Oracle-Datenbank ist jetzt fehlgeschlagen. Die SQL-Abfragegenerierung wurde korrigiert, um die Kompatibilität mit Oracle-Datenbanken sicherzustellen. (NEO-76947)
* Fehlerkorrektur - Die gleichzeitige Erstellung von Ordnern während der Übergänge in den neuen Monaten hat Versandfehler behoben. Die Erstellungslogik des Versandordners wurde angepasst, um Verletzungen von doppelten Schlüsseln zu verhindern. (NEO-76824)
* Fehlerkorrektur - In externen Teradata-Konten treten jetzt keine inkonsistenten Konversionsprobleme mehr auf. Die angezeigten Zeitstempel stimmen nun korrekt mit den konfigurierten Zeitzoneneinstellungen überein. (NEO-76716)
* Verbesserte Workflows zur Datenbankbereinigung, um große Datensätze effizient zu verarbeiten. Es wurde ein neuer Ansatz zur Optimierung der Löschleistung implementiert, bei dem Zeilen-IDs und Bindungsvariablen verwendet werden. (NEO-76439)
* Es wurde ein Problem behoben, bei dem externe Sendungen mit dem Kanal „Sonstige“ keine Ausgabedateien generiert haben. Die Versandeigenschaften enthalten nun den Dateipfad für die generierten Dateien korrekt. (NEO-75962)
* Fehlerkorrektur - Im `ffdaReplicateStagingData`-Workflow treten jetzt keine Fehler mehr auf, die durch große Datenaktualisierungen verursacht wurden. Die Einstellungen für die maximale Wartezeit und die Tabellengrößenverwaltung wurden optimiert, um Workflow-Fehler zu vermeiden. (NEO-75643)
* Es wurde ein Problem behoben, bei dem die Vorschau von Briefpost-Ausgabedateien dazu führte, dass Dashboards leer blieben. Das Dashboard wird nun nach der Dateivorschau korrekt angezeigt. (NEO-75359)
* Verbesserte Tracking-Indikatoren für Push-Benachrichtigungen , um Klicks und Öffnungen einzuschließen. Indikatoren wie `@recipientClick`, `@personClick` und `@totalRecipientClick` sind nun auch für mobile Benachrichtigungsklicks verantwortlich. (NEO-75240)
* Fehlerkorrektur - In Bereinigungs-Workflows werden jetzt keine Fehler mehr für Sendungen mit externen Status „Abbruch ausstehend“ mehr angezeigt. Die Logik zum Abrufen von Datenbankdatensätzen wurde korrigiert. (NEO-74833)
* Es wurde ein Problem mit einer Zeitzonen-Diskrepanz in Russland (UTC+3:00 Moskau) behoben, bei dem `nlserver` Ausgabezeiten falsch waren. Die Zeitsynchronisierungslogik wurde aktualisiert. (NEO-74754)
* Fehlerkorrektur - Im `defaultMidSourcingDlvStat`-Workflow treten jetzt keine Fehler mehr auf, die durch eine falsche SQL-Syntax für MSSQL-Datenbanken verursacht werden. Die Logik zur Abfragegenerierung wurde aus Gründen der Kompatibilität angepasst. (NEO-74156)
* Behandlung mehrerer Abstürze im Web-Prozess. (NEO-73174)
* Es wurde ein Problem behoben, bei dem BigQuery-Abfragen fehlschlugen, wenn Apostrophe in Bedingungen vorhanden waren. Die Logik zur Abfrageverarbeitung wurde aktualisiert, um Sonderzeichen korrekt zu interpretieren. (NEO-72547)
* Es wurde ein Problem behoben, bei dem Typologieregeln mit Ausschlussfiltern nicht ordnungsgemäß funktionierten. Die SQL-Abfragegenerierung für die Versandvorbereitung wurde behoben. (NEO-72292)
* Behebung von Diskrepanzen bei Ereignisdaten und Kontaktdaten für die Bounce-Verwaltung. Die Logik zur Zeitzonenbehandlung wurde verbessert. (NEO-72277)
* Verbesserte Handhabung von falsch konvertierten UTF-8-Zeichen in Briefpost-Sendungen. Ausgeblendete Zeichen werden jetzt korrekt verarbeitet, um Versandfehler zu vermeiden. (NEO-72148)
* Fehlerkorrektur - In der Aktivität „SMS-Empfang“ treten jetzt keine Fehler mehr auf, bei denen Filter zu Speicherproblemen führten. Der Workflow wird jetzt korrekt gespeichert, ohne Fehler zu erzeugen. (NEO-70427)
* Die SQL-Abfragegenerierung für gruppierte Eignungskriterien in Platzierungen wurde korrigiert. Es wurden fehlende Klammern in SQL-Bedingungen hinzugefügt, um eine ordnungsgemäße Filterung sicherzustellen. (NEO-70425)

<!--
* Updated the public documentation link in the `ffdaUnicity` workflow email template to point to the correct page for key management in v8. (NEO-67996)
-->

* Fehlerkorrektur - Zeitweise auftretende Fehler beim Laden von BigQuery-Daten, die durch HTTP-Inhalte oder Übertragungs-Codierungsprobleme verursacht werden, wurden behoben. Die Verbindungsbehandlungslogik wurde verbessert. (NEO-66989)

## Version 8.6.5 {#release-8-6-5}

_Samstag, 25. April 2025_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. 

### Neue Funktionen {#features-8-6-5}

**Neuer SMS-Versand-Connector**: Der SMS-Versand-Connector wurde modernisiert und verbessert, um SMPP-Verbindungen im Transceiver-Modus zu aktivieren, persistente SMPP-Verbindungen zu ermöglichen und eine bessere Kompatibilität für Umgebungen sicherzustellen, die von Adobe Campaign Standard aus umgestellt werden. Für alle neuen SMS-Implementierungen ist jetzt ein neues externes SMS-Konto verfügbar. Die vorhandene Implementierung wird weiterhin unterstützt. Es wird jedoch empfohlen, zu diesem neuen, modernen und erweiterten Connector zu wechseln. [Weitere Informationen](../send/sms/sms.md)

### Allgemeine Verbesserungen {#improvements-8-6-5}

* Die globale Leistung der Anwendung wurde im Kontext einer Enterprise-Bereitstellung (FFDA) verbessert, einschließlich der Durchführung des Testversands und der Datenbankbereinigung.

* Um die Sicherheit der gesamten Kommunikation zwischen Anwendungen zu erhöhen, wird mTLS jetzt für externe API-Aufrufe unterstützt.

* Mail Transfer Agent (MTA): Behebung eines Problems, bei dem ein verwaistes untergeordnetes MTA-Element im Status **[!UICONTROL Start ausstehend]** hängen bleibt.

### Fehlerbehebungen {#fixes-8-6-5}

Die folgenden Probleme wurden ebenfalls in dieser Version behoben:

NEO-67620, NEO-71534, NEO-80245, NEO-81105, NEO-81758, NEO-81908, NEO-82351, NEO-82742, NEO-83044, NEO-83138, NEO-83350, NEO-83729, NEO-83793, NEO-83809, NEO-84038, NEO-84108, NEO-85269, NEO-86121, NEO-86556, NEO-86739

## Version 8.7.4 {#release-8-7-4}

_Freitag, 10. April 2025_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. Sie ist Kundinnen und Kunden vorbehalten, die **von Adobe Campaign Standard zu Adobe Campaign v8** migrieren, und kann nicht in anderen Umgebungen bereitgestellt werden.
>
>Benutzende von Campaign Standard, die auf Campaign v8 umsteigen, können in der [Dokumentation zur Web-Benutzeroberfläche von Campaign v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration){target="_blank"} mehr über diese Transition erfahren.

### Neue Funktionen {#features-8-7-4}

* **SMS REST API-Unterstützung**: Das REST-API für Transaktionsnachrichten ist nun für den SMS-Kanal verfügbar. Wenn sowohl „email“ als auch „mobilePhone“ in der Payload vorhanden sind, können Sie den Kanal über das Feld „wishedChannel“ angeben. Ohne Angabe wird standardmäßig „email“ verwendet, es sei denn, „wishedChannel“ fordert explizit SMS. 

* **Mehrsprachige Sendungen**: Seit der Version der Campaign Web-Benutzeroberfläche vom April können Sie mehrere E-Mail-Sendungen in verschiedenen Sprachen senden und auf die zugehörigen dynamischen Berichte zugreifen. Diese Funktion wird erst ab Ende April in der Adobe Campaign Web-Benutzeroberfläche verfügbar sein und erfordert ein Server-Update auf Campaign v8.7.4.

### Fehlerbehebungen {#fixes-8-7-4}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-80245, NEO-83559

## Version 8.7.3 {#release-8-7-3}

_14. Februar 2025_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. Sie ist Kundinnen und Kunden vorbehalten, die **von Adobe Campaign Standard zu Adobe Campaign v8** migrieren, und kann nicht in anderen Umgebungen bereitgestellt werden.
>
>Benutzende von Campaign Standard, die auf Campaign v8 umsteigen, können in der [Dokumentation zur Web-Benutzeroberfläche von Campaign v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration){target="_blank"} mehr über diese Transition erfahren.

### Neue Funktionen {#features-8-7-3}

* **Dynamische Berichte für Transaktionsnachrichten**: Sie können jetzt Ihre Transaktionsnachrichten in der Benutzeroberfläche der dynamischen Berichte überwachen. Diese Berichte ermöglichen es Marketing-Fachleuten, alle Berichtsmetriken und Dimensionen von Transaktionsnachrichten sowie die Aufschlüsselung der über eine Vorlage gesendeten Sendungen in Echtzeit anzuzeigen. [Weitere Informationen](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"}

* **REST-APIs für Transaktionsnachrichten**: Ereignisbasierte Transaktions-APIs sind jetzt für E-Mails verfügbar. [Weitere Informationen](../dev/api/get-started-apis.md)

### Fehlerbehebungen {#fixes-8-7-3}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-79373, NEO-81908, NEO-83081

## Version 8.6.4 {#release-8-6-4}

_15. Januar 2025_

### Allgemeine Verbesserungen {#improvements-8-6-4}

* Die Stabilität der Campaign-Anwendung wurde bei der Versandanalyse im Kontext einer [Enterprise-Bereitstellung (FFDA)](../../v8/architecture/enterprise-deployment.md) optimiert.
* Diese Version enthält verbesserte und verstärkte FFDA-Architekturmechanismen, einschließlich Schlüsselverwaltung, Staging und Datenreplikation.
* Für die [Enterprise-Bereitstellung (FFDA)](../../v8/architecture/enterprise-deployment.md) wurden neue technische Workflows eingeführt. Diese Workflows replizieren den Versand und zugehörige Daten, indem sie parallele Replikationsanfragen für die entsprechenden Tabellen zentralisieren. Diese Workflows beginnen mit `Replicate nms`. [Weitere Informationen](../architecture/replication.md)
* Eine neue Option **Watchdog-Supervisor darf den Workflow dauerhaft laufen lassen** ist jetzt in den Workflow-Eigenschaften verfügbar. Wenn diese Option aktiviert ist, werden Workflows nach einem Fehler automatisch neu gestartet. Der Neustart erfolgt standardmäßig alle 30 Sekunden, wenn der Workflow noch immer einen Fehler aufweist. Um dieses Intervall anzupassen, können Sie eine neue Option `XtkWorkflow_WatchdogRestartTimerTimeout` erstellen und einen Datentyp als Ganzzahl festlegen, um die neue Verzögerung anzugeben. Diese Option sollte nur in technischen Workflows aktiviert werden. [Weitere Informationen](../../automation/workflow/workflow-properties.md#execution)

### Verbesserungen bezüglich der Sicherheit {#security-8-6-4}

Die Verarbeitung von HTTP-Anfragen im Apache-Web-Modul wurde verbessert, um die Sicherheit zu erhöhen und potenzielle Sicherheitslücken bei der Anfrageverarbeitung zu vermeiden. (NEO-85824)

Die Verbindung mit Adobe-Lösungen und -Anwendungen über das externe **[!UICONTROL Adobe Experience Cloud]**-Konto wurde aktualisiert, um die Sicherheit zu erhöhen.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Kompatibilitätsaktualisierungen {#comp-8-6-4}

Die folgenden FDA-Connectoren wurden hinzugefügt: Mehr dazu erfahren Sie auf [dieser Seite](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks wird jetzt als externe Datenbank mit Adobe Campaign Federated Data Access (FDA) unterstützt. 

* Ein neuer Amazon Redshift FDA ODBC-Connector ist jetzt verfügbar. Er bietet verbesserte Konnektivität, einfachere Wartung und optimierte Kompatibilität. Diese neue Version bietet die folgenden Verbesserungen:

   * Der neue Connector basiert auf der ODBC-Schnittstelle, die auf unsere neuesten FDA-Connectoren ausgerichtet ist. Dies sichert eine langfristige Unterstützung.
   * Außerdem wird ein neuer Mechanismus zum Laden von Daten mit S3-Buckets eingeführt, wodurch die Leistung erheblich verbessert wird.

  Der alte Connector kann weiterhin verwendet werden. Wenn Sie den neuen ausprobieren möchten, wenden Sie sich an den Adobe-Support.

### Fehlerbehebungen {#fixes-8-6-4}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-82665, NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137, NEO-83143.

