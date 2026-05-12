---
product: campaign
title: Und-Verknüpfung
description: Und-Verknüpfung
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: c70a106d-3518-4eac-9944-6f7c93d85bac
TQID: https://experienceleague.adobe.com/1ChXl3Rlm93ftFFaD7Z-PcoO7CwUcxRHm2JdCFzIOZs
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 195
ht-degree: 72%

---

# Und-Verknüpfung{#and-join}



Ein Join gibt seine ausgehende Transition nur dann an, wenn alle eingehenden Transitionen aktiviert wurden, d. h. wenn alle vorherigen Aktivitäten abgeschlossen sind. Auf diese Weise können Sie sicherstellen, dass bestimmte Aktivitäten abgeschlossen sind, bevor Sie mit der Ausführung des Workflows fortfahren.

Beispielsweise können Sie eine Und-Verknüpfungsaktivität bei der Inhaltserstellung und Automatisierung des Versand verwenden, um sicherzustellen, dass ein Versand erst gestartet wird, wenn die Zielgruppe abgefragt und die Schritte zur Inhaltsaktualisierung abgeschlossen sind. Ein spezieller Anwendungsfall ist verfügbar unter

![](assets/and-join-usage.png)

>[!NOTE]
>
>Beachten Sie, dass eingehende Transitionen, die mit verschiedenen Zielgruppendimensionen konfiguriert sind, nicht mit der Aktivität **[!UICONTROL Und-Verknüpfung]** zusammengeführt werden können.

Die an die ausgehende Transition übermittelte Population entspricht der Hauptmenge, die zuvor aus den eingehenden Transitionen der Aktivität bestimmt wurde.

Die ausgehende Transition darf nur eine der Populationen der eingehenden Transition enthalten. Wenn die Aktivität nicht konfiguriert ist, wählt die ausgehende Transition nach dem Zufallsprinzip eine der Eingangspopulationen aus.

>[!CAUTION]
>
>Bei Verwendung einer **UND-Verknüpfung** werden die Ereignisvariablen zusammengeführt. Wenn eine Variable aber mehrmals definiert wurde, entsteht ein Konflikt und es wird ein unbestimmter Wert ausgegeben. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](javascript-scripts-and-templates.md#event-variables).
