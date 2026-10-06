---
product: campaign
title: Vierteljährliches Listen-Update mithilfe einer inkrementellen Abfrage
description: In diesem Anwendungsfall dient eine inkrementelle Abfrage zur automatischen Aktualisierung einer Empfängerliste.
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: eedc796a-865f-47a8-8807-5980546b8adf
TQID: 'https://experienceleague.adobe.com/0C-z3NZX9SMcI4Zl2dxUKwf4l3welUfwGQijq3H5K6A'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 100%
---
# Vierteljährliches Listen-Update mithilfe einer inkrementellen Abfrage {#quarterly-list-update}



Im folgenden Beispiel wird eine [inkrementelle Abfrage](incremental-query.md) verwendet, um eine Empfängerliste automatisch zu aktualisieren. Diese Empfangenden werden im Rahmen von saisonalen Marketing-Kampagnen angesprochen.

Da diese Kampagnen zu Beginn jeder Saison gestartet werden, um relevante sportliche Aktivitäten anzubieten, werden diese Listen jedes Quartal aktualisiert. Eine empfangende Person darf von dieser Kampagne jedoch nur einmal alle 9 Monate angesprochen werden. So können Sie die Eignungshäufigkeit der empfangenden Person strecken und Aktivitäten für verschiedene Jahreszeiten im Laufe der Jahre anbieten.

![](assets/incremental_query_example.png)

1. Erstellen Sie einen neuen Workflow und positionieren Sie eine inkrementelle Abfrage mit anschließendem Listen-Update im Diagramm.
1. Konfigurieren Sie in der Aktivität die Registerkarte **[!UICONTROL Inkrementelle Abfrage]** (wie im Abschnitt [Erstellen einer Abfrage](query.md#creating-a-query) beschrieben).
1. Wählen Sie die Registerkarte **[!UICONTROL Planung und Verlauf]** aus und geben Sie dann einen Verlauf von 270 Tagen an. Bereits angesprochene Empfangende werden im Rahmen dieser Kampagne innerhalb der nächsten 270 Tage, also ungefähr 9 Monate, nicht mehr kontaktiert.

   Klicken Sie dann auf die Schaltfläche **[!UICONTROL Ändern...]**.

1. Da die Liste jeweils zu Saisonbeginn aktualisiert werden soll, muss als Häufigkeit **[!UICONTROL Monatlich]** ausgewählt werden.
1. Wählen Sie im nächsten Bildschirm die Monate März, Juni, September und Dezember aus. Wählen Sie als Tag den 20. des Monats und geben Sie die Uhrzeit an, an der der Workflow gestartet werden soll.
1. Geben Sie abschließend den Gültigkeitszeitraum der Abfrage an. Im vorliegenden Beispiel wurde **[!UICONTROL Dauerhaft gültig]** ausgewählt.

1. Konfigurieren Sie nun die Aktivität Listen-Update (wie im Abschnitt ](list-update.md)Listen-Update[ beschrieben).

Der Workflow startet automatisch kurz vor Saisonbeginn. Die Liste wird jeweils mit den neuen Angebotsempfangenden aktualisiert.
