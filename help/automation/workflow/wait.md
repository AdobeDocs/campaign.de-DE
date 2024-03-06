---
product: campaign
title: Warten
description: Erfahren Sie mehr über die Workflow-Aktivität "Warten".
feature: Workflows
exl-id: a9bcb214-5c87-4b26-804a-22b868905022
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 71%

---

# Warten{#wait}



In einer **Warten**-Aktivität kann eine Wartezeit von wenigen Sekunden bis hin zu mehreren Monaten definiert werden. Nach Ablauf der angegebenen Frist wird die ausgehende Transition aktiviert. Diese Aktivität betrifft nicht den gesamten Workflow, andere Aufgaben können parallel ausgeführt werden.

Im Editor werden der Titel und die Wartezeit angegeben, wie unten abgebildet:

![](assets/edit_wait.png)

Im Feld **[!UICONTROL Dauer]** können, wenn in den regionalen Parametern des Benutzers nicht anders angegeben, folgende Einheiten verwendet werden:

* **s** für Sekunden, **m** für Minuten, **h** für Stunden, **d** für Tage und **y** für Jahre. Sobald die Eingabe validiert wird, wird der Wert in die am besten lesbare Einheit umgewandelt.

  Die Standardeinheit ist **T** für Tag.

* Wenn beispielsweise die regionalen Gegebenheiten auf &quot;Français&quot; gesetzt werden, **s** für Sekunden, **mn** für Minuten, **h** für Stunden, **j** für Tage, **m** für Monate, **a** für Jahre. Zum Zeitpunkt der Validierung wird der Wert automatisch in die am besten lesbare Einheit konvertiert, wie im obigen Beispiel **90 s** wurde in **1 min 30 s**.

  Die Standardeinheit ist **T** für Tag.
