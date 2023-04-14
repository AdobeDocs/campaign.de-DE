---
title: Transaktionsnachrichten senden und überwachen
description: Erfahren Sie, wie Sie Transaktionsnachrichten senden und überwachen
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: 2d10a8f4349b9e2405847fc6a3db1ed568c60387
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 69%

---


# Transaktionsnachrichten senden und überwachen {#delivery-execution}

## Senden von Nachrichten{#send-transactional-msg}

Sobald die Anreicherung abgeschlossen und dem Ereignis eine Versandvorlage zugeordnet wurde, wird der Versand von der Ausführungsinstanz aus gestartet.

>[!NOTE]
>
>Die Transaktionsnachrichten werden priorisiert vor jedem anderen Versand.

Alle Sendungen werden im Ordner **[!UICONTROL Administration > Betreibung > Message Center > Standard > Sendungen]** gruppiert.

Sie werden standardmäßig in Unterordner nach Versandmonat unterteilt. Dies kann in den Eigenschaften der Nachrichtenvorlage geändert werden.

## Nachrichten überwachen {#monitor-transactional-msg}

Zur Überwachung Ihrer Transaktionsnachrichten können Sie die [Versandlogs](send.md) einsehen.

Die von der Ausführungsinstanz gesendeten Transaktionsnachrichten werden durch einen technischen Workflow (**[!UICONTROL Message Center-Ausführungsinstanz]**), der stündlich ausgeführt wird, wieder synchronisiert und in die Kontrollinstanz transferiert.

>[!NOTE]
>
>Die Sendungen sammeln die Ereignisse wöchentlich auf der Grundlage der neuesten Ereignisaktualisierung, und nicht am Erstellungsdatum des Ereignisses. Daher kann sich beim Extrahieren von Transaktionsnachrichten-Versandlogs in der Kontrollinstanz die mit jeder Versandlog-Kennung verknüpfte Versandkennung im Laufe der Zeit ändern, wenn das Log aktualisiert wird (z. B. wenn für das Ereignis ein eingehender Bounce empfangen wird).

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->

## Reporting{#reporting-transactional-msg}

Adobe Campaign bietet verschiedene Berichte, mit deren Hilfe Sie die Aktivitäten der Ausführungsinstanzen steuern sowie ihre reibungslose Ausführung gewährleisten können.

Der Zugriff auf diese Message Center-Berichte erfolgt über den Tab **[!UICONTROL Berichte]** der **Kontrollinstanz**.

![](assets/mc-reports.png)

### Message-Center-Ereignisverlauf {#history-events}

Die **[!UICONTROL Ereignisverlauf]** zeigt einen Überblick über die Message-Center-Modulaktivität an, d. h. die Anzahl der verarbeiteten Ereignisse und der zugestellten Ereignisse als Transaktionsnachrichten.

Beim Öffnen des Berichts entsprechen die standardmäßig angezeigten Daten der Rate der erfolgreich gesendeten Transaktionsnachrichten. Sie können die unterschiedlichen Knoten aufklappen, um weitere Ebenen anzuzeigen. Fahren Sie mit dem Mauszeiger über eine Ebene, um sie hervorzuheben.

Sie haben zudem die Möglichkeit, für jeden Zeitraum die Daten jedes Ereignisses zu visualisieren. Die Spalte **[!UICONTROL Ereignisse]** entspricht der Anzahl von der Kontrollinstanz empfangenen Ereignisse. In der Spalte **[!UICONTROL Gesendet]** werden die als Reaktion auf die Ereignisse gesendeten personalisierten Transaktionsnachrichten berechnet.


### Message Center-Verarbeitungsdauer {#processing-time}

Die **[!UICONTROL Verarbeitungszeit]** zeigt die wichtigsten Indikatoren im Zusammenhang mit der Echtzeit-Warteschlange an. Auf diesen Bericht kann auch über die **[!UICONTROL Überwachung]** in der Kontrollinstanz.

![](assets/mc-processing-time-report.png)

Sie können globale Statistiken oder Statistiken anzeigen, die sich auf eine bestimmte Ausführungsinstanz beziehen. Sie können die Daten auch nach Kanal und einem bestimmten Zeitraum filtern.

Die im Bereich **[!UICONTROL Kennzahlen über den Zeitraum]** angezeigten Indikatoren werden für den ausgewählten Zeitraum berechnet:

* **[!UICONTROL Durchschnittliche Verweildauer in der Warteschlange (s)]**: Durchschnittliche Dauer, die erfolgreich verarbeitete Ereignisse in Message Center verbringen. Es wird nur die Verarbeitungsdauer berücksichtigt.
* **[!UICONTROL Durchschnittliche Sendungsdauer (s)]**: Durchschnittliche Dauer, die erfolgreich verarbeitete Ereignisse in Message Center verbringen. Es wird nur die Dauer des Versands durch die MTAs berücksichtigt.
* **[!UICONTROL Durchschnittliche Verarbeitungsdauer (s)]**: Durchschnittliche Dauer, die erfolgreich verarbeitete Ereignisse in Message Center verbringen. Die Berechnung berücksichtigt die Verarbeitungs- und MTA-Versanddauer.
* **[!UICONTROL Maximale Anzahl an Ereignissen in der Warteschlange]**: Maximale Anzahl der zum gleichen Zeitpunkt in der Message-Center-Warteschlange vorhandenen Ereignisse.
* **[!UICONTROL Minimale Anzahl an Ereignissen in der Warteschlange]**: Minimale Anzahl der zum gleichen Zeitpunkt in der Message-Center-Warteschlange vorhandenen Ereignisse.
* **[!UICONTROL Durchschnittliche Anzahl an Ereignissen in der Warteschlange]**: Durchschnittliche Anzahl der zum gleichen Zeitpunkt in der Message-Center-Warteschlange vorhandenen Ereignisse.

>[!NOTE]
>
>Die Hinweis- und Warnschwellen (orange bzw. rot) der Kennzahlen können im Software-Verteilungs-Assistenten von Adobe Campaign konfiguriert werden. Siehe [Überwachungsschwellen](#thresholds).



### Message Center-Dienstqualität {#service-level}

Die **[!UICONTROL Dienstqualität]** zeigt die Versandstatistiken der Transaktionsnachrichten sowie die Verteilung der Fehler an. Sie können auf einen Fehlertyp klicken, um dessen Details anzuzeigen.

Auf diesen Bericht kann auch über die **[!UICONTROL Überwachung]** in der Kontrollinstanz.

Sie können globale Statistiken oder Statistiken anzeigen, die sich auf eine bestimmte Ausführungsinstanz beziehen. Sie können die Daten auch nach Kanal und einem bestimmten Zeitraum filtern.

Die im Bereich **[!UICONTROL Kennzahlen über den Zeitraum]** angezeigten Indikatoren werden für den ausgewählten Zeitraum berechnet:

* **[!UICONTROL Eingehend (Ereignis/Std.)]**: Durchschnittliche Anzahl der pro Stunde neu in die Message-Center-Warteschlange eingereihten Ereignisse.
* **[!UICONTROL Eingehend (Ereignisanz.)]**: Anzahl der neuen Ereignisse in der Warteschlange.
* **[!UICONTROL Ausgehend (Durchsatz/Std.)]**: Durschnittliche Anzahl der pro Stunde erfolgreich aus Message Center entlassenen Ereignisse (über einen Versand).
* **[!UICONTROL Ausgehend (Nachrichtenanz.)]**: Anzahl der erfolgreich aus Message Center entlassenen Nachrichten (über einen Versand).
* **[!UICONTROL Durchschnittliche Sendungsdauer (Sekunden)]**: Durchschnittliche Dauer, die erfolgreich verarbeitete Ereignisse in Message Center verbringen. Die Berechnung berücksichtigt die Verarbeitungs- und MTA-Versanddauer.
* **[!UICONTROL Fehlerrate]**: Anzahl fehlerhafter Ereignisse im Vergleich zur Anzahl der Neuzugänge in der Message-Center-Warteschlange. Folgende Fehler werden berücksichtigt: Routing-Fehler, Ereignis ist abgelaufen (zu lange in der Warteschlange verbliebenes Ereignis), Versandfehler, Vom Versand ignoriert (Quarantäne etc.).

>[!NOTE]
>
>Die Hinweis- und Warnschwellen (orange bzw. rot) der Kennzahlen können im Software-Verteilungs-Assistenten von Adobe Campaign konfiguriert werden. Siehe [Überwachungsschwellen](#thresholds).

### Schwellenwerte überwachen {#thresholds}

Sie können die Schwellenwerte für Warnhinweise (orange) und Warnhinweise (rot) der Indikatoren konfigurieren, die in der Variablen **Dienstqualität** und **Verarbeitungszeit** Berichte.

Gehen Sie dazu wie folgt vor:

1. Öffnen Sie den Softwareverteilungs-Assistenten im **Ausführungsinstanz** und navigieren Sie zum **[!UICONTROL Message Center]** Seite.
1. Verwenden Sie die Pfeile, um die Schwellenwerte zu ändern.

   ![](assets/mc-thresholds.png)

