---
product: campaign
title: Wiederkehrender Versand
description: Erfahren Sie mehr über die Workflow-Aktivität "Wiederkehrender Versand".
feature: Workflows
role: User, Data Engineer
version: Campaign v8, Campaign Classic v7
exl-id: 27308b0d-cbfc-4bc6-9061-d771ceac95fd
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: ht
source-wordcount: '266'
ht-degree: 100%

---

# Wiederkehrender Versand{#recurring-delivery}



Ein **[!UICONTROL wiederkehrender Versand]** dient der Konfiguration einer Versandvorlageninstanz im Rahmen einer Kampagne.

![](assets/do-not-localize/how-to-video.png) [Funktion im Video kennenlernen](#recurring-delivery-video).

Diese Aktivität ist nur im Tab **[!UICONTROL Zielbestimmungen und Workflows]** von Kampagnen verfügbar.

Gehen Sie dazu wie folgt vor:

1. Wählen Sie die Versandvorlage aus, auf der die Aktivität basieren soll.

   ![](assets/recurring_delivery_001.png)

1. Konfigurieren Sie die Versandvorlage.

Die im Konfigurationsprozess dieser Aktivität zur Verfügung stehenden Optionen entsprechen denen einer Versandvorlage.

Ein Anwendungsbeispiel für diese Aktivität finden Sie in diesem [Abschnitt](send-a-birthday-email.md#creating-a-recurring-delivery-in-a-targeting-workflow).

## Einrichten eines wiederkehrenden Versands

Ein **wiederkehrender Versand** erstellt bei jeder Ausführung eine neue Versandinstanz. Wenn der Workflow beispielsweise einmal pro Woche ausgeführt werden soll, führt dies nach einem Jahr zu 52 Sendungen. Dies bedeutet auch, dass das Broadlog und die Trackinglogs je Versandinstanz getrennt sind.

![Wiederkehrender Versand](assets/delivery_recurring.jpg)

Wenn Sie die Ausführung eines wiederkehrenden Versands stoppen möchten, sollten Sie die Kampagne vollständig abbrechen oder den Workflow, mit dem sie ausgeführt wird, stoppen. Das Stoppen des Versands über das Kampagnen-Dashboard stoppt nur den aktuellen Versand, die nächsten Instanzen des wiederkehrenden Versands werden jedoch weiterhin bei jeder Workflow-Ausführung erstellt.

>[!NOTE]
>
>Die Durchführung von Testsendungen ist in der Aktivität **[!UICONTROL Wiederkehrender Versand]** nicht möglich.
> 
>Nutzen Sie zur direkten Erstellung von Sendungen in Kampagnen-Workflows die vorkonfigurierten kanalspezifischen Versandaktionen, wie z. B. **[!UICONTROL E-Mail-Versand]**.

## Anleitungsvideo (#recurring-delivery-video)

In diesem Video wird das Konfigurieren eines wiederkehrenden Versands und einer Planungsaktivität erläutert.

>[!VIDEO](https://video.tv.adobe.com/v/30201?quality=12&captions=ger)

Weitere Anleitungsvideos zu Campaign finden Sie [hier](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html?lang=de){target="_blank"}.
