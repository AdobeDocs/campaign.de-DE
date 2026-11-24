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
source-git-commit: 2c6140065272892d40ad66da0c0c89dfe169ce19
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 5%
---
# Kampagnenoptionen {#campaign-options}

Optionen sind Parameter, die steuern, wie sich Ihre Campaign-Instanz verhält, z. B. die Standardgrößenbeschränkung von Bildern in E-Mails, die Anzahl der gleichzeitig ausgeführten Workflows oder der standardmäßige Routing-Anbieter von Versandvorlagen. Einige Optionen sind integriert und andere werden bei Bedarf erstellt. Die verfügbaren Optionen hängen von den auf Ihrer Instanz installierten Paketen ab. Weitere Informationen finden [&#x200B; unter „Integrierte Pakete](built-in-packages.md).

>[!CAUTION]
>
>Ändern Sie nur die in der Campaign-Dokumentation dokumentierten Optionen und nur die hier beschriebenen. Nicht dokumentierte Optionen sind intern und dürfen nicht geändert werden. Das Ändern von Optionen ist erfahrenen Benutzern vorbehalten.

## Wo Optionen gespeichert werden {#where-options-are-stored}

Optionen werden in der Campaign-Datenbank in der Tabelle **xtkOption** gespeichert (Schema **xtk:option**). Im Campaign-Explorer sind sie unter **[!UICONTROL Administration]** > **[!UICONTROL Plattform]** > **[!UICONTROL Optionen]** verfügbar.

## Verwenden von Optionen {#use-options}

1. Navigieren Sie im Campaign-Explorer zu **[!UICONTROL Administration]** > **[!UICONTROL Plattform]** > **[!UICONTROL Optionen]**.
1. Wählen Sie die Option aus und aktualisieren Sie dann ihren Wert. Wenn die Option nicht vorhanden ist, erstellen Sie sie mit dem genauen Namen, der in der Dokumentation angegeben ist.
1. Legen Sie einen Wert des Typs fest, den die Dokumentation erwartet. Beispielsweise eine Textoption für das CRM-Synchronisierungsdatum oder eine Ganzzahloption für die Verzögerung des Workflow-Neustarts.

Einige Optionen verfügen über Anmeldeinformationen. Verschlüsseln Sie geheime Daten mit der `cryptString`, wie unter [Arbeiten mit Campaign- und Adobe Experience Platform-Landingpages“ beschrieben](../connect/ac-aep-landing-pages.md). Drehen Sie beim Drehen von Anmeldeinformationen auch die in Optionen gespeicherten Anmeldeinformationen. Weitere Informationen finden Sie im [Handbuch zur Berechtigungs-Rotation](../../technotes/security/credential-rotation-guide.md#ac-options-credentials).

## Dokumentierte Optionen für Campaign v8 {#documented-options}

In der folgenden Tabelle sind die Optionen aufgeführt, zu deren Verwendung Sie in der Dokumentation zu Campaign v8 aufgefordert werden. Außerdem ist ein Link zu der Seite aufgeführt, auf der die Vorgehensweise beschrieben wird.

### Sendungen {#delivery-options}

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

### Kampagnen und Workflows {#campaign-workflow-options}

| Option | Beschreibung |
|---|---|
| NmsCampaign_Activate_OwnerConfirmation | Erstellen Sie sie und legen Sie sie auf 1 fest, damit der/die Kampagnenverantwortliche den Versand bestätigen kann, auch wenn Validierungsverantwortliche definiert sind. Zur Deaktivierung auf 0 setzen. [Weitere Informationen](../../automation/campaigns/marketing-campaign-deliveries.md) |
| NmsOperation_LimitConcurrency | Maximale Anzahl von Versand-, Workflow-, Hypothesen- und Simulationsvorgängen, die eine Kampagne gleichzeitig verarbeitet. Der Standardwert ist 10. [Weitere Informationen](../../automation/workflow/workflow-best-practices.md) |
| NmsServer_PausedWorkflowPeriod | Anzahl der Tage zwischen zwei Prüfungen auf pausierte Workflows. [Weitere Informationen](../../automation/workflow/monitor-workflow-execution.md) |
| XtkWorkflow_WatchdogRestartTimerTimeout | Erstellen Sie sie als ganzzahlige Option, um das 30-Sekunden-Intervall zu ändern, in dem Workflows überprüft und automatisch neu gestartet werden. [Weitere Informationen](../../automation/workflow/workflow-properties.md) |
| XtkSecurity_FeatureFlag_SqlSensible | Setzen Sie ihn auf 0, um den Schutz der SQL-Code-Aktivitäten vor blockierten SQL-Methoden zu deaktivieren. [Weitere Informationen](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| XtkSecurity_SqlSensitive_Methods | Liste der SQL-Methoden, die von den SQL-Aktivitäten blockiert oder gewarnt werden. [Weitere Informationen](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |

### E-Mail-Standardeinstellungen {#email-default-options}

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

| Option | Beschreibung |
|---|---|
| NmsNPAI_EmailMaxError | Maximale Anzahl an Softbounces, die im E-Mail-Kanal akzeptiert werden, bevor der Empfänger unter Quarantäne gestellt wird. |
| NmsNPAI_EmailSignificantErrorDelay | Minimale Zeit, die nach dem vorherigen Softbounce im E-Mail-Kanal vergehen muss, bevor ein neuer Softbounce berücksichtigt wird. |
| NmsNPAI_MobileMaxError | Maximale Anzahl an Softbounces, die auf dem mobilen Kanal akzeptiert werden, bevor der Empfänger unter Quarantäne gestellt wird. |
| NmsNPAI_MobileSignificantErrorDelay | Minimale Zeit, die nach dem vorherigen Softbounce auf dem Mobile-Kanal vergehen muss, bevor ein neuer Softbounce berücksichtigt wird. |

Erfahren Sie mehr über Softbounces und Quarantänen in [Versandfehler](../send/delivery-failures.md).

### Schwellenwerte für Message Center {#message-center-options}

Jede Echtzeit-Ereignismetrik hat einen Warnschwellenwert und einen Warnschwellenwert. Der Optionsname endet mit „Warnung“ oder „Warnhinweis“, z. B. MC_RtEventErrorWarning und MC_RtEventErrorAlert. Erfahren Sie mehr über Transaktionsnachrichten in [Campaign-Transaktionsnachrichten](../send/transactional.md).

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

### Datenschutzanfragen {#privacy-options}

| Option | Beschreibung |
|---|---|
| Privacy_Request_ConfirmDeletePending | Legen Sie ihn in einem zweiten Schritt auf 1 fest, um jeden Löschvorgang manuell in der Benutzeroberfläche zu bestätigen. Andernfalls werden Daten ohne Bestätigung gelöscht. |
| Privacy_Request_ConfirmDeletePendingDelay | Verzögerung, nach der eine Anfrage, die auf eine Löschbestätigung wartet, storniert wird. |
| Privacy_Request_MaxErrorAllowed | Maximal zulässige Anzahl von Fehlern bei der Verarbeitung oder Löschung einer Datenschutzanfrage. |
| Datenschutz_Request_PurgeDelay | Intervall zwischen der Erstellung einer Anfrage in der Warteschlange und dem Löschen der zugehörigen Daten |

Weitere Informationen zu Datenschutzanfragen finden Sie unter [Verwalten von &#x200B;](../start/privacy.md)).

### Audit-Protokoll {#audit-trail-options}

Legen Sie eine Audit-Protokoll-Option auf 1 fest, um das Audit-Protokoll für eine Entität zu aktivieren, oder auf 0, um sie zu deaktivieren: XtkAudit_Workflows, XtkAudit_DataSchema, XtkAudit_Option, XtkAudit_Delivery, XtkAudit_ExtAccount, XtkAudit_DeliveryMapping, XtkAudit_WebApp, XtkAudit_Offer, XtkAudit_Operator. Verwenden Sie XtkAudit_Enable_All für jede Entität. Weitere Informationen finden Sie [&#x200B; „Audit-Protokoll](../reporting/audit-trail.md#enable-disable-audit-trail).

### Integrationen und Umfragen {#integration-options}

| Option | Beschreibung |
|---|---|
| IMS_CLIENT_ID, IMS_CLIENT_SECRET, IMS_ORG_ID, IMS_CLIENT_API_KEY | Adobe Developer Console-Anmeldedaten für Landingpages mit Adobe Experience Platform. [Weitere Informationen](../connect/ac-aep-landing-pages.md) |
| LASTIMPORT_<instance>_<activity> | Datum der letzten Synchronisation der allgemeinen CRM-Connector-Aktivität. Erstellen Sie sie manuell als Textoption im Format `yyyy/MM/dd hh:mm:ss`. [Weitere Informationen](../connect/crm-data-sync.md) |
| NmsWebApp_XmlBackup | Erstellen Sie sie und legen Sie sie auf 1 fest, um eine Kopie der unbearbeiteten Antworten standardmäßig für alle Umfragen zu speichern. [Weitere Informationen](../dev/surveys/managing-answers.md) |

## Verwandte Themen {#related-topics}

* [Integrierte Packages](built-in-packages.md)
* [Allgemeine Prinzipien](general-architecture.md)
* [Handbuch zum Rotieren von Anmeldeinformationen](../../technotes/security/credential-rotation-guide.md)
