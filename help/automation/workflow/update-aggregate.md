---
product: campaign
title: Aggregat-Update
description: Erfahren Sie mehr über die Workflow-Aktivität "Aggregat-Update".
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 100%

---

# Aggregat-Update{#update-aggregate}

Aggregate dienen Berichtszwecken und werden auf Cube-Niveau definiert. Bei der Konfiguration von Aggregaten steht die Registerkarte **[!UICONTROL Workflow]** zur Verfügung.

Weitere Informationen zu Cubes und zur Verwendung von Aggregaten in Adobe Campaign finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/designing-reports-with-cubes/about-cubes.html?lang=de){target=&quot;_blank&quot;}.


Um ein Aggregat zu aktualisieren, bearbeiten Sie die Aktivität **[!UICONTROL Aggregat-Update]** und wählen Sie den zu aktualisierenden Cube und das Aggregat aus.

Sie können eine **vollständige Aktualisierung** oder eine **teilweise Aktualisierung** durchführen.

Standardmäßig wird bei jeder Berechnung eine vollständige Aktualisierung ausgeführt. Um eine teilweise Aktualisierung zu aktivieren, wählen Sie die entsprechende Option aus und definieren Sie die Aktualisierungsbedingungen.

**Best Practices**: Die Aktivität **[!UICONTROL Planung]** kann verwendet werden, um die Aktualisierungshäufigkeit des Aggregats festzulegen.

![](assets/scheduler-and-cube-aggregate.png)
