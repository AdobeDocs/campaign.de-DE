---
title: Zugriff auf Trackinglogs
description: Erfahren Sie, wie Sie auf Trackinglogs zugreifen und diese interpretieren können
feature: Monitoring
role: User
level: Beginner
exl-id: df494786-5950-4646-aa9c-4dde45845057
source-git-commit: 5b23be4cb8f0896d2482e525e416713b1a6c4514
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 18%

---

# Zugriff auf Trackinglogs {#accessing-the-tracking-logs}

Der technische Workflow **[!UICONTROL Tracking]** hat die Aufgabe, nach dem Versand und der Aktivierung des Trackings die Tracking-Informationen abzurufen. Standardmäßig wird er stündlich ausgeführt.

## Tracking in Empfängerprofilen anzeigen {#recipient-tracking}

Die derart gesammelten Informationen reichern die im **[!UICONTROL Tracking]**-Tab der Versandempfänger angezeigten Daten an:

![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

Auf dieser Registerkarte werden alle vom Empfänger getrackten und angeklickten URLs angezeigt, darunter:

* Die angeklickte URL
* Datum und Uhrzeit des Klicks
* Der Versand, in dem die URL gefunden wurde
* Alle anderen relevanten Tracking-Informationen

Sie können diese Informationen filtern und sortieren, um das Empfängerverhalten zu analysieren und Interaktionsmuster zu identifizieren.

## Tracking in Sendungen anzeigen {#delivery-tracking}

Tracking-Informationen sind auch über die Registerkarte **[!UICONTROL Tracking]** des Versands zugänglich.

![](assets/s_ncs_user_select_tracking_tab_from_del.png)

Auf dieser Registerkarte können Sie Folgendes anzeigen:

* **[!UICONTROL Tracking-]**: Bietet einen Überblick über Öffnungen, Klicks und andere Tracking-Ereignisse
* **[!UICONTROL URLs und Clickstreams]**: Zeigt an, welche Links wie oft angeklickt wurden
* **[!UICONTROL Klicks]**: Zeigt visuell an, wo Empfängerinnen und Empfänger auf Ihre Nachricht geklickt haben
* **[!UICONTROL Trackinglogs]**: liefert detaillierte, individuelle Trackinglogs

## Fehlerbehebung beim Tracking {#troubleshooting}

>[!NOTE]
>
>Wenn die Registerkarte **[!UICONTROL Tracking]** eines Versands nicht sichtbar ist, bedeutet dies, dass das Tracking nicht aktiviert wurde. Siehe [diesen Abschnitt](tracked-links.md), um zu erfahren, wie Sie Tracking konfigurieren.

### Überprüfen des technischen Workflows Tracking {#check-tracking-workflow}

Der technische Tracking-Workflow muss ausgeführt werden, um Tracking-Daten zu erfassen. Den technischen Tracking-Workflow finden Sie im Ordner **[!UICONTROL Administration > Produktion > Technische Workflows]**.

So überprüfen Sie den Workflow:

1. Öffnen des **[!UICONTROL Tracking]**-Workflows
1. Letztes Ausführungsdatum überprüfen
1. Sicherstellen, dass die Workflow-Protokolle keine Fehler enthalten

Wenn der Workflow nicht ausgeführt wird oder Fehler aufweist, wenden Sie sich an Ihren Systemadministrator.

## Tracking-Datenerfassung überprüfen

Nach dem Versand eines Versands mit aktiviertem Tracking:

1. Warten Sie, bis der Tracking-Workflow ausgeführt wird (standardmäßig stündlich)
1. Versand öffnen und zur Registerkarte **[!UICONTROL Tracking]** wechseln
1. Überprüfen, ob Tracking-Daten angezeigt werden
1. Wenn keine Daten angezeigt werden, überprüfen Sie Folgendes:
   * Tracking wurde in den Versandeinstellungen aktiviert
   * Der technische Tracking-Workflow wird ausgeführt
   * Empfänger haben die E-Mail geöffnet und auf Links geklickt

## Verwandte Themen {#related-topics}

* [Erfahren Sie, wie Sie verfolgte Links konfigurieren](tracked-links.md)
* [Erfahren Sie, wie Sie das Tracking testen](testing-tracking.md)
* [Verstehen von Tracking-Berichten](../reporting/delivery-reports.md#tracking-indicators)

