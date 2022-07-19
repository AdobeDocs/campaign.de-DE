---
product: campaign
title: Kanalübergreifender Versand
description: Weitere Informationen zu kanalübergreifenden Sendungen.
feature: Workflows, Channels Activity
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 62%

---

# Kanalübergreifender Versand{#cross-channel-deliveries}

Auf kanalübergreifende Sendungen kann auf der Registerkarte **[!UICONTROL Sendungen]** von Kampagnen-Workflows zugegriffen werden.[](campaign-workflows.md)

Wählen Sie die Vorlage aus, auf der der Versand basieren soll, und definieren Sie ihre Inhalte.

Die Zielgruppe des Versands kann mithilfe der verschiedenen dedizierten Zielgruppenbestimmungs-Aktivitäten vorab im Workflow definiert werden.

Im folgenden Beispiel erfahren Sie, wie Sie einen Workflow erstellen, um eine E-Mail oder eine SMS an Abonnenten einer Push-Benachrichtigung und eine Push-Benachrichtigung eine Woche später zu senden. Gehen Sie dazu wie folgt vor:

1. Erstellen Sie eine Kampagne.
1. Im **[!UICONTROL Zielbestimmungen und Workflows]** im Tab Ihrer Kampagne eine **[!UICONTROL Abfrage]** Aktivität.
1. Konfigurieren Sie Ihre Abfrage: Wählen Sie als Zieldimension die Empfänger aus, die Push-Benachrichtigungen abonniert haben.

   >[!NOTE]
   >
   >Verwenden Sie für Push-Benachrichtigungen die Zieldimension **Abonnierte Anwendungen**.

   ![](assets/cross_channel_delivery_1.png)

1. Fügen Sie Ihrer Abfrage die Filterbedingungen hinzu. In unserem Fall wählen wir Empfänger aus, die eine Mobiltelefonnummer oder E-Mail-Adresse besitzen.

   ![](assets/cross_channel_delivery_2.png)

1. Fügen Sie Ihrem Workflow eine **[!UICONTROL Aufspaltung]** hinzu, um Empfänger in Besitzer einer Mobiltelefonnummer und in Besitzer einer E-Mail-Adresse zu unterteilen.
1. Wählen Sie im Tab **[!UICONTROL Versand]** für jeden Zieldatensatz einen Versand.

   Erstellen Sie Ihren Versand auf die gleiche Weise wie mit einem klassischen Versand-Assistenten, indem Sie in Ihrem Workflow auf die Versandaktivität doppelklicken. Weitere Informationen hierzu finden Sie in diesem .

   ![](assets/cross_channel_delivery_3.png)

1. Fügen Sie eine **[!UICONTROL Warten]**-Aktivität hinzu und konfigurieren Sie sie, damit die Empfänger nicht zu viele Sendungen gleichzeitig erhalten.
1. Fügen Sie eine **[!UICONTROL Aufspaltung]** hinzu, um Abonnenten in Anwender von iOS- und Android-Apps zu unterteilen.

   Wählen Sie für jedes Betriebssystem einen Dienst aus. Weiterführende Informationen zur Erstellung von Diensten finden Sie in diesem .

   ![](assets/cross_channel_delivery_4.png)

1. Wählen Sie für jedes Betriebssystem einen Versand über eine mobile App aus und konfigurieren Sie ihn.

   ![](assets/cross_channel_delivery_5.png)
