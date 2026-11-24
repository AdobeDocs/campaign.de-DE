---
title: Kampagnenoptionen
description: Erfahren Sie, was Campaign-Optionen sind, wo sie gespeichert werden und wie Sie die für Campaign v8 dokumentierten Optionen verwenden
feature: Architecture
role: Admin, Developer
level: Intermediate
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 36111995a9a550d5089107bbc1f734c204db8aff
workflow-type: tm+mt
source-wordcount: '2836'
ht-degree: 3%
---
# Kampagnenoptionen {#campaign-options}

Optionen sind Parameter, die steuern, wie sich Ihre Campaign-Instanz verhält, z. B. die Standardgrößenbeschränkung von Bildern in E-Mails, die Anzahl der gleichzeitig ausgeführten Workflows oder der standardmäßige Routing-Anbieter von Versandvorlagen. Einige Optionen sind integriert und andere werden bei Bedarf erstellt. Die verfügbaren Optionen hängen von den auf Ihrer Instanz installierten Paketen ab. Weitere Informationen finden [&#x200B; unter „Integrierte Pakete](built-in-packages.md).

>[!CAUTION]
>
>Ändern Sie nur die in der Campaign-Dokumentation dokumentierten Optionen und nur die hier beschriebenen. Nicht dokumentierte Optionen sind intern und dürfen nicht geändert werden. Das Ändern von Optionen ist erfahrenen Benutzern vorbehalten.

## Wo Optionen gespeichert werden {#where-options-are-stored}

Optionen werden in der Campaign-Datenbank in der Tabelle **xtkOption** gespeichert (Schema **xtk:option**). Im Campaign-Explorer sind sie unter **[!UICONTROL Administration]** > **[!UICONTROL Plattform]** > **[!UICONTROL Optionen]** verfügbar. In der Web-Benutzeroberfläche von Campaign sind sie unter **[!UICONTROL Administration]** > **[!UICONTROL Optionen]** verfügbar. Beide Listen sind identisch. Weitere Informationen finden Sie unter [Konfigurieren von Kampagnenoptionen](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options){target="_blank"}.

## Verwenden von Optionen {#use-options}

1. Navigieren Sie im Campaign-Explorer zu **[!UICONTROL Administration]** > **[!UICONTROL Plattform]** > **[!UICONTROL Optionen]**.
1. Wählen Sie die Option aus und aktualisieren Sie dann ihren Wert. Wenn die Option nicht vorhanden ist, erstellen Sie sie mit dem genauen Namen, der in der Dokumentation angegeben ist.
1. Legen Sie einen Wert des Typs fest, den die Dokumentation erwartet. Beispielsweise eine Textoption für das CRM-Synchronisierungsdatum oder eine Ganzzahloption für die Verzögerung des Workflow-Neustarts.

Sie können auch eigene Optionen erstellen, z. B. um Zwischendaten eines Workflows zu speichern. Geben Sie einen Namen ein, wählen Sie den Datentyp aus und legen Sie den Wert fest. Weitere Informationen finden Sie unter [Konfigurieren von Kampagnenoptionen](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#create){target="_blank"}.

Einige Optionen verfügen über Anmeldeinformationen. Verschlüsseln Sie geheime Daten mit der `cryptString`, wie unter [Arbeiten mit Campaign- und Adobe Experience Platform-Landingpages“ beschrieben](../connect/ac-aep-landing-pages.md). Drehen Sie beim Drehen von Anmeldeinformationen auch die in Optionen gespeicherten Anmeldeinformationen. Weitere Informationen finden Sie im [Handbuch zur Berechtigungs-Rotation](../../technotes/security/credential-rotation-guide.md#ac-options-credentials).

## Verwenden von Optionen in Workflows und Personalisierung {#use-options-in-processes}

Sie können Optionswerte aus JavaScript-Code, Personalisierung und Abfragen lesen und schreiben.

* **JavaScript-**, z. B. eine Workflow-Aktivität vom Typ JavaScript-Code: `getOption('OptionName')` gibt den Wert einer Option zurück und legt ihn `setOption('OptionName', value, 'description')` fest. Beispiel: `getOption('IMS_ORG_ID')`. Weitere Informationen finden Sie unter [getOption](../../campaign-api/f-getoption.md) und [setOption](../../campaign-api/f-setoption.md).
* **Versandpersonalisierung**: `<%@ include option='OptionName' %>` fügt den Wert einer Option ein. Beispielsweise enthält `<%@ include option='NmsServer_URL' %>` die Server-URL in einem Link zu einer Web-Anwendung in einer LINE-Nachricht. Weitere Informationen finden Sie unter [Senden von LINE-Direktnachrichten mit Adobe Campaign](../send/line/line.md).
* **Abfrage-Editor**: Geben Sie `$(options:OPTION_NAME)` in das Feld **Wert** ein, um den Wert einer Option zu verwenden. Weitere Informationen finden Sie unter [&#x200B; von Abfragen](../start/design-queries.md).

## Verfügbare Optionen {#available-options}

In den folgenden Tabellen sind die in Campaign v8 verfügbaren Optionen nach Bereich gruppiert aufgeführt. Wenn auf einer anderen Seite der Dokumentation eine Option beschrieben wird, wird die Tabelle mit ihr verknüpft.

### Sendungen {#delivery-options}

Diese Optionen steuern, wie Sendungen vorbereitet und gesendet werden. Es geht dabei um Bild- und Anlagenbeschränkungen, den Standard-Routing-Provider, den Mid-Sourcing-Split-Schwellenwert, das Open-Tracking-Skript, die URL des öffentlichen Servers, die Versandgültigkeit, die Handhabung von Duplikaten und verzögerten Sendungen sowie Barcodes. Weitere Informationen finden Sie unter [Anhängen von &#x200B;](../send/attaching-files.md), [E-Mail-Parameter](../send/email-parameters.md), [Best Practices für den Versand](../start/delivery-best-practices.md), [Erste Schritte mit der Campaign-Architektur](architecture.md#split) [Anleitungen zu E-Mail-Tracking-Pixeln](../start/cnil-pixel-tracking.md) und [Senden von direkten LINE-Nachrichten](../send/line/line.md).

| Option | Beschreibung |
|---|---|
| NmsDelivery_MaxDownloadedImageSize | Maximale Größe (in Byte) eines Bildes, das von einer personalisierten URL heruntergeladen und an eine E-Mail angehängt wird. Der Standardwert ist 100.000 Byte (100 KB). [Weitere Informationen](../send/attaching-files.md) |
| NmsDelivery_MaxRecommendedAttachments | Maximale Anzahl von Anhängen in einer E-Mail- oder Transaktions-E-Mail-Vorlage, bevor eine Warnung angezeigt wird. Der Standardwert ist 1. [Weitere Informationen](../send/attaching-files.md) |
| NmsEmail_DefaultErrorAddr | Standard-Fehler-E-Mail-Adresse der Instanz, die verwendet wird, wenn der Versand die Fehleradresse leer lässt. [Weitere Informationen](../send/email-parameters.md) |
| XtkEmail_Characters | Gültige Zeichen für eine E-Mail-Adresse. [Weitere Informationen](../start/delivery-best-practices.md) |
| NmsBroadcast_DefaultProvider | Standard-Routing-Anbieter neuer Versandvorlagen. Auf den Namen eines aufgeteilten externen Kontos setzen, um den aufgeteilten Versand standardmäßig zu verwenden. [Weitere Informationen](architecture.md#split) |
| NmsDelivery_MultiMidSplitThreshold | Größe, ab der ein Versand auf mehrere Mid-Sourcing-Instanzen aufgeteilt wird Der Standardwert ist 100K. [Weitere Informationen](architecture.md#split) |
| NmsTracking_OpenFormula | Script zur Berechnung der URL für das Öffnungs-Tracking Definieren Sie eine Option pro Pixelzweck. [Weitere Informationen](../start/cnil-pixel-tracking.md) |
| NmsServer_URL | Basis-URL des öffentlichen Webanwendungsservers. Wird beispielsweise verwendet, um einen Web-App-Link in eine LINE-Nachricht einzufügen. [Weitere Informationen](../send/line/line.md) |
| NmsBroadcast_MsgValidityDuration | Standardmäßiger Gültigkeitszeitraum eines Versands in Sekunden. |
| NmsBroadcast_RemoveDuplicatesRecipients | Setzen Sie ihn auf 1 , um doppelte Empfänger automatisch zu ignorieren. |
| NmsDelivery_ImageServerTimeout | Die maximale Wartezeit in Sekunden, um eine Antwort vom Server zu erhalten, wenn ein Bild abgerufen wird, das von einer personalisierten URL heruntergeladen und an eine E-Mail angehängt wurde. Wenn die maximale Wartezeit überschritten wird, kann die Nachricht nicht gesendet werden. Der Standardwert ist 60 Sekunden. |
| NmsDeliveryWizard_ShowDeliveryWeight | Zeigt die Nachrichtengewichtung im Versand-Assistenten an. |
| nmsMTA_alert_delay | Verzögerung in Minuten, nach deren Ablauf ein Versand als verzögert gilt. Der Standardwert ist 30 Minuten. |
| NmsServer_MirrorPageUrl | URL des Mirrorseiten-Servers Dies ist der Standardwert für E-Mail-Sendungen, wenn in der Routing-Definition keine URL angegeben ist. Standardmäßig ist sie mit der Tracking-Server-URL identisch. |
| XtkBarcode_SpecialChar | Aktiviert oder deaktiviert die Unterstützung von Sonderzeichen für Code128-Barcodes. |
| XtkSecurity_Restrict_EditXML | Fügen Sie ihn mit dem Wert 0 hinzu, um die Bearbeitung des XML-Codes von Sendungen zu deaktivieren (XML-Quelle bearbeiten oder Strg+F4). |
| NMS_ActivateOwnerConfirmation | Legen Sie den Wert auf 1 fest, damit der für den Versand verantwortliche Benutzer den Versand bestätigen kann, wenn ein bestimmter Benutzer oder eine bestimmte Gruppe für den Start des Versands bestimmt ist. Legen Sie ihn auf 0 fest, um ihn zu deaktivieren: Nur der vorgesehene Benutzer bzw. die vorgesehene Gruppe oder ein Administrator kann dann den Versand bestätigen. |
| NmsDelivery_senderAddressMask | Kommagetrennte Liste der Absenderadressen, die im Feld Von E-Mail von E-Mail-Sendungen zulässig sind. Wenn die Option einen Wert hat, wird das Feld zu einer Dropdown-Liste. Diese Einschränkung gilt global für alle Marken und Versandvorlagen und unterstützt nur statische Adressen. [Weitere Informationen](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#restrict-sender-address){target="_blank"} |

### Kampagnen und Workflows {#campaign-workflow-options}

Diese Optionen steuern, wie Kampagnen und Workflows ausgeführt werden. Sie umfassen die Bestätigung eines Versands durch den Verantwortlichen, die Anzahl der gleichzeitig verarbeiteten Vorgänge sowie die Prüfung und den automatischen Neustart von Workflows. Sie umfassen auch den Schutz von SQL-Aktivitäten, die Standardgültigkeit von Kampagnen und das Logo exportierter Berichte. Weitere Informationen finden Sie unter [Sendungen von Marketing](../../automation/campaigns/marketing-campaign-deliveries.md), [Best Practices für Workflows](../../automation/workflow/workflow-best-practices.md), [Überwachen der Workflow-](../../automation/workflow/monitor-workflow-execution.md), [Workflow-Eigenschaften](../../automation/workflow/workflow-properties.md) und [SQL-Code und JavaScript-Code](../../automation/workflow/sql-code-and-javascript-code.md#important-notes).

| Option | Beschreibung |
|---|---|
| NmsCampaign_Activate_OwnerConfirmation | Erstellen Sie sie und legen Sie sie auf 1 fest, damit der/die Kampagnenverantwortliche den Versand bestätigen kann, auch wenn Validierungsverantwortliche definiert sind. Zur Deaktivierung auf 0 setzen. [Weitere Informationen](../../automation/campaigns/marketing-campaign-deliveries.md) |
| NmsOperation_LimitConcurrency | Maximale Anzahl von Versand-, Workflow-, Hypothesen- und Simulationsvorgängen, die eine Kampagne gleichzeitig verarbeitet. Der Standardwert ist 10. [Weitere Informationen](../../automation/workflow/workflow-best-practices.md) |
| NmsServer_PausedWorkflowPeriod | Anzahl der Tage zwischen zwei Prüfungen auf pausierte Workflows. [Weitere Informationen](../../automation/workflow/monitor-workflow-execution.md) |
| XtkWorkflow_WatchdogRestartTimerTimeout | Erstellen Sie sie als ganzzahlige Option, um das 30-Sekunden-Intervall zu ändern, in dem Workflows überprüft und automatisch neu gestartet werden. [Weitere Informationen](../../automation/workflow/workflow-properties.md) |
| XtkSecurity_FeatureFlag_SqlSensible | Setzen Sie ihn auf 0, um den Schutz der SQL-Code-Aktivitäten vor blockierten SQL-Methoden zu deaktivieren. [Weitere Informationen](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| XtkSecurity_SqlSensitive_Methods | Liste der SQL-Methoden, die von den SQL-Aktivitäten blockiert oder gewarnt werden. [Weitere Informationen](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| NmsOperation_Duration | Standardmäßiger Gültigkeitszeitraum einer Kampagne in Sekunden. |
| NmsOperation_TimeRange | Zeitraum für die Targeting- und Extraktionsbedingungen im geplanten Modus. |
| NmsOperation_OperationMgtDebug | Legen Sie ihn auf 1 fest, um die Ausführungsinformationen des technischen Workflows „operationMgt“ in den Workflow-Auditprotokollen zu protokollieren. |
| NmsOperation_DeliveryPreparationWindow | Die Anzahl der Tage, über die Sendungen mit einem inkonsistenten Status vom technischen Workflow operationMgt von der Anzahl der laufenden Sendungen ausgeschlossen werden. Der Standardwert ist 7. |
| workflow_analysisThreshold | Anzahl an Datensatzänderungen, die eine automatische Aktualisierung der Statistiken auslöst |
| XtkReport_Logo | Das Logo wird in der oberen rechten Ecke der exportierten Berichte angezeigt. |

### E-Mail-Standardeinstellungen {#email-default-options}

Diese Optionen definieren die standardmäßigen Absender- und Antwortadressen sowie Beschriftungen Ihrer E-Mails. Campaign verwendet sie, wenn ein Versand das entsprechende Feld leer lässt. Weitere Informationen finden Sie unter [E](../send/email-parameters.md)Mail-Parameter und [Arbeiten mit Versandvorlagen](../send/create-templates.md).

| Option | Beschreibung |
|---|---|
| NmsEmail_DefaultFromAddr | Standard-Absenderadresse der Instanz, die verwendet wird, wenn der Versand sie leer lässt. |
| NmsEmail_FromName | Standard-Absenderbezeichnung der Instanz, die verwendet wird, wenn der Versand sie leer lässt. |
| NmsEmail_DefaultReplyToAddr | Standard-Antwortadresse der Instanz, die verwendet wird, wenn der Versand sie leer lässt. |
| NmsEmail_ReplyToName | Standard-Antwortbezeichnung der Instanz, die verwendet wird, wenn der Versand sie leer lässt. |
| NmsEmail_DefaultErrorAddr | Standardmäßige Fehleradresse der Instanz, die verwendet wird, wenn der Versand sie leer lässt. [Weitere Informationen](../send/email-parameters.md) |
| NmsDelivery_FromAddressMasks | Syntax der für den Nachrichtenversand verwendeten Absenderadresse. |
| NmsDelivery_ErrorAddressMasks | Syntax der Fehleradresse für die Antwort auf eine Nachricht. |
| NmsEmail_ExpOrganization | Allgemeiner Name Ihres Unternehmens, der in einigen Warnmeldungen verwendet wird, die den Empfängern angezeigt werden. |

### Softbounces und Quarantäne {#error-options}

Diese Optionen definieren, wann ein Empfänger nach Softbounces, bei denen es sich um temporäre Versandfehler handelt, unter Quarantäne gestellt wird. Weitere Informationen finden Sie unter [Quarantäneverwaltung in Campaign](../send/quarantines.md#soft-error-management) und [Versandfehler in Campaign](../send/delivery-failures.md#retries).

| Option | Beschreibung |
|---|---|
| NmsNPAI_EmailMaxError | Maximale Anzahl an Softbounces, die im E-Mail-Kanal akzeptiert werden, bevor der Empfänger unter Quarantäne gestellt wird. |
| NmsNPAI_EmailSignificantErrorDelay | Minimale Zeit, die nach dem vorherigen Softbounce im E-Mail-Kanal vergehen muss, bevor ein neuer Softbounce berücksichtigt wird. |
| NmsNPAI_MobileMaxError | Maximale Anzahl an Softbounces, die auf dem mobilen Kanal akzeptiert werden, bevor der Empfänger unter Quarantäne gestellt wird. |
| NmsNPAI_MobileSignificantErrorDelay | Minimale Zeit, die nach dem vorherigen Softbounce auf dem Mobile-Kanal vergehen muss, bevor ein neuer Softbounce berücksichtigt wird. |

### Kanäle {#channel-options}

Diese Optionen definieren die Absenderadresse von Briefpost, die Einstellungen der LINE- und SMS-Kanäle und die zulässigen Weiterleitungsadressen eingehender E-Mails. Weitere Informationen finden Sie unter [Senden von Briefpost mit Adobe Campaign](../send/direct-mail.md), [Senden von Briefpostnachrichten mit Adobe Campaign](../send/line/line.md) und [Senden von SMS mit Adobe Campaign](../send/sms/sms.md).

| Option | Beschreibung |
|---|---|
| NmsPaper_SenderLine1, NmsPaper_SenderLine3, NmsPaper_SenderLine4, NmsPaper_SenderLine6, NmsPaper_SenderLine7 | Zeilen 1, 3, 4, 6 und 7 der Absenderadresse der Briefpost-Sendungen. |
| NmsLine_AESKey | AES-Schlüssel, der vom lineImage-Servlet zum Codieren von URLs im LINE-Kanal verwendet wird. |
| NmsLine_MessageCenterURL | Message Center-Server-URL zum Senden von Willkommensnachrichten im LINE-Kanal. |
| NmsSMS_Priority | Priorität der an das SMS-Gateway gesendeten SMS-Nachrichten. |
| NmsInMail_AllowlistEmails | Zulässige Weiterleitungs-E-Mail-Adressen des Moduls zur Verarbeitung eingehender E-Mails, durch Kommas getrennt. Verwenden Sie *, um alle Adressen zuzulassen. |

### Schwellenwerte für Message Center {#message-center-options}

Diese Optionen definieren die Schwellenwerte, die eine Warnung oder einen Warnhinweis auslösen, wenn die Verarbeitung von Echtzeit-Ereignissen, die Trigger-Transaktionsnachrichten auslösen, sich verschlechtert. Jede Metrik hat einen Warnschwellenwert und einen Warnschwellenwert. Der Optionsname endet mit „Warnung“ oder „Warnhinweis“, z. B. MC_RtEventErrorWarning und MC_RtEventErrorAlert. Weitere Informationen finden Sie unter [Einstellungen für Campaign](../send/transactional.md)Transaktionsnachrichten und [Campaign-Transaktionsnachrichten](../config/transactional-msg-settings.md).

| Präfix des Optionsnamens | Metrik |
|---|---|
| MC_RtEventAvgDeliveryTime | Durchschnittliche Sendungsdauer von Echtzeit-Ereignissen. |
| MC_RtEventAvgProcessTime | Durchschnittliche Verarbeitungszeit für Echtzeit-Ereignisse. |
| MC_RtEventAvgQueueTime | Durchschnittliche Verweildauer in der Warteschlange von Echtzeit-Ereignissen. |
| MC_RtEventAvgQueue | Durchschnittliche Anzahl der Echtzeit-Ereignisse in der Warteschlange. |
| MC_RtEventMaxQueue | Maximale Anzahl an Echtzeit-Ereignissen in der Warteschlange |
| MC_RtEventMinQueue | Minimale Anzahl an Echtzeit-Ereignissen in der Warteschlange. |
| MC_RtEventQueue | Warteschlange ausstehender Echtzeit-Ereignisse. Die Warnschwelle ist die kritische Bedingung. |
| MC_RtEventError | Verarbeitungsfehler bei Echtzeit-Ereignissen |
| MC_RtEventThroughput | Durchsatz von Echtzeit-Ereignissen. |

### Datenaufbewahrung und -datenbank {#database-options}

Der Bereinigungs-Workflow löscht alte Datensätze, um ein Wachstum der Datenbank zu verhindern. Diese Optionen legen fest, wie lange Campaign die einzelnen Datentypen speichert. Wenn Sie die Verzögerung in der Benutzeroberfläche ändern, wird automatisch eine Option „Bereinigungsverzögerung“ erstellt. Wenn Sie ihn über die Optionsliste bearbeiten, drücken Sie den Wert in Sekunden aus. Weitere Informationen finden Sie unter [Allgemeine &#x200B;](general-architecture.md) und [Sicherheitsrichtlinien](../config/security.md#consent).

| Option | Beschreibung |
|---|---|
| NmsCleanup_BroadLogPurgeDelay | Verzögerung, nach der Versandlogs (Broadlogs) gelöscht werden. |
| NmsCleanup_TrackingLogPurgeDelay | Verzögerung, nach der Trackinglogs gelöscht werden. |
| NmsCleanup_TrackingStatPurgeDelay | Verzögerung, nach der Tracking-Statistiken gelöscht werden. |
| NmsCleanup_EventPurgeDelay | Verzögerung, nach der Ereignisse gelöscht werden. |
| NmsCleanup_EventHistoPurgeDelay | Verzögerung, nach der der Ereignisverlauf gelöscht wird. |
| NmsCleanup_EventStatPurgeDelay | Verzögerung, nach der die Ereignisstatistiken gelöscht werden. |
| NmsCleanup_PropositionPurgeDelay | Zeitspanne, nach der die Vorschläge gelöscht werden. |
| NmsCleanup_QuarantineMailboxFull | Wartezeit, nach der die Quarantänen gelöscht werden. |
| NmsCleanup_RecycledDeliveryPurgeDelay | Verzögerung, nach der wiederverwertete Sendungen gelöscht werden. |
| NmsCleanup_RejectsPurgeDelay | Wartezeit, nach der Zurückweisungen gelöscht werden. |
| NmsCleanup_VisitorPurgeDelay | Wartezeit, nach der Besucher gelöscht werden. |
| NmsCleanup_WorkflowResultPurgeDelay | Verzögerung, nach der Workflow-Ergebnisse gelöscht werden. |
| XtkCleanup_NoStats | Legen Sie ihn auf 1 fest, damit der Bereinigungs-Workflow die Datenbankstatistiken nicht aktualisiert. |
| WdbcKillSessionPolicy | Verhalten beim bedingungslosen Anhalten von Workflows in PostgreSQL. 0 (Standard): Hält den Workflow-Prozess an, ohne dass sich dies auf die Datenbank auswirkt. 1: Beendet den Prozess und bricht die Abfrage ab (pg_cancel_backend). 2: Beendet den Prozess und beendet die Abfrage (pg_terminate_backend). |
| XtkSequence_AutoGeneration | Gilt für benutzerdefinierte Schemata, die nach dem Festlegen dieser Option erstellt werden, mit autopk=„true“ und ohne pkSequence-Attribut: Campaign generiert die Sequenz automatisch. |

### Anpassung des Message Centers {#message-center-customization}

Mit diesen Optionen können Sie anpassen, wie Campaign Echtzeit- und Batch-Ereignisse anreichert und weiterleitet. Weitere Informationen finden Sie unter [Einstellungen für Campaign](../send/transactional.md)Transaktionsnachrichten und [Campaign-Transaktionsnachrichten](../config/transactional-msg-settings.md).

| Option | Beschreibung |
|---|---|
| MC_EnrichmentCustomJS | JavaScript-Bibliothek, die Ereignisse anreichert. Sie muss enrichRtEvents(aiEventId) für Echtzeitereignisse und enrichBatchEvents(aiEventId) für Batch-Ereignisse implementieren. Beide Funktionen reichern die Ereignisse an und speichern sie in der Datenbank. |
| MC_RoutingCustomJS | JavaScript-Bibliothek, die Ereignisse weiterleitet. Sie muss dispatchRtEvent(iEventId) und dispatchBatchEvent(iEventId) implementieren, die den internen Namen der für das Echtzeit- oder Batch-Ereignis ausgewählten Transaktionsnachricht zurückgeben. |
| NmsMessageCenter_RoutingBatchSize | Größe der für das Ereignis-Routing verwendeten Gruppen. |
| NmsTracking_RT_ClickFormula, NmsTracking_RT_OpenFormula | Formeln, die für das Klick- und Öffnungs-Tracking von Echtzeit-Sendungen (RT) verwendet werden, wenn das Branding aktiviert ist. Sie werden auf der RT-Kontrollinstanz konfiguriert. [Weitere Informationen](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |
| Branding_RT_ListXtkOptions_toPublish | Liste der Optionen, durch Kommas getrennt, die Ihre benutzerdefinierten Tracking-Formeln enthalten, damit RT-Sendungen sie anwenden können. [Weitere Informationen](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |

### Interaction (Angebotsverwaltung) {#interaction-options}

Diese Optionen gelten für Campaign Interaction, das Modul Angebotsverwaltung . Sie steuern, wie Vorschläge geschrieben werden und wie die Kontroll- und Ausführungsinstanzen synchronisiert werden. Weitere Informationen finden [&#x200B; unter „Campaign Interaction - Angebotsverwaltung](../interaction/interaction.md) und in den [Wartungsoptionen](../interaction/interaction-architecture.md#maintenance-options) der Interaction-Architektur.

| Option | Beschreibung |
|---|---|
| NmsInteraction_UseDaemon | Setzen Sie ihn auf 1, um das asynchrone Schreiben von Vorschlägen zu aktivieren, oder auf 0, um es zu deaktivieren. |
| NmsInteraction_MapWorkflowId | Liste aller erzeugten Synchronisations-Workflows. Wartungsoption der Kontrollinstanz. |
| NmsExecutionInstanceId | Kennung der Ausführungsinstanz. Verfügbar auf Ausführungsinstanzen. |

Die folgenden Optionen sind ebenfalls Wartungsoptionen der Kontrollinstanz:

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**: Letztes Datum, an dem eine Umgebung auf einer bestimmten Instanz synchronisiert wurde.
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**: Letztes Datum, an dem die Vorschläge eines Schemas von einer Instanz zur anderen synchronisiert wurden.

>[!CAUTION]
>
>Verwenden Sie die Wartungsoptionen nur für bestimmte Wartungsfälle.

Die folgenden Optionen gelten für Gutscheine, die in Enterprise (FFDA)-Bereitstellungen nicht verfügbar sind. Weitere Informationen finden Sie unter [Personalisierte Gutscheine](../send/personalized-coupons.md).

| Option | Beschreibung |
|---|---|
| NmsModule_CouponsEnabled | Aktiviert Gutscheine. |
| NmsCoupons_MaxPerTransac | Anzahl der pro SQL-Transaktion aktualisierten Coupons. |

### Datenschutzanfragen {#privacy-options}

Diese Optionen steuern, wie Campaign Datenschutzanfragen verarbeitet, z. B. die Löschbestätigung, die Anzahl der zulässigen Fehler und wie lange Anfragedaten aufbewahrt werden. Weitere Informationen finden [&#x200B; unter „Verwalten von Datenschutzanfragen in Campaign](../start/privacy.md).

| Option | Beschreibung |
|---|---|
| Privacy_Request_ConfirmDeletePending | Legen Sie ihn in einem zweiten Schritt auf 1 fest, um jeden Löschvorgang manuell in der Benutzeroberfläche zu bestätigen. Andernfalls werden Daten ohne Bestätigung gelöscht. |
| Privacy_Request_ConfirmDeletePendingDelay | Verzögerung, nach der eine Anfrage, die auf eine Löschbestätigung wartet, storniert wird. |
| Privacy_Request_MaxErrorAllowed | Maximal zulässige Anzahl von Fehlern bei der Verarbeitung oder Löschung einer Datenschutzanfrage. |
| Datenschutz_Request_PurgeDelay | Intervall zwischen der Erstellung einer Anfrage in der Warteschlange und dem Löschen der zugehörigen Daten |
| realtimeReporting_collectPII | Auswahl der Vereinbarung über personenbezogene Daten (PII) für dynamische Berichte. Der Wert 1 entspricht „Später bitten“, 2 „Ablehnen“ und 3 „Annehmen“. [Weitere Informationen](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reporting/dynamic-reporting/pii-agreement){target="_blank"} |

### Audit-Protokoll {#audit-trail-options}

Das Audit-Protokoll zeichnet die Änderungen auf, die an Campaign-Entitäten vorgenommen wurden. Verwenden Sie diese Optionen, um sie für eine Entität zu aktivieren oder zu deaktivieren, z. B. um Speicherplatz in der Datenbank zu sparen. Legen Sie den Wert auf 1 fest, um das Audit-Protokoll zu aktivieren, und auf 0, um es zu deaktivieren. Weitere Informationen finden Sie [&#x200B; „Audit-Protokoll](../reporting/audit-trail.md#enable-disable-audit-trail).

| Option | Geprüfte Entität |
|---|---|
| XtkAudit_Workflows | Workflows |
| XtkAudit_DataSchema | Schemata |
| XtkAudit_Option | Optionen |
| XtkAudit_Delivery | Sendungen |
| XtkAudit_ExtAccount | Externe Konten |
| XtkAudit_DeliveryMapping | Versandzuordnungen |
| XtkAudit_WebApp | Webanwendungen |
| XtkAudit_Offer | Angebote |
| XtkAudit_Operator | Benutzer |
| XtkAudit_Enable_All | Alle Entitäten |

### Integrationen und Umfragen {#integration-options}

Diese Optionen speichern die Einstellungen von Integrationen und Umfragen: die Adobe Developer Console-Anmeldedaten für Landingpages, das letzte Synchronisierungsdatum der CRM-Connector-Aktivität und das standardmäßige Backup der Umfrageantworten. Weitere Informationen finden Sie unter [Aktualisieren von Adobe Experience Platform-Profilen von Adobe Campaign](../connect/ac-aep-landing-pages.md), [Datensynchronisierung mit CRM-Connectoren](../connect/crm-data-sync.md) und [Antworten verwalten](../dev/surveys/managing-answers.md).

| Option | Beschreibung |
|---|---|
| IMS_CLIENT_ID, IMS_CLIENT_SECRET, IMS_ORG_ID, IMS_CLIENT_API_KEY | Adobe Developer Console-Anmeldedaten für Landingpages mit Adobe Experience Platform. [Weitere Informationen](../connect/ac-aep-landing-pages.md) |
| LASTIMPORT_ gefolgt vom internen Namen der Instanz und dem Aktivitätsnamen | Datum der letzten Synchronisation der allgemeinen CRM-Connector-Aktivität. Erstellen Sie sie manuell als Textoption im Format `yyyy/MM/dd hh:mm:ss`. [Weitere Informationen](../connect/crm-data-sync.md) |
| NmsWebApp_XmlBackup | Erstellen Sie sie und legen Sie sie auf 1 fest, um eine Kopie der unbearbeiteten Antworten standardmäßig für alle Umfragen zu speichern. [Weitere Informationen](../dev/surveys/managing-answers.md) |
| AEMResourceTypeFilter | Typen von Adobe Experience Manager-Ressourcen, die in Campaign verwendet werden können, durch Kommas getrennt. [Weitere Informationen](../connect/ac-aem.md) |
| nmsPipeline_config | Konfiguration von Adobe Experience Cloud-Triggern im JSON-Format. Erstellen Sie sie als Langtext-Option. [Weitere Informationen](../connect/ac-triggers.md) |
| TNT_EdgeServer | Für die Integration verwendeter Adobe Target-Server, standardmäßig festgelegt. Es handelt sich um den Adobe Target-Domain-Server gefolgt von /m2, z. B. tt.omtrdc.net/m2. [Weitere Informationen](../connect/ac-at.md) |
| TNT_TENANTName | Name der Adobe Target-Organisation (Client). [Weitere Informationen](../connect/ac-at.md) |
| AAM_DataSourceId, AAM_DestinationId | Von der Integration mit Adobe Audience Manager verwendete Kennungen. [Weitere Informationen](../start/shared-audiences.md) |
| WdbcCapabilities_AzureDW | Optionen des Azure Synapse-Connectors (Azure SQL Data Warehouse). [Weitere Informationen](../connect/fda.md) |

## Verwandte Themen {#related-topics}

* [Integrierte Packages](built-in-packages.md)
* [Allgemeine Prinzipien](general-architecture.md)
* [Handbuch zum Rotieren von Anmeldeinformationen](../../technotes/security/credential-rotation-guide.md)
