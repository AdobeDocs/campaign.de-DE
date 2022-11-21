---
product: campaign
title: Planung
description: Erfahren Sie mehr über die Workflow-Aktivität "Planung".
feature: Workflows
exl-id: ed70d2d3-251e-4ee8-84d4-73ad03e8dd35
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 100%

---

# Planung {#scheduler}



Die **Planung** ist eine persistente Aufgabe, die ihre ausgehende Transition zum konfigurierten Zeitpunkt aktiviert.

Eine **[!UICONTROL Planung]** entspricht einem programmierten Start, daher sind die gleichen Regeln zu beachten wie für die **[!UICONTROL Start]**-Aktivität. So darf die Planung beispielsweise keine eingehende Transition aufweisen.

## Best Practices {#best-practices}

* Es wird empfohlen, Workflows nicht öfter als alle 15 Minuten auszuführen, da die Gesamtleistung des Systems beeinträchtigt werden kann und Blöcke in der Datenbank entstehen können.

* Verwenden Sie in einem Workflow nie mehr als eine **[!UICONTROL Planungs]**-Aktivität pro Verzweigung. Siehe [Verwenden von Aktivitäten](workflow-best-practices.md#using-activities).

* Die Verwendung einer Planungsaktivität kann dazu führen, dass mehrere Workflow-Ausführungen gleichzeitig vorgenommen werden. Beispielsweise kann eine Planung die Workflow-Ausführung stündlich auslösen, während die Ausführung des gesamten Workflows aber mehr als eine Stunde dauert.

   Sie können die Ausführung ggf. überspringen, wenn der Workflow bereits ausgeführt wird. Weitere Informationen hierzu, wie Sie gleichzeitige Ausführungen eines Workflows verhindern können, finden Sie auf [dieser Seite](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions).

* Beachten Sie, dass die Transition mehrere Stunden später aktiviert werden kann, wenn der Workflow eine langfristige Aufgabe ausgeführt hat, wie z. B. einen Import, oder wenn das wfserver-Modul eine bestimmte Zeit lang angehalten wurde. In diesem Fall kann es erforderlich sein, die Ausführung der von der Planung aktivierten Aufgabe auf einen bestimmten Zeitraum zu beschränken.

## Konfigurieren der Planungsaktivität {#configuring-scheduler-activity}

In der Planung wird die einmalige oder periodische Aktivierung der ausgehenden Transition geplant. Öffnen Sie hierzu die Aktivität und klicken Sie auf die Schaltfläche **[!UICONTROL Ändern...]**.

![](assets/s_user_segmentation_scheduler.png)

In den folgenden Schritten des Assistenten lassen sich die Frequenz der Ausführungen und die Gültigkeit der Aktivität festlegen. Gehen Sie wie folgt vor:

1. Kreuzen Sie die gewünschte Häufigkeit an und klicken Sie auf **[!UICONTROL Weiter]**.

   ![](assets/s_user_segmentation_scheduler2.png)

1. Geben Sie die Tage und Uhrzeit der Ausführung an. Die zur Verfügung stehenden Parameter hängen von der im ersten Schritt ausgewählten Häufigkeit ab. Wenn Sie die Aktivität mehrmals täglich aktivieren, sind folgende Optionen verfügbar:

   ![](assets/s_user_segmentation_scheduler3.png)

1. Definieren Sie im nächsten Schritt die Gültigkeit der Planung oder die maximale Anzahl an Ausführungen.

   ![](assets/s_user_segmentation_scheduler4.png)

1. Prüfen Sie im letzten Schritt die Konfiguration und klicken Sie auf **[!UICONTROL Beenden]**, um sie zu speichern.

   ![](assets/s_user_segmentation_scheduler5.png)
