---
title: Senden und Überwachen von Transaktionsnachrichten
description: Erfahren Sie, wie Sie Transaktionsnachrichten senden und überwachen
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 084607f6-47d8-40c0-89ba-bfbb88fc2e53
TQID: https://experienceleague.adobe.com/lF4AHDlqHrKUs5Vp5ycT8aCX-EzMzJG5mdULfZIl0ZY
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 863
ht-degree: 77%

---

# Senden und Überwachen von Transaktionsnachrichten {#delivery-execution}

## Senden von Nachrichten{#send-transactional-msg}

Sobald die Anreicherung abgeschlossen ist und dem Ereignis eine Versandvorlage zugeordnet wurde, wird der Versand von der Ausführungsinstanz aus gestartet.

>[!NOTE]
>
>Die Transaktionsnachrichten werden vor jedem anderen Versand priorisiert.

Alle Sendungen werden im Ordner **[!UICONTROL Administration > Betreibung > Message Center > Standard > Sendungen]** gruppiert.

Sie werden standardmäßig in Unterordner nach Versandmonat unterteilt. Dies kann in den Eigenschaften der Nachrichtenvorlage geändert werden.

## Überwachen von Nachrichten {#monitor-transactional-msg}

Zur Überwachung Ihrer Transaktionsnachrichten können Sie die [Versandlogs](send.md) einsehen.

Die von der Ausführungsinstanz gesendeten Transaktionsnachrichten werden durch einen technischen Workflow (**[!UICONTROL Message Center-Ausführungsinstanz]**), der stündlich ausgeführt wird, wieder synchronisiert und in die Kontrollinstanz transferiert.

>[!NOTE]
>
>Die Sendungen sammeln die Ereignisse wöchentlich auf der Grundlage der neuesten Ereignisaktualisierung, und nicht am Erstellungsdatum des Ereignisses. Daher kann sich beim Extrahieren von Transaktionsnachrichten-Versandlogs in der Kontrollinstanz die mit jeder Versandlog-Kennung verknüpfte Versandkennung im Laufe der Zeit ändern, wenn das Log aktualisiert wird (z. B. wenn für das Ereignis ein eingehender Bounce empfangen wird).

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).
-->

## Reporting{#reporting-transactional-msg}

Adobe Campaign bietet verschiedene Berichte, mit deren Hilfe Sie die Aktivitäten der Ausführungsinstanzen steuern sowie ihre reibungslose Ausführung gewährleisten können.

Der Zugriff auf diese Message Center-Berichte erfolgt über den Tab **[!UICONTROL Berichte]** der **Kontrollinstanz**.

![](assets/mc-reports.png)

### Message Center-Ereignisverlauf {#history-events}

Der **[!UICONTROL Ereignisverlauf des Message Centers]** zeigt einen Überblick über die Aktivität des Message-Center-Moduls an, d. h. die Anzahl der als Transaktionsnachrichten verarbeiteten und zugestellten Ereignisse.

Wenn der Bericht geöffnet wird, entsprechen die standardmäßig angezeigten Informationen der Rate der erfolgreich gesendeten Transaktionsnachrichten. Um weitere Ebenen anzuzeigen, können Sie die verschiedenen Knoten öffnen und den Cursor auf der entsprechenden Ebene platzieren, um sie auszuwählen.

Sie haben zudem die Möglichkeit, für jeden Zeitraum die Daten jedes Ereignisses zu visualisieren. Die Spalte **[!UICONTROL Ereignisse]** entspricht der Anzahl von der Kontrollinstanz empfangenen Ereignisse. In der Spalte **[!UICONTROL Gesendet]** werden die als Reaktion auf die Ereignisse gesendeten personalisierten Transaktionsnachrichten berechnet.


### Message Center-Verarbeitungsdauer {#processing-time}

Die **[!UICONTROL Verarbeitungszeit des Message Centers]** zeigt die wichtigsten Indikatoren im Zusammenhang mit der Echtzeit-Warteschlange an. Auf diesen Bericht kann auch über die Registerkarte **[!UICONTROL Überwachung]** der Kontrollinstanz zugegriffen werden.

![](assets/mc-processing-time-report.png)

Sie können globale Statistiken oder Statistiken anzeigen, die sich auf eine bestimmte Ausführungsinstanz beziehen. Sie können die Daten auch nach Kanal und nach einem bestimmten Zeitraum filtern.

Die im Bereich **[!UICONTROL Kennzahlen über den Zeitraum]** angezeigten Indikatoren werden für den ausgewählten Zeitraum berechnet:

* **[!UICONTROL Durchschnittliche Verweildauer in der Warteschlange]**: Durchschnittliche Dauer, die erfolgreich verarbeitete Ereignisse in Message Center verbringen. Dabei wird nur die Verarbeitungszeit berücksichtigt.
* **[!UICONTROL Durchschnittliche Sendungsdauer(en)]**: Durchschnittliche Dauer, die erfolgreich verarbeitete Ereignisse in Message Center verbringen. Es wird nur die MTA-Versandzeit berücksichtigt.
* **[!UICONTROL Durchschnittliche Verarbeitungszeit(en)]**: Durchschnittliche Zeit, die erfolgreich verarbeitete Ereignisse in Message Center verbringen. Die Berechnung berücksichtigt die Verarbeitungszeit und die MTA-Versandzeit.
* **[!UICONTROL Maximale Anzahl an Ereignissen in der Warteschlange]**: Maximale Anzahl der zum gleichen Zeitpunkt in der Message-Center-Warteschlange vorhandenen Ereignisse.
* **[!UICONTROL Minimale Anzahl an Ereignissen in der Warteschlange]**: Minimale Anzahl der zum gleichen Zeitpunkt in der Message-Center-Warteschlange vorhandenen Ereignisse.
* **[!UICONTROL Durchschnittliche Anzahl an Ereignissen in der Warteschlange]**: Durchschnittliche Anzahl der zum gleichen Zeitpunkt in der Message-Center-Warteschlange vorhandenen Ereignisse.

>[!NOTE]
>
>Die Hinweis- und Warnschwellen (orange bzw. rot) der Kennzahlen können im Bereitstellungassistenten von Adobe Campaign konfiguriert werden. Siehe [Überwachungsschwellen](#thresholds).



### Message Center-Dienstqualität {#service-level}

Die **[!UICONTROL Dienstqualität des Message Centers]** zeigt die Versandstatistiken der Transaktionsnachrichten sowie die Fehleraufschlüsselung. Sie können auf einen Fehlertyp klicken, um dessen Details anzuzeigen.

Auf diesen Bericht kann auch über die Registerkarte **[!UICONTROL Überwachung]** der Kontrollinstanz zugegriffen werden.

Sie können globale Statistiken oder Statistiken anzeigen, die sich auf eine bestimmte Ausführungsinstanz beziehen. Sie können die Daten auch nach Kanal und nach einem bestimmten Zeitraum filtern.

Die im Bereich **[!UICONTROL Kennzahlen über den Zeitraum]** angezeigten Indikatoren werden für den ausgewählten Zeitraum berechnet:

* **[!UICONTROL Eingehend (Ereignis/Std.)]**: Durchschnittliche Anzahl der pro Stunde neu in die Message-Center-Warteschlange eingereihten Ereignisse.
* **[!UICONTROL Eingehend (Ereignisanz.)]**: Anzahl der neuen Ereignisse in der Warteschlange.
* **[!UICONTROL Ausgehend (Durchsatz/Std.)]**: Durschnittliche Anzahl der pro Stunde erfolgreich aus Message Center entlassenen Ereignisse (über einen Versand).
* **[!UICONTROL Ausgehend (Nachrichtenanz.)]**: Anzahl der erfolgreich aus Message Center versandten Nachrichten (über einen Versand).
* **[!UICONTROL Durchschnittliche Sendungsdauer (Sekunden)]**: Durchschnittliche Dauer, die erfolgreich verarbeitete Ereignisse in Message Center verbringen. Die Berechnung berücksichtigt die Verarbeitungszeit und die MTA-Versandzeit.
* **[!UICONTROL Fehlerrate]**: Anzahl fehlerhafter Ereignisse im Vergleich zur Anzahl der Neuzugänge in der Message-Center-Warteschlange. Folgende Fehler werden berücksichtigt: Routing-Fehler, Ereignis ist abgelaufen (zu lange in der Warteschlange verbliebenes Ereignis), Versandfehler, vom Versand ignoriert (Quarantäne usw.).

>[!NOTE]
>
>Die Hinweis- und Warnschwellen (orange bzw. rot) der Kennzahlen können im Bereitstellungassistenten von Adobe Campaign konfiguriert werden. Siehe [Überwachungsschwellen](#thresholds).

### Schwellenwerte überwachen {#thresholds}

Sie können die Schwellenwerte für Warnung (orange) und Benachrichtigung (rot) der Indikatoren konfigurieren, die in den Berichten **Message Center Service-Level** und **Message-Center-Verarbeitungszeit** erscheinen.

Gehen Sie dazu wie folgt vor:

1. Öffnen Sie den Bereitstellungsassistenten auf der **Ausführungsinstanz** und navigieren Sie zur Seite **[!UICONTROL Message Center]**.
1. Verwenden Sie die Pfeile, um die Schwellenwerte zu ändern.

   ![](assets/mc-thresholds.png)
