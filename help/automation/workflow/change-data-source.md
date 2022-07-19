---
title: Datenquelle ändern
description: Erfahren Sie mehr über die Aktivität "Datenquelle ändern".
feature: Workflows, Data Management, Federated Data Access
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 19%

---

# Datenquelle ändern {#change-data-source}

Verwenden Sie die **[!UICONTROL Datenquelle ändern]** -Aktivität zum Ändern der Datenquelle eines [Workflow-Arbeitstabelle](use-workflow-data.md#workflow-temporary-work-table). Diese Aktivität bietet mehr Flexibilität bei der Verwaltung von Daten aus verschiedenen Datenquellen, z. B. Federated Data Access (FDA), Campaign Cloud Database (FFDA) und Campaign Local Database.

Der Workflow **[!UICONTROL Arbeitstabelle]** wird verwendet, um Daten mit den Workflow-Aktivitäten zu verarbeiten und freizugeben.

Standardmäßig wird die **[!UICONTROL Arbeitstabelle]** wird in derselben Datenbank erstellt wie die Quelle der Daten, die Sie abfragen müssen.
Wenn Sie beispielsweise die **[!UICONTROL Empfänger]** in der Cloud-Datenbank gespeichert ist, erstellt der Workflow eine **[!UICONTROL Arbeitstabelle]** in derselben Cloud-Datenbank.

Verwenden Sie eine **[!UICONTROL Datenquelle ändern]** -Aktivität verwenden, um eine andere Datenquelle für Ihre **[!UICONTROL Arbeitstabelle]**.

Beachten Sie bei Verwendung der Variablen **[!UICONTROL Datenquelle ändern]** zur Cloud-Datenbank wechseln, um die Workflow-Ausführung fortzusetzen.

So verwenden Sie die **[!UICONTROL Datenquelle ändern]** -Aktivität verwenden, müssen Sie:

1. Erstellen Sie einen Workflow.

1. Fragen Sie Ihre ausgewählten Empfänger mit einer **[!UICONTROL Abfrage]**-Aktivität ab.

   Weitere Informationen zur Aktivität **[!UICONTROL Abfrage]** erhalten Sie auf dieser [Seite](query.md#create-a-query).

1. Hinzufügen einer **[!UICONTROL Datenquelle ändern]** Aktivität.

   ![](assets/change-data-source.png)

1. Bearbeiten Sie Ihre **[!UICONTROL Datenquelle ändern]** Zu wählende Aktivität **[!UICONTROL Standarddatenquelle]**.

   Die Arbeitstabelle, die das Ergebnis Ihrer Abfrage enthält, wird dann in die Standard-Datenbank Campaign Local verschoben.

   ![](assets/change-data-source_2.png)

1. Hinzufügen einer **[!UICONTROL JavaScript-Code]** -Aktivität zum Ausführen von Einzeloperationen an der Arbeitstabelle.

   Weitere Informationen über **[!UICONTROL JavaScript-Code]** -Aktivität, siehe [diese Seite](sql-code-and-javascript-code.md#javascript-code).

1. Fügen Sie eine weitere Aktivität vom Typ **[!UICONTROL Datenquelle ändern]** hinzu, um zur Cloud-Datenbank zurückzukehren.

1. Bearbeiten Sie diese Aktivität und wählen Sie **[!UICONTROL Externes aktives FDA-Konto]** und die entsprechenden **[!UICONTROL Externe Datenbank]** externes Konto.

   ![](assets/change-data-source_3.png)

1. Sie können den Workflow jetzt starten.
