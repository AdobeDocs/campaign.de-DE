---
product: campaign
title: Technische Workflows
description: Erfahren Sie mehr über die technischen Workflows, die mit Campaign verfügbar sind
feature: Workflows
role: User, Admin
exl-id: 2693856c-80b2-4e35-be8e-2a9760f8311f
source-git-commit: 0a074b2ef84e89e67363b722372718e4c46d65e5
workflow-type: tm+mt
source-wordcount: '1827'
ht-degree: 90%

---

# Technische Workflows{#about-technical-workflows}

Adobe Campaign verfügt über eine Reihe integrierter technischer Workflows. Sie steuern Vorgänge und Aufträge, die für die periodische Ausführung auf dem Server geplant sind. Technische Workflows führen Wartungsarbeiten an Ihrer Campaign-Datenbank durch, verwalten Tracking-Daten zu Sendungen und richten provisorische Versandprozesse ein.

Standardmäßig sind technische Workflows in einem Unterordner des folgenden Knotens verfügbar: **[!UICONTROL Administration]** > **[!UICONTROL Produktion]** > **[!UICONTROL Technische Workflows]**.

![](assets/navtree.png){width="50%" align="left" zoomable="yes"}

>[!NOTE]
>
>* Die Liste der technischen Workflows, die mit jedem Modul installiert werden, finden Sie in [diesem Abschnitt](#list-technical-workflows).
>
>* Technische Workflows, die mit dem Message Center-Add-on in Verbindung stehen, werden standardmäßig im Knoten **[!UICONTROL Administration]** > **[!UICONTROL Betreibung]** > **[!UICONTROL Message Center]** > **[!UICONTROL Technische Workflows]** gespeichert.

Der Unterordner **[!UICONTROL Kampagnenprozesse]** enthält die für die Ausführung wichtiger Kampagnenvorgänge (Benachrichtigungen zu Aufgaben, Lagerverwaltung, Kostenberechnungen etc.) notwendigen Workflows.

![](assets/campaign-processes-wf.png)

## Technische Workflows verwalten und erstellen {#manage-tech-workflows}

Technische Workflows für Campaign können nur von Benutzern mit **Administratorberechtigungen** gestartet und geändert werden. In diesem [Abschnitt](monitor-technical-workflows.md) erfahren Sie, wie Sie technische Workflows überwachen.

Sie können benutzerdefinierte technische Workflows im Knoten **[!UICONTROL Administration > Betreibung > Technische Workflows]** der Baumstruktur erstellen. Zur Erstellung von technischen Workflows stehen spezifische Vorlagen zu Verfügung. Sie können entsprechend Ihren Anforderungen konfiguriert werden. Dieser Prozess ist jedoch erfahrenen Benutzern vorbehalten. Die in technischen Workflows verfügbaren Aktivitäten entsprechen denen von Zielgruppen-Workflows. [Weitere Informationen](targeting-workflows.md).

## Integrierte technische Workflows {#list-technical-workflows}

Die auf dieser Seite beschriebenen Workflows werden mit den integrierten Adobe Campaign-Packages installiert. Diese Pakete und die damit verbundenen technischen Workflows hängen von Ihrer Lizenzvereinbarung und Ihren Add-ons ab.

| Technischer Workflow | Package | Beschreibung  |
|------|--------|-----------|
| **Alias-Datenbereinigung** (aliasCleansing) | Standardmäßig installiert | Dieser Workflow vereinheitlicht Aufzählungswerte. Er wird standardmäßig täglich um 3 Uhr morgens ausgelöst. |
| **Abrechnung** (billing) | Standardmäßig installiert | Dieser Workflow übermittelt per E-Mail den Aktivitätsbericht des Systems an den fakturierungsverantwortlichen Benutzer (&#39;billing&#39;). Er wird am 25. jedes Monats in der Marketing-Instanz ausgelöst. |
| **Vorgänge bei Kampagnen** (operationMgt) | Standardmäßig installiert | Dieser Workflow verwaltet Vorgänge in Marketing-Kampagnen (Zielgruppenbestimmung, Dateiextraktion etc.). Er erstellt darüber hinaus Workflows für wiederkehrende und periodische Kampagnen. |
| **Erfassen von Daten für den HeatMap-Service** (collectDataHeatMapService) | Standardmäßig installiert | Dieser Workflow ruft die für den HeatMap-Service erforderlichen Daten ab. |
| **Erfassen von Datenschutzanfragen** (collectPrivacyRequests) | Datenschutzbestimmung | Mit diesem Workflow werden die in Adobe Campaign gespeicherten Empfängerdaten abgerufen und auf dem Bildschirm zur Datenschutzanfrage für den Download bereitgestellt. |
| **Kostenberechnung** (budgetMgt) | Standardmäßig installiert | Dieser Workflow berechnet Ausgaben- und Kostenposten für Budgets, Pläne, Programme, Kampagnen, Sendungen und Aufgaben. |
| **Datenbankbereinigung** (cleanup) | Standardmäßig installiert | Dieser Workflow ist der Datenbankwartungs-Workflow: Er führt verschiedene Berechnungen mit Statistiken und Prozessen durch und löscht gemäß der definierten Konfiguration im Bereitstellungsassistenten veraltete Daten aus der Datenbank. Er wird standardmäßig jeden Tag um 4 Uhr morgens ausgelöst. |
| **Löschen von gesperrten LINE-Benutzern** (deleteBlockedLineUsersV2) | LINE-Kanal | Dieser Workflow stellt sicher, dass die Daten der LINE V2-Benutzer gelöscht werden, nachdem sie das offizielle LINE-Konto 180 Tage lang gesperrt haben. |
| **Löschen von Datenschutzanfragedaten** (deletePrivacyRequestsData) | Datenschutzbestimmung | Mit diesem Workflow werden die in Adobe Campaign gespeicherten Empfängerdaten gelöscht. |
| **Versandindikatoren** (deliveryIndicators) | Standardmäßig installiert | Dieser Workflow aktualisiert Tracking-Indikatoren eines Versands. Er wird standardmäßig stündlich ausgelöst. |
| **Bearbeitungsvorgänge des verteilten Marketings** (centralLocalMgt) | Zentrales/lokales Marketing (verteiltes Marketing) | Dieser Workflow führt die Vorgänge im Zusammenhang mit dem Modul &quot;verteiltes Marketing&quot; aus. Er erstellt lokale Kampagnen und verwaltet Benachrichtigungen in Bezug auf Bestellungen und die Verfügbarkeit von Campaign-Packages. |
| **Bereinigen von Ereignissen** (webAnalyticsPurgeWebEvents) | Web Analytics-Connectoren | Mit diesem Workflow können Sie jedes Ereignis aus dem Datenbankfeld entsprechend dem im Feld &quot;Lebensdauer&quot; konfigurierten Zeitraum löschen. |
| **Exportieren von Audiences zu Adobe Experience Cloud** (exportSharedAudience) | Integration mit Adobe Experience Cloud | Dieser Workflow exportiert freigegebene Audiences/Segmente. Diese können dann in anderen von Ihnen verwendeten Lösungen von Adobe Experience Cloud genutzt werden. |
| **Prognosen** (forecasting) | Standardmäßig installiert | Dieser Workflow analysiert die im Planungskalender verzeichneten Sendungen (Erstellung von Planungslogs). Er wird standardmäßig täglich um 1 Uhr morgens ausgelöst. |
| **Berechnung des vollständigen Aggregats (propositionrcp-Cube)** (agg_nmspropositionrcp_full) | Angebotsmodul (interaction) | Dieser Workflow aktualisiert das volle Aggregat des Angebotsvorschlag-Cubes. Er wird standardmäßig täglich um 6 Uhr morgens ausgelöst. Dieses Aggregat erfasst die folgenden Dimensionen: Kanal, Versand, Marketing-Angebot und -Datum. Der Cube „Angebotsvorschlag“ wird dann zur Erstellung von angebotsbasierten Berichten verwendet. Weitere Informationen zu Cubes finden Sie in [diesem Abschnitt](../../v8/reporting/gs-cubes.md). |
| **Identifizierung der konvertierten Kontakte** (webAnalyticsFindConverted) | Web Analytics-Connectoren | Dieser Workflow indexiert die Besucher, die nach einer Remarketing-Kampagne einen Kauf getätigt haben. Die von diesem Workflow ermittelten Daten werden im Bericht Remarketing-Effizienz zur Verfügung gestellt (siehe diese Seite). |
| **Importieren von Audiences aus Adobe Experience Cloud** (importSharedAudience) | Integration mit Adobe Experience Cloud | Dieser Workflow ermöglicht den Import von Audiences/Segmenten aus den unterschiedlichen Adobe Experience Cloud-Lösungen in Adobe Campaign. |
| **Bearbeitungsvorgänge bezüglich Kampagnensendungen** (deliveryMgt) | Standardmäßig installiert | Dieser Workflow startet den Versand der validierten Sendungen und die Anschlussvorgänge des Dienstleisters bei externem Versand. Außerdem werden Validierungsbenachrichtigungen und Erinnerungen gesendet. |
| **Bearbeitungsvorgänge bezüglich der Dienstleister** (supplierMgt) | Standardmäßig installiert | Dieser Workflow startet Provider-Vorgänge nach erfolgter Versandvalidierung (E-Mail an den Router und nachfolgende Vorgänge). |
| **Migration von MID zu LineUserID** (MIDToUserIDMigration) | LINE-Kanal | Dieser Workflow erzeugt die Kennung von LINE V2-Benutzern für die Migration von LINE V1 nach LINE V2. |
| **Message Center &lt;external_account_name>** (mcSynch_&lt;external_account_name>) | Kontrolle der Transaktionsnachrichten (Message Center – Kontrolle) | Dieser Workflow: <ul><li>Ruft die Liste der durch die Aktion(en) verarbeiteten Ereignisse ab.</li><li>Wird mit der NmsBroadLogMsg-Tabelle synchronisiert, um die Qualifizierung der Versandnachrichten abzurufen.</li><li>Ruft Ereignis-Versandlogs ab, sobald die Synchronisation mit der NmsBroadLogMsg-Tabelle abgeschlossen ist.</li><li>Wird mit der NmsTrackingUrl-Tabelle synchronisiert, um das Tracking für die Versand-URLs abzurufen.</li><li>Ruft Ereignis-Verfolgungs-URLs ab, sobald die Synchronisation mit der NmsTrackingUrl-Tabelle abgeschlossen ist.</li><li>Ruft alle drei Stunden die E-Mail-Adressen ab, die infolge eines Versands neu in Quarantäne gekommen sind.</li></ul> |
| **Berechnung des vollen Message Center-Aggregats** (agg_messageCenter_full) | Kontrolle der Transaktionsnachrichten (Message Center – Kontrolle) | Dieser Workflow aktualisiert das vollständige Aggregat für den Message Center-Cube. Er wird standardmäßig jeden Tag um 3 Uhr morgens ausgelöst. Dieses Aggregat erfasst die folgenden Dimensionen: Kanal, Datum, Status und Ereignistyp. Der Message Center-Cube wird dann zur Erstellung von ereignisbasierten Berichten verwendet. Weitere Informationen zu Cubes finden Sie hier |
| **Mid-Sourcing (Versandzähler)** (defaultMidSourcingDlv) | Weiterleitung an Mid-Sourcing | Dieser Workflow ruft Informationen bezüglich der Zählung von Sendungen vom Mid-Sourcing-Server ab. Zu diesen Informationen gehören allgemeine Versandindikatoren wie etwa die Anzahl der Sendungen. Tracking-Informationen wie etwa Öffnungen sind nicht enthalten. Dieser Workflow wird standardmäßig alle zehn Minuten ausgelöst. |
| **Mid-Sourcing (Versand-Logs)** (defaultMidSourcingLog) | Weiterleitung an Mid-Sourcing | Dieser Workflow ruft Versand-Logs vom Mid-Sourcing-Server ab. Er wird standardmäßig stündlich ausgelöst. |
| **NMAC-Abmeldungsverwaltung** (mobileAppOptOutMgt) | Mobile-App-Kanal (Push) | Dieser Workflow aktualisiert die Abmeldungen von Benachrichtigungen auf Smartphones und Tablets. Er wird standardmäßig alle sechs Stunden zwischen 1 Uhr morgens und Mitternacht ausgelöst. |
| **Benachrichtigung über Angebote** (offerMgt) | Standardmäßig installiert | Dieser Workflow stellt validierte Angebote sowie die im Angebotskatalog enthaltenen Kategorien in die Online-Umgebung bereit. |
| **Bereinigung angehaltener Workflows** (cleanupPausedWorkflows) | Standardmäßig installiert | In diesem Workflow werden angehaltene Workflows analysiert, für die eine normale Prioritätsstufe festgelegt wurde. Er löst Warnhinweise und Benachrichtigungen aus, wenn sie zu lange angehalten werden. Nach einem Monat werden ausgesetzte technische Workflows bedingungslos gestoppt. Standardmäßig wird dieser Workflow jeden Montag um 5 Uhr morgens ausgelöst. Weitere Informationen finden Sie unter [Handhabung angehaltener Workflows](monitor-workflow-execution.md#handling-of-paused-workflows). |
| **Datenschutzanfragebereinigung** (cleanupPrivacyRequests) | Datenschutzbestimmung | Mit diesem Workflow werden Dateien mit Zugriffsanfragen gelöscht, die älter als 90 Tage sind. |
| **Verarbeitung von Batch-Ereignissen** (batchEventsProcessing) | Ausführung einer Transaktionsnachricht (Message Center – Ausführung) | Mit diesem Workflow können Sie Batch-Ereignisse in eine Warteschlange stellen, bevor ihnen eine Nachrichtenvorlage zugeordnet wird. |
| **Verarbeitung von Echtzeitereignissen** (rtEventsProcessing) | Ausführung einer Transaktionsnachricht (Message Center – Ausführung) | Mit diesem Workflow können Sie Echtzeitereignisse in eine Warteschlange stellen, bevor ihnen eine Nachrichtenvorlage zugeordnet wird. |
| **Synchronisation von Vorschlägen** (propositionSynch) | Steuerung des Angebotsmoduls durch die Ausführungsinstanz | Dieser Workflow synchronisiert Vorschläge zwischen der Marketing-Instanz und der Ausführungsinstanz, die für Interaktionen verwendet wird. |
| **Abruf von Web-Ereignissen** (webAnalyticsGetWebEvents) | Web Analytics-Connectoren | Dieser Workflow ruft stündlich die Segmente ab, die sich auf das Besucherverhalten einer gegebenen Website beziehen, fügt die Daten zur Adobe Campaign-Datenbank hinzu und startet den Remarketing-Workflow. |
| **Berichtsaggregate** (reportingAggregates) | Versand | Dieser Workflow aktualisiert die in Berichten verwendeten Aggregate. Er wird standardmäßig täglich um 2 Uhr morgens ausgelöst. |
| **Übermittlung von Indikatoren und Kampagnenattributen** (webAnalyticsSendMetrics) | Web Analytics-Connectoren | Dieser Workflow ermöglicht es Ihnen, Indikatoren für E-Mail-Kampagnen aus Adobe Campaign über Adobe® Analytics Connector an Adobe Experience Cloud Suite zu senden. Dies betrifft die folgenden Indikatoren: Gesendet (iSent), Öffnungen insgesamt (iTotalRecipientOpen), Gesamtzahl der Empfänger, die geklickt haben (iTotalRecipientClick), Fehler (iError), Abmeldung (Opt-out) (iOptOut). |
| **Lager: Bestellungen und Warnhinweise** (stockMgt) | Standardmäßig installiert | Dieser Workflow startet die Berechnung der Lagerbestände zu den Bestellzeilen und verwaltet Warnschwellen. |
| **Synchronisieren von Apps mit der Datenerfassung von Adobe Experience Platform** (syncWithLaunch) | Standardmäßig installiert, ab Version 8.5 | Mit diesem Workflow werden Mobile-Eigenschaften aus der Datenerfassung automatisch mit Adobe Campaign synchronisiert. |
| **Tracking** (tracking) | Standardmäßig installiert | Dieser Workflow ruft Tracking-Informationen ab und konsolidiert sie. Er aktualisiert außerdem die Berechnung der Tracking- und Versandstatistiken, insbesondere der Statistiken, die von den Archivierungs-Workflows des Message Centers verwendet werden. Er wird standardmäßig stündlich ausgelöst. |
| **Update des Ereignisstatus** (updateEventsStatus) | Ausführung einer Transaktionsnachricht (Message Center – Ausführung) | Dieser Workflow weist Ereignissen einen Status zu. Folgende Status sind möglich:<ul><li>Ausstehend: Das Ereignis befindet sich in der Warteschlange. Ihm wurde noch keine Nachrichtenvorlage zugeordnet.</li><li>Versand ausstehend: Das Ereignis befindet sich in der Warteschlange. Ihm wurde eine Nachrichtenvorlage zugeordnet und die Versandverarbeitung ist im Gange.</li><li>Gesendet: Dieser Status wird aus den Versandlogs übernommen. Er bedeutet, dass die Nachricht gesendet wurde.</li><li>Vom Versand ignoriert: Dieser Status wird aus den Versand-Logs übernommen. Er bedeutet, dass der Versand ignoriert wurde.</li><li>Versandfehler: Dieser Status wird aus den Versand-Logs übernommen. Er bedeutet, dass der Versand fehlgeschlagen ist.</li><li>Ereignis wurde nicht berücksichtigt: Dem Ereignis konnte keine Nachrichtenvorlage zugeordnet werden. Es erfolgt kein weiterer Verarbeitungsversuch.</li></ul> |
| **Update für Zustellbarkeit** (deliverabilityUpdate) | Standardmäßig installiert | Sobald das Paket zur Überwachung der Zustellbarkeit (E-Mail-Zustellbarkeit) installiert ist, wird dieser Workflow nachts ausgeführt und verwaltet die Qualifikationsregeln für unzustellbare E-Mails sowie die Liste der Domains und MXs. Dazu muss der HTTPS-Port auf der Plattform geöffnet sein. |
| **Abmeldungen aktualisieren** (ffdaUnsubscribe) | Standardmäßig nur bei [Campaign Enterprise (FFDA)-Bereitstellungen](../../v8/architecture/enterprise-deployment.md) installiert | Dieser Workflow verarbeitet Abmeldungen, die als Bounce-E-Mails zurückgesendet wurden (mithilfe der `<mailto>`-Abmeldemethode). Er wird täglich im Stundentakt nur auf Marketing-Instanzen mit einer Unternehmensbereitstellung (FFDA) ausgeführt.<br/><br/>Der Workflow überprüft Broadlogs aus einem bestimmten Zeitraum (letzte Verarbeitungszeit und aktuelle Zeit), die vom inMail-Modul als Abmelde-Bounces markiert werden (Markierung wurde in der NmsBroadLog-Tabelle in der Spalte „iFlags“ festgelegt), und verarbeitet eine Abmeldung abhängig davon, ob der Dienst des Broadlogs festgelegt ist oder nicht:<ul><li>Wenn die serviceId „0“ lautet (nicht definiert), wird die Empfängerin bzw. der Empfänger auf die Blockierungsliste gesetzt.</li><li>Wenn die serviceId nicht „0“ lautet (mit einem vorhandenen Dienst verknüpft), wird die Empfängerin bzw. der Empfänger von diesem Dienst abgemeldet.</li></ul><br/>Hinweis: Dieser Workflow verarbeitet nur Bounce-Abmeldungen. Abmeldungen, die über den Ausschluss-Link erfolgen, und Ein-Klick-Abmeldungen (URL-Methode) werden separat außerhalb dieses Workflows verarbeitet. |
