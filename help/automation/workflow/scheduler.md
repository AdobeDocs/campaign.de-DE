---
product: campaign
title: Planung
description: Erfahren Sie mehr über die Workflow-Aktivität "Planung".
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ed70d2d3-251e-4ee8-84d4-73ad03e8dd35
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: ht
source-wordcount: '400'
ht-degree: 100%

---

# Planung {#scheduler}



Die **Planung** ist eine persistente Aufgabe, die ihre ausgehende Transition zum konfigurierten Zeitpunkt aktiviert.

Eine **[!UICONTROL Planung]** entspricht einem programmierten Start, daher sind die gleichen Regeln zu beachten wie für die **[!UICONTROL Start]**-Aktivität. So darf die Planung beispielsweise keine eingehende Transition aufweisen.

## Best Practices {#best-practices}

**Workflow nach Änderung der Zeit der Planung neu starten**: Wenn die geplante Zeit der Aktivität **[!UICONTROL Planung]** geändert wird, muss der Workflow neu gestartet werden. Dadurch wird sichergestellt, dass der Workflow zu den aktualisierten Zeiten ausgeführt wird. Ohne Neustart wird der Workflow weiterhin gemäß dem alten Zeitplan ausgeführt.

**Häufigkeit der Planung begrenzen**: Vermeiden Sie es, Workflows so zu planen, dass sie häufiger als alle 15 Minuten ausgeführt werden. Eine häufigere Ausführung kann die Systemleistung beeinträchtigen und zu einer Überlastung der Datenbank führen.

**Eine Planung pro Verzweigung verwenden**: Jede Verzweigung Ihres Workflows sollte nur eine Aktivität vom Typ **[!UICONTROL Planung]** aufweisen. Weitere Informationen zu den Best Practices für die Verwendung von Aktivitäten in Workflows finden Sie auf der Seite [Best Practices bei Workflows](workflow-best-practices.md#using-activities).

**Gleichzeitige Ausführungen von Workflows verhindern**: Wenn ein Workflow von einer Planung ausgelöst wird, sollten Sie beachten, dass mehrere Instanzen des Workflows gleichzeitig ausgeführt werden können. Wenn der Workflow beispielsweise stündlich von einer Planung ausgelöst wird, die Ausführung des Workflows jedoch länger als eine Stunde dauert, kann es zu Überschneidungen bei den Ausführungen kommen. Um dies zu vermeiden, sollten Sie Prüfungen einrichten, um mehrere gleichzeitige Ausführungen zu verhindern. [Erfahren Sie, wie Sie die gleichzeitige Ausführung mehrerer Workflows verhindern können](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions).

**Konto für verzögerte Transitionen**: Von der Planung ausgelöste Transitionen können verzögert werden, wenn der Workflow lange andauernde Aufgaben ausführt (z. B. Importe) oder wenn das Modul „wfserver“ vorübergehend angehalten wurde. Um dies zu verhindern, beschränken Sie die Aktivierungszeiten der Planung, um sicherzustellen, dass die Aufgaben innerhalb eines festgelegten Zeitfensters ausgeführt werden.

## Konfigurieren der Planungsaktivität {#configuring-scheduler-activity}

Die Planung definiert die Aktivierungsplanung der Transition. Doppelklicken Sie zur Konfiguration auf das grafische Objekt und klicken Sie auf **[!UICONTROL Ändern...]**

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
