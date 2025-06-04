---
product: campaign
title: Listen-Update
description: Listen-Update
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: abb7f777-0b4a-4bf2-bcb6-32264f340a58
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 100%

---

# Listen-Update{#list-update}



Das **Listen-Update** speichert die Ergebnisse der eingehenden Aktivitäten in einer Liste.

![](assets/s_user_segmentation_update_group.png)

Die Liste kann bereits existieren.

Sie kann jedoch auch mithilfe der Optionen **[!UICONTROL Wenn nötig Liste erstellen (Titel berechnet)]** oder **[!UICONTROL Wenn nötig Liste erstellen (Ordner und Titel berechnet)]** neu erstellt werden. Auf diese Weise können Sie den Titel der Liste und eventuell den Speicherordner angeben. Der Titel kann jedoch auch über dynamische Felder oder ein Script berechnet werden. Der Zugriff auf die dynamischen Felder erfolgt über das Kontextmenü der Schaltfläche rechts vom Titel.

![](assets/s_user_segmentation_update_list_calc.png)

Wenn die Liste bereits existiert, werden die neuen Datensätze hinzugefügt, es sei denn, Sie aktivieren die Option **[!UICONTROL Wenn sie existiert, Liste leeren und erneut verwenden (nicht vervollständigen)]**.

Kreuzen Sie die Option **[!UICONTROL Liste mit eigener Tabelle erstellen oder verwenden]** an, wenn die erstellte oder aktualisierte Liste nicht die Empfängertabelle verwenden soll.

In diesem Fall müssen die entsprechenden Tabellen zuvor in der Adobe Campaign-Instanz konfiguriert werden.

Im Allgemeinen stellt die Speicherung einer Zielgruppe in einer Liste das Ende eines Workflows dar. Standardmäßig bietet die **[!UICONTROL Listen-Update]**-Aktivität daher keine ausgehende Transition. Dies kann durch Ankreuzen der Option **[!UICONTROL Ausgehende Transition erzeugen]** umgangen werden.

![](assets/do-not-localize/how-to-video.png) [Erfahren Sie im Video, wie Sie vom Explorer aus eine Liste von Empfängern erstellen](#video)

## Anwendungsbeispiel Listen-Update {#example--list-update}

Im vorliegenden Beispiel soll eine Liste mit allen Männern über 30 Jahre, die in Deutschland leben, erstellt werden. Bei der ersten Durchführung des Workflows wird die Liste erstellt, bei allen späteren Durchführungen wird sie aktualisiert. Die Liste kann beispielsweise im Rahmen von speziell abgestimmten Werbekampagnen Verwendung finden.

1. Schließen Sie an eine Abfrage ein **[!UICONTROL Listen-Update]** an und öffnen Sie die Aktivität.

   Weitere Informationen zum Erstellen von Abfragen in Workflows finden unter [Abfrage](query.md).

1. Benennen Sie die Aktivität.
1. Kreuzen Sie die Option **[!UICONTROL Wenn nötig Liste erstellen (Titel berechnet)]** an, damit die Liste bei der ersten Durchführung erstellt und später jeweils aktualisiert wird.
1. Wählen Sie den Ordner aus, in dem die Liste gespeichert werden soll.
1. Geben Sie den Titel der Liste an. Fügen Sie gegebenenfalls dynamische Felder ein, um den Listentitel automatisch zu berechnen. Im vorliegenden Beispiel hat die Liste den gleichen Namen wie die Abfrage, um den Inhalt leichter identifizieren zu können.
1. Lassen Sie die Option **[!UICONTROL Wenn sie existiert, Liste leeren und erneut verwenden (nicht vervollständigen)]** aktiv, damit die Empfänger, die nicht mehr den Filterkriterien entsprechen, gelöscht und die neuen Empfänger eingfügt werden.
1. Lassen Sie die Option **[!UICONTROL Liste mit eigener Tabelle erstellen oder verwenden]** ebenfalls aktiv.
1. Lassen Sie die Option **[!UICONTROL Ausgehende Transition erzeugen]** deaktiviert.
1. Klicken Sie auf **[!UICONTROL OK]** und starten Sie den Workflow.

   ![](assets/s_user_segmentation_update_list_calc_example.png)

   Die Empfängerliste wird erstellt und bei erneuter Ausführung des Workflows aktualisiert.

## Eingabeparameter {#input-parameters}

* tableName
* schema

Identifiziert die in der Gruppe zu speichernde Population.

## Ausgabeparameter {#output-parameters}

* groupId: Gruppenkennung.

## Anleitungsvideo {#video}

In diesem Video wird gezeigt, wie man vom Explorer aus eine Liste von Empfängern erstellt.

>[!VIDEO](https://video.tv.adobe.com/v/25602/quality=12)

Weitere Anleitungsvideos zu Campaign finden Sie [hier](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html?lang=de){target="_blank"}.