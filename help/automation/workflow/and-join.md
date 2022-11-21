---
product: campaign
title: Und-Verknüpfung
description: Und-Verknüpfung
feature: Workflows
exl-id: c70a106d-3518-4eac-9944-6f7c93d85bac
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 100%

---

# Und-Verknüpfung{#and-join}



Bei einer Und-Verknüpfung wird die ausgehende Transition erst aktiviert, wenn alle eingehenden Transitionen aktiviert wurden, d. h. wenn alle vorherigen Aktivitäten abgeschlossen sind. Dadurch lässt sich sicherstellen, dass gewisse Aktivitäten beendet sind, bevor die Workflow-Ausführung fortgesetzt wird.

Beispielsweise können Sie eine Und-Verknüpfungsaktivität bei der Inhaltserstellung und Automatisierung des Versand verwenden, um sicherzustellen, dass ein Versand erst gestartet wird, wenn die Zielgruppe abgefragt und die Schritte zur Inhaltsaktualisierung abgeschlossen sind. Ein spezieller Anwendungsfall ist verfügbar unter

![](assets/and-join-usage.png)

>[!NOTE]
>
>Beachten Sie, dass eingehende Transitionen, die mit verschiedenen Zielgruppenbestimmungsdimensionen konfiguriert sind, nicht mit der Aktivität **[!UICONTROL Und-Verknüpfung]** zusammengeführt werden können.

Die an die ausgehende Transition übermittelte Population entspricht der Hauptmenge, die zuvor aus den eingehenden Transitionen der Aktivität bestimmt wurde.

Die ausgehende Transition kann nur eine der eingehenden Populationen enthalten. Wenn die Hauptmenge nicht bestimmt wurde, wird die an die ausgehende Transition übermittelte Population zufällig ausgewählt.

>[!CAUTION]
>
>Bei Verwendung einer **UND-Verknüpfung** fusionieren die Ereignisvariablen. Wenn eine Variable aber mehrmals definiert wurde, entsteht ein Konflikt und es wird ein unbestimmter Wert ausgegeben. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](javascript-scripts-and-templates.md#event-variables).
