---
product: campaign
title: Start und Ende
description: Erfahren Sie mehr über die Workflow-Aktivitäten "Start" und "Ende".
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 1de622bc-967b-403b-86e0-2ad32cb432e3
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 21%

---

# Start und Ende{#start-and-end}



Mit **[!UICONTROL Start]** und **[!UICONTROL End]**-Aktivitäten können Sie den Start und das Ende eines Workflows grafisch markieren. Diese Aktivitäten haben keine funktionalen Auswirkungen und sind daher optional.

* **[!UICONTROL Starten]**

  Die Ausführung eines Workflows beginnt mit Aktivitäten ohne eingehende Transition oder mit einer Beginnaktivität.

  ![](assets/s_user_segmentation_start_stop.png)

* **[!UICONTROL Ende]**

  Sie können die Aktivität **[!UICONTROL Ende]** so konfigurieren, dass alle laufenden Aufgaben unterbrochen werden. Doppelklicken Sie dazu auf die Aktivität, um deren Eigenschaften anzuzeigen, und aktivieren Sie die entsprechende Option.

  ![](assets/s_user_segmentation_end.png)

  Die Daten in der Arbeitstabelle werden automatisch gelöscht, wenn die Endaktivität aktiviert ist. Wenn dies nicht erforderlich ist, können Sie zur Vermeidung unnötiger Lasten die Transition bei der letzten Aktivitätsausgabe deaktivieren. Wenn beispielsweise an einer Versandausgabe kein Prozess geplant ist, deaktivieren Sie die entsprechende Option wie unten dargestellt:

  ![](assets/s_advuser_delivery_option_no_output.png)
