---
product: campaign
title: Externes Signal
description: Erfahren Sie mehr über die Workflow-Aktivität "Externes Signal".
feature: Workflows
role: User
exl-id: 45cb95ec-77bf-4bab-895f-b94f6ce660fd
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 78%

---

# Externes Signal{#external-signal}



Ein **Externes Signal** löst die Ausführung einer Reihe von Aufgaben innerhalb eines Workflows aus.

Wenn eine Aufgabe „Externes Signal“ aktiviert wird, wird sie unbegrenzt oder bis zum Ende des angegebenen Zeitraums ausgesetzt. Ihre Transition wird durch den SOAP-Aufruf **PostEvent(sessionToken, workflowId, activity, transitions, parameters, complete) aktiviert.** Der **[!UICONTROL complete]**-Parameter ermöglicht die Fertigstellung der Aufgabe, damit sie nicht mehr auf nachfolgende Aufrufe reagiert.

Weiterführende Hinweise zu SOAP-Aufrufen und der PostEvent-Funktion finden Sie in der einschlägigen Online-Literatur.

Sie können diese Aktivität konfigurieren, um Ereignisse zu definieren, wenn kein Signal empfangen wird. Bearbeiten Sie dazu die Aktivität und klicken Sie auf die Schaltfläche **[!UICONTROL Gültigkeit]** Tabulator. Klicken Sie auf die Schaltfläche **[!UICONTROL Einfügen]** Schaltfläche zum Erstellen und Konfigurieren eines Ereignisses.

![](assets/edit_signal.png)

Die Ablauf-Konfiguration wird im Abschnitt [Timeouts](define-approvals.md) beschrieben.

In der Spalte **Timeout** kann die Zeitspanne vor Ablauf in den Einheiten Ihrer Wahl definiert werden. Siehe [Warten](wait.md).

Jede Zeile stellt einen Ablauftypen dar und entspricht einer Transition.

![](assets/external_sign_diag.png)
