---
product: campaign
title: Listen-Update
description: Listen-Update
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: abb7f777-0b4a-4bf2-bcb6-32264f340a58
TQID: 'https://experienceleague.adobe.com/jUe51eJ7c3SJn-Lggdn4mmMzpdzsfckpY1FwpbswcxI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ff84ab2f-a7c2-4ced-a3c8-5113f4348d99
    internal-label: Targeting Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 100%
---
# Listen-Update{#list-update}



Das **Listen-Update** speichert die Ergebnisse der eingehenden Aktivitäten in einer Liste.

![](assets/s_user_segmentation_update_group.png)

Die Liste kann bereits existieren.

Sie kann auch mit den Optionen **[!UICONTROL Wenn nötig, Liste erstellen (Name berechnet)]** und **[!UICONTROL Wenn nötig, Liste erstellen (Ordner und Name berechnet)]** erstellt werden. Mit diesen Optionen können Sie den Titel Ihrer Wahl auswählen, um eine Liste und später den Ordner, in dem sie gespeichert werden soll, zu erstellen. Der Titel kann auch automatisch durch Einfügen dynamischer Felder oder eines Skripts generiert werden. Die verschiedenen dynamischen Felder sind im Popup-Menü rechts neben dem Titel verfügbar.

![](assets/s_user_segmentation_update_list_calc.png)

Wenn die Liste bereits existiert, werden Empfangende zum bestehenden Inhalt hinzugefügt, es sei denn, Sie aktivieren die Option **[!UICONTROL Wenn sie existiert, Liste leeren und erneut verwenden (nicht vervollständigen)]**. In diesem Fall wird der Inhalt der Liste vor der Aktualisierung gelöscht.

Kreuzen Sie die Option **[!UICONTROL Liste mit eigener Tabelle erstellen oder verwenden]** an, wenn die erstellte oder aktualisierte Liste nicht die Empfängertabelle verwenden soll.

In diesem Fall müssen die entsprechenden Tabellen zuvor in der Adobe Campaign-Instanz konfiguriert werden.

Im Allgemeinen stellt die Speicherung einer Zielgruppe in einer Liste das Ende eines Workflows dar. Standardmäßig bietet die **[!UICONTROL Listen-Update]**-Aktivität daher keine ausgehende Transition. Dies kann durch Ankreuzen der Option **[!UICONTROL Ausgehende Transition erzeugen]** umgangen werden.

![](assets/do-not-localize/how-to-video.png) [Erfahren Sie im Video, wie Sie vom Explorer aus eine Liste von Empfängern erstellen](#video)

## Anwendungsbeispiel Listen-Update {#example--list-update}

Im folgenden Beispiel folgt die Aktivität „Listen-Update“ einer Abfrage, die sich an Männer über 30 richtet, die in Frankreich leben. Die Liste wird zunächst aus den Ergebnissen der Abfrage erstellt. Sie wird dann jedes Mal aktualisiert, wenn sie vom Workflow gestartet wird. Sie kann beispielsweise regelmäßig für zielgerichtete Werbeangebote für Kampagnen genutzt werden.

1. Schließen Sie an eine Abfrage ein **[!UICONTROL Listen-Update]** an und öffnen Sie die Aktivität.

   Weitere Informationen zum Erstellen von Abfragen in Workflows finden unter [Abfrage](query.md).

1. Benennen Sie die Aktivität.
1. Kreuzen Sie die Option **[!UICONTROL Wenn nötig Liste erstellen (Titel berechnet)]** an, damit die Liste bei Ausführung des ersten Workflows erstellt und später jeweils aktualisiert wird.
1. Wählen Sie den Ordner aus, in dem die Liste gespeichert werden soll.
1. Geben Sie einen Titel für die Liste ein. Sie können dynamische Felder einfügen, um den Namen automatisch aus der Liste zu generieren. Im vorliegenden Beispiel hat die Liste denselben Namen wie die Abfrage, damit der Inhalt leichter identifiziert werden kann.
1. Lassen Sie die Option **[!UICONTROL Wenn sie existiert, Liste leeren und erneut verwenden (nicht vervollständigen)]** aktiv, damit die Empfänger, die nicht mehr den Targeting-Kriterien entsprechen, gelöscht und die neuen Empfänger eingfügt werden.
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