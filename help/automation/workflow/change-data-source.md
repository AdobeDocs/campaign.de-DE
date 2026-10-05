---
title: Datenquelle ändern
description: Erfahren Sie mehr über die Aktivität "Datenquelle ändern".
feature: Workflows, Data Management, Federated Data Access
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
TQID: 'https://experienceleague.adobe.com/jpyolWAkavJVJeUJzIP9-vHt17Z20oGKZ6sG99ahQE0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ee3dfd63-9a21-4961-9f24-ea3385284a21
    internal-label: Federated Data Access
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 100%
---
# Datenquelle ändern {#change-data-source}

Verwenden Sie die Aktivität **[!UICONTROL Datenquelle ändern]**, um die Datenquelle einer [Workflow-Arbeitstabelle](use-workflow-data.md#workflow-temporary-work-table) zu ändern. Diese Aktivität bietet mehr Flexibilität bei der Verwaltung von Daten aus verschiedenen Datenquellen, z. B. Federated Data Access (FDA), Campaign-Cloud-Datenbank (FFDA) und lokale Campaign-Datenbank.

Die **[!UICONTROL Workflow-Arbeitstabelle]** wird verwendet, um Daten mit den Workflow-Aktivitäten zu verarbeiten und freizugeben.

Standardmäßig wird die **[!UICONTROL Arbeitstabelle]** in derselben Datenbank erstellt wie die Quelle der Daten, die Sie abfragen möchten.
Wenn Sie zum Beispiel die Tabelle **[!UICONTROL Empfänger]** abfragen, die in der Cloud-Datenbank gespeichert ist, erstellt der Workflow eine **[!UICONTROL Arbeitstabelle]** in derselben Cloud-Datenbank.

Verwenden Sie eine Aktivität **[!UICONTROL Datenquelle ändern]**, um eine andere Datenquelle für Ihre **[!UICONTROL Arbeitstabelle]** zu verwenden.

Beachten Sie, dass Sie bei Verwendung der Aktivität **[!UICONTROL Datenquelle ändern]** zur Cloud-Datenbank zurückkehren müssen, um die Ausführung des Workflows fortzusetzen.

>[!IMPORTANT]
>
>Beachten Sie, dass die Aktivitäten **[!UICONTROL Dimension ändern]** und **[!UICONTROL Datenquelle ändern]** nicht in einer Zeile hinzugefügt werden dürfen. Wenn Sie beide Aktivitäten nacheinander verwenden müssen, muss die Aktivität **[!UICONTROL Anreicherung]** zwischen ihnen enthalten sein. Dadurch wird eine ordnungsgemäße Ausführung sichergestellt und potenzielle Konflikte oder Fehler werden vermieden.

>[!NOTE]
>
>Die Aktivität **Datenquelle ändern** kann maximal eine Million Einträge pro Ausführung verarbeiten. Wenden Sie sich an den Adobe-Support, wenn Sie dieses Limit erhöhen möchten.

So verwenden Sie die Aktivität **[!UICONTROL Datenquelle ändern]**:

1. Erstellen Sie einen Workflow.

1. Fragen Sie Ihre ausgewählten Empfänger mit einer **[!UICONTROL Abfrage]**-Aktivität ab.

   Weitere Informationen zur Aktivität **[!UICONTROL Abfrage]** erhalten Sie auf dieser [Seite](query.md#create-a-query).

1. Fügen Sie die Aktivität **[!UICONTROL Datenquelle ändern]** hinzu.

   ![](assets/change-data-source.png)

1. Bearbeiten Sie die Aktivität **[!UICONTROL Datenquelle ändern]** und wählen Sie **[!UICONTROL Standarddatenquelle]** aus.

   Die Arbeitstabelle, die das Ergebnis Ihrer Abfrage enthält, wird dann in die standardmäßige lokale Campaign-Datenbank verschoben.

   ![](assets/change-data-source_2.png)

1. Fügen Sie eine **[!UICONTROL JavaScript-Code]**-Aktivität hinzu, um Einzeloperationen an der Arbeitstabelle durchzuführen.

   Weitere Informationen über die Aktivität **[!UICONTROL JavaScript-Code]** finden Sie auf [dieser Seite](sql-code-and-javascript-code.md#javascript-code).

1. Fügen Sie eine weitere Aktivität vom Typ **[!UICONTROL Datenquelle ändern]** hinzu, um zur Cloud-Datenbank zurückzukehren.

1. Bearbeiten Sie diese Aktivität und wählen Sie **[!UICONTROL Aktives externes FDA-Konto]** sowie das entsprechende externe Konto **[!UICONTROL Externe Datenbank]**.

   ![](assets/change-data-source_3.png)

1. Sie können den Workflow jetzt starten.
