---
title: Ausführung des Versands von Transaktionsnachrichten
description: Machen Sie sich mit der Ausführung und Überwachung des Versands von Transaktionsnachrichten vertraut
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 74%

---


# Versandausführung {#delivery-execution}

Sobald die Anreicherung abgeschlossen und dem Ereignis eine Versandvorlage zugeordnet wurde, wird der Versand von der Ausführungsinstanz aus gestartet.

>[!NOTE]
>
>Die Transaktionsnachrichten werden priorisiert vor jedem anderen Versand.

Alle Sendungen werden im Ordner **[!UICONTROL Administration > Betreibung > Message Center > Standard > Sendungen]** gruppiert.

Sie werden standardmäßig in Unterordner nach Versandmonat unterteilt. Diese Sortierung kann in den Eigenschaften der Nachrichtenvorlage geändert werden.

## Überwachung der Transaktionsnachrichten {#transactional-message-monitoring}

Zur Überwachung Ihrer Transaktionsnachrichten können Sie die [Versandlogs](send.md) einsehen.

Die von der Ausführungsinstanz gesendeten Transaktionsnachrichten werden durch einen technischen Workflow (**[!UICONTROL Message Center-Ausführungsinstanz]**), der stündlich ausgeführt wird, wieder synchronisiert und in die Kontrollinstanz transferiert.

>[!NOTE]
>
>Die Sendungen sammeln die Ereignisse wöchentlich auf der Grundlage der neuesten Ereignisaktualisierung, und nicht am Erstellungsdatum des Ereignisses. Daher kann sich beim Extrahieren von Transaktionsnachrichten-Versandlogs in der Kontrollinstanz die mit jeder Versandlog-Kennung verknüpfte Versandkennung im Laufe der Zeit ändern, wenn das Log aktualisiert wird (z. B. wenn für das Ereignis ein eingehender Bounce empfangen wird).

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->
