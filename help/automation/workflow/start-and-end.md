---
product: campaign
title: Start und Ende
description: Erfahren Sie mehr über die Workflow-Aktivitäten "Start" und "Ende".
feature: Workflows
exl-id: 1de622bc-967b-403b-86e0-2ad32cb432e3
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 100%

---

# Start und Ende{#start-and-end}



**[!UICONTROL Beginn]**- und **[!UICONTROL Ende]**-Aktivitäten markieren grafisch den Anfangs- bzw. Endpunkt eines Workflows. Sie haben keine funktionale Auswirkung und sind daher optional.

* **[!UICONTROL Starten]**

  Die Ausführung eines Workflows beginnt mit Aktivitäten ohne eingehende Transition oder mit einer Beginnaktivität.

  ![](assets/s_user_segmentation_start_stop.png)

* **[!UICONTROL Ende]**

  Das **[!UICONTROL Ende]** kann dahingehend konfiguriert werden, dass es alle laufenden Aufgaben unterbricht. Öffnen Sie hierzu die Aktivität und kreuzen Sie die entsprechende Option an.

  ![](assets/s_user_segmentation_end.png)

  Die Daten der Arbeitstabelle werden automatisch gelöscht, sobald die Endeaktivität aktiviert wird. Sollte dies nicht erforderlich sein und um eine unnötige Inanspruchnahme von Ressourcen zu vermeiden, kann die ausgehende Transition der letzten Workflow-Aktivität deaktiviert werden. Wenn beispielsweise ein Versand die letzte Aktivität eines Workflows ist, können Sie, wie unten abgebildet, die entsprechende Option deaktivieren:

  ![](assets/s_advuser_delivery_option_no_output.png)
