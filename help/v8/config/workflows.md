---
title: Verwalten und Automatisieren von Prozessen mit Adobe Campaign-Workflows
description: Erste Schritte mit Workflows
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 93%

---

# Erste Schritte mit Workflows{#gs-with-workflows}

Konfigurieren Sie Campaign, um leistungsstarke Automatisierungsfunktionen für Marketing-Kampagnen zu nutzen.

Sie können Folgendes einrichten:

* Workflows
* Wiederkehrende Kampagnen
* End-to-End-Validierungszyklus
* Warnhinweise
* Automatisches Senden von Berichten
* Erzeugte Ereignisse

>[!NOTE]
>
>Die Web-Benutzeroberfläche von Adobe Campaign enthält eine überarbeitete Arbeitsfläche für Workflows, mit der dynamischere und personalisiertere Kunden-Journey erstellt werden können. Weitere Informationen zu Workflows für die Web-Benutzeroberfläche finden Sie in der [Dokumentation zur Campaign Web-Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/campaign-web/v8/wf/gs-workflows){target=_blank}.


## Entwerfen und Verwenden von Workflows {#gs-ac-wf}

Verwenden Sie Adobe Campaign-Workflows, um jeden Aspekt Ihrer Marketing-Kampagnen zu beschleunigen und zu skalieren – von der Erstellung von Segmenten über die Vorbereitung von Nachrichten bis hin zum Versand.

Weitere Informationen zur Benutzeroberfläche und Ausführung von Workflows finden Sie auf diesen Seiten: 

* [Erste Schritte mit Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=de){target="_blank"}

* [Best Practices bei Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=de){target="_blank"}

* [Integrierte technische Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=de){target="_blank"}

* [Überwachen der Ausführung von Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=de){target="_blank"}

* [Erstellen einer Zielgruppe im Workflow einer Marketing-Kampagne](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=de){target="_blank"}

## Workflow-Aktivitäten {#wf-activities}

Weitere Informationen über die verfügbaren Workflow-Aktivitäten finden Sie in [diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html?lang=de){target="_blank"}.

Workflow-Aktivitäten sind in Kategorien gruppiert. Diese vier Aktivitätskategorien sind verfügbar:

* [Zielgruppenbestimmungsaktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=de){target="_blank"}: Abfrage, Lesen von Listen, Anreicherung, Vereinigung und mehr
* [Flusssteuerungs-Aktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=de){target="_blank"}: Planung, Verzweigung, Warnhinweis, externes Signal und mehr
* [Aktionsaktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=de){target="_blank"}: Kanalübergreifende Sendungen, JavaScript-Code, CRM-Aktivitäten, Aggregat aktualisieren und mehr
* [Ereignisaktivitäten](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=de){target="_blank"}: Dateiübertragung, HTTP-Übertragung und mehr

<!--
### Change data source activity {#change-data-source-activity}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. This provides more flexibility to manage data across different data sources such as FDA, FFDA and local database.

The **[!UICONTROL Working table]** allows Adobe Campaign workflow to handle data and share data with the workflow activities.
By default, the **[!UICONTROL Working table]** is created in the same database as the source of the data we query on.

For example, when querying the **[!UICONTROL Profiles]** table, stored on the Cloud database, you will create a **[!UICONTROL Working table]** on the same Cloud database.
To change this, you can add the **[!UICONTROL Change Data Source]** activity to choose a different data source for your **[!UICONTROL Working table]**.

Note that when using the **[!UICONTROL Change Data Source]** activity, you will need to switch back to the Cloud database to continue the workflow execution.

To use the **[!UICONTROL Change Data Source]** activity:

1. Create a workflow.

1. Query your targeted recipients with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=de){target="_blank"}.

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

    For more information on the **[!UICONTROL JavaScript code]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html?lang=de){target="_blank"}.

1. Add another **[!UICONTROL Change data source]** activity to switch back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. You can now start your workflow.
-->

## Verwalten von virtuellen Warehouses {#warehouse}

Nach der Erstellung Ihres Workflows haben Sie mit der Schaltfläche **[!UICONTROL Eigenschaften]** Zugriff auf weitere Konfigurationen.

Weitere Informationen über **Workflow-Eigenschaften** finden Sie auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html?lang=de){target="_blank"}.

Auf der Registerkarte **[!UICONTROL Ausführung]** in den **[!UICONTROL Eigenschaften]** Ihres Workflows können Sie Ihren Workflow mit verschiedenen Warehouses verknüpfen und die Verwaltung Ihres Arbeitsaufkommens optimieren. Lesen Sie für weiterführende Informationen über **Warehouses** die [Snowflake-Dokumentation](https://docs.snowflake.com/en/user-guide/warehouses-overview.html){target="_blank"}.

![](assets/warehouse.png)

Je nach Zweck Ihres Workflows können Sie in der Dropdown-Liste **[!UICONTROL Warehouse]** zwischen den folgenden drei Warehouses wählen:

* **[!UICONTROL Standard]**/**[!UICONTROL Kampagne]**: wird bei der Erstellung eines neuen Workflows standardmäßig eingestellt.

* **[!UICONTROL Import/Export]**: sollte mit Import- oder Export-Workflows festgelegt werden, um die Performance Ihrer Aktivitäten zu optimieren.

* **[!UICONTROL Kampagnen-Burst]**: sollte mit Kampagnen- oder Versand-Workflows eingestellt werden, um die Verarbeitungszeit für Sendungen zu optimieren.

>[!NOTE]
>
>Das **[!UICONTROL System]**-Warehouse wird nur für integrierte Workflows festgelegt.

## Einrichten wiederkehrender Kampagnen

Entwerfen Sie einen wiederkehrenden Workflow und erstellen Sie bei jeder Workflow-Ausführung eine neue Versandinstanz. Wenn der Workflow beispielsweise einmal pro Woche ausgeführt werden soll, führt dies nach einem Jahr zu 52 Sendungen. Das bedeutet auch, dass die Protokolle für jede Versandinstanz getrennt erstellt werden.

Auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=de){target="_blank"} erfahren Sie, wie Sie eine wiederkehrende Kampagne erstellen.


## Erzeugte Ereignisse nutzen

Verwenden Sie Transaktionsnachrichten in Campaign, um Nachrichten zu automatisieren, die von durch Informationssysteme ausgelösten Ereignissen generiert werden. Diese Transaktionsnachrichten können z. B. Rechnungen, Auftragsbestätigungen, Versandbestätigungen, Passwortänderungen, Benachrichtigungen über die Nichtverfügbarkeit von Produkten, Kontoauszüge oder die Erstellung von Website-Konten sein. Diese Nachrichten können einzeln oder in Batches per E-Mail, SMS oder Push-Benachrichtigungen gesendet werden.

Weitere Informationen zu den Funktionen von Transaktionsnachrichten finden Sie in [diesem Abschnitt](../send/transactional.md).

Verbinden Sie Adobe Campaign und Adobe Analytics, um Benutzeraktionen abzurufen und nahezu in Echtzeit personalisierte Nachrichten zu versenden.

In [diesem Abschnitt](../start/connect.md) erfahren Sie, wie Sie Campaign mit anderen Lösungen integrieren.


## End-to-End-Anwendungsfälle von Workflows{#end-to-end-uc}

Erfahren Sie mehr über Anwendungsfälle, die Funktionen von Campaign-Workflows nutzen [in diesem Abschnitt](../../automation/workflow/workflow-use-cases.md).
