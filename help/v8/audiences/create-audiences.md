---
title: Erstellen von Profilzielgruppen in Campaign
description: Erfahren Sie, wie Sie Listen erstellen und eine Zielgruppe erstellen
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 6fbe5616-7b8b-4504-988b-2bbbfd062548
source-git-commit: 67d08660431f02d2a18f39b3270cc7c7b62ed40e
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 29%

---

# Erstellen einer Zielgruppe in einer Liste{#create-segments}

Verwenden Sie Campaign-Listen, um Zielgruppen zu erstellen und zu organisieren.

Eine Liste ist ein statischer Kontaktsatz, der in Versandaktionen verwendet oder bei einem Import oder einer anderen Workflow-Aktion aktualisiert werden kann. Beispielsweise kann eine mithilfe einer Abfrage aus der Datenbank extrahierte Population als Liste gespeichert werden.

Listen werden über den Link **[!UICONTROL Listen]** im Tab **[!UICONTROL Profile und Zielgruppen]** erstellt und verwaltet. Diese Liste basiert auf der standardmäßigen Adobe Campaign-Profiltabelle (nms:recipient). [Weitere Informationen](../dev/datamodel.md#ootb-profiles.md)

![](assets/list-dashboard.png)

Sie können eine Liste mithilfe der **Liste aktualisieren** -Aktivität in einem Workflow. Diese Aktivität speichert die resultierende Population in einer Liste. Verwenden Sie sie, um eine neue Liste zu erstellen oder eine vorhandene Liste zu aktualisieren. Um Listen zu erstellen, die andere Datentypen als die integrierte Profiltabelle enthalten, müssen Sie einen Workflow ausführen. Wenn Sie beispielsweise eine Abfrage in der Besuchertabelle verwenden und die Liste dann aktualisieren, können Sie eine Besucherliste erstellen. [Weitere Informationen](#create-a-list-wf).

In diesem Video erfahren Sie mehr über die Verwaltung von Listen in Adobe Campaign.

>[!VIDEO](https://video.tv.adobe.com/v/334909?quality=12)


## Erstellen einer Liste von Kontakten {#create-a-list-of-contacts}

Gehen Sie wie folgt vor, um eine Kontaktliste zu erstellen:

1. Verwenden Sie die Schaltfläche **[!UICONTROL Erstellen]** und wählen Sie **[!UICONTROL Neue Liste]** aus.

   ![](assets/new-list.png)

1. Erfassen Sie im Tab **[!UICONTROL Bearbeiten]** des Listenfensters alle nötigen Informationen.

   ![](assets/list-details.png)

   * Geben Sie im Feld **[!UICONTROL Titel]** den Namen der Liste an und ändern Sie ggf. den internen Namen.
   * Sie haben die Möglichkeit, eine Beschreibung in Bezug auf die Liste zu erfassen.
   * Des Weiteren können Sie ein Ablaufdatum angeben. Bei Erreichen des Datums wird die Liste automatisch gelöscht.


1. Setzen Sie im Tab **[!UICONTROL Inhalt]** durch Klick auf die Schaltfläche **[!UICONTROL Hinzufügen]** Profile auf die Liste.

   ![](assets/add-profiles-to-a-list.png)

   Sie können ein neues Profil erstellen und es direkt aus diesem Fenster in die Liste einfügen, indem Sie die **[!UICONTROL Erstellen]** Symbol. Das Profil wird der Datenbank hinzugefügt.

1. Verwenden Sie die Schaltfläche **[!UICONTROL Speichern]**. Die Liste ist nunmehr über die Listenübersicht zugänglich.


## Gefilterte Kontakte in Listen konvertieren {#convert-data-to-a-list}

Sie können Profile auswählen und zu einer Liste hinzufügen. Gehen Sie dazu wie folgt vor:

1. Wählen Sie im Campaign Explorer Profile aus und klicken Sie mit der rechten Maustaste darauf.

   Diese Profile können nach bestimmten Kriterien gefiltert werden.

1. Wählen Sie nun > **[!UICONTROL Aktionen > Auswahl einer Liste zuordnen...]**.

   ![](assets/add-selection-to-a-list.png)

1. Wählen Sie eine vorhandene Liste aus oder erstellen Sie eine neue Liste und klicken Sie auf **[!UICONTROL Nächste]**.

   ![](assets/select-the-list.png)

1. Klicken Sie auf die Schaltfläche **[!UICONTROL starten]**.

   ![](assets/record-a-list.png)

Wählen Sie die **[!UICONTROL Liste neu erstellen]** Option zum Löschen des existierenden Inhalts aus der Liste und zur Optimierung der Listenerstellung (es ist keine Abfrage erforderlich, um zu überprüfen, ob die Profile bereits mit der Liste verknüpft sind).

Wenn Sie die Option **[!UICONTROL Vorgang nicht in der Datenbank protokollieren]** abwählen, ist die Auswahl oder Erstellung eines Ausführungsordners erforderlich, in dem die den Vorgang betreffenden Protokollnachrichten gespeichert werden.

In der oberen Hälfte des Assistenten werden Informationen bezüglich der Ausführung angezeigt. Durch Klick auf die Schaltfläche **[!UICONTROL Abbrechen]** kann der Vorgang gestoppt werden. Bereits verarbeitete Datensätze werden jedoch trotzdem der Liste zugeordnet.

Sobald die Ausführung abgeschlossen ist, öffnen Sie die **[!UICONTROL Profile und Zielgruppen > Listen]** und wählen Sie die Liste aus: die **[!UICONTROL Inhalt]** zeigt die der Liste zugeordneten Profile an.


## Liste mit einem Workflow erstellen  {#create-a-list-wf}

Sie können die **[!UICONTROL Listen-Update]** -Aktivität, um eine Liste zu erstellen oder eine Population zu einer Empfängerliste hinzuzufügen.

Im folgenden Beispiel wird eine Liste aller Empfänger zwischen 25 und 40 erstellt.

1. Auswählen **[!UICONTROL Profile und Zielgruppen]** und **[!UICONTROL Zielgruppen-Workflows]**, erstellen Sie dann einen neuen Workflow aus dem **[!UICONTROL Erstellen]** Schaltfläche.
1. Geben Sie einen Titel für diesen Workflow ein, z. B. &quot;25-40 Kontakte&quot;, fügen Sie eine Beschreibung hinzu und klicken Sie auf **[!UICONTROL Nächste]**.

   ![](assets/targeting-wf-sample.png)

1. Einfügen einer **[!UICONTROL Abfrage]** -Aktivität, um die Zielpopulation zu definieren und die Abfrage zu bearbeiten.

   ![](assets/targeting-wf-edit-query.png)

1. Definieren Sie die Filterbedingungen wie folgt:

   ![](assets/targeting-wf-age-filter.png)

   Erfahren Sie, wie Sie in einem Workflow eine Abfrage erstellen [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html?lang=de#creating-a-query){target=&quot;_blank&quot;}

1. Benennen Sie diese Abfrage und speichern Sie Ihre Änderungen.
1. Hinzufügen einer **[!UICONTROL Listen-Update]** und bearbeiten Sie sie.

   ![](assets/list-update-activity.png)

1. Benennen Sie die Aktivität.
1. Wählen Sie die **[!UICONTROL Erstellen Sie bei Bedarf die Liste (berechneter Name).]** -Option, um anzuzeigen, dass die Liste erstellt wird, sobald der erste Workflow ausgeführt wurde, und dann mit den folgenden Ausführungen aktualisiert wird.
1. Wählen Sie einen Ordner aus und geben Sie einen Titel für die Liste ein.
1. Wählen Sie die **[!UICONTROL Datenbank der Zielgruppendimension]** , um die Tabelle zu speichern.
1. Lassen Sie die **[!UICONTROL Liste leeren, falls vorhanden (andernfalls zur Liste hinzufügen)]** Option aktiviert, um Empfänger zu löschen, die nicht den Targeting-Kriterien entsprechen, und die neuen Empfänger in die Liste einzufügen.
1. Lassen Sie die Option **[!UICONTROL Liste mit eigener Tabelle erstellen oder verwenden]** ebenfalls aktiv.
1. Lassen Sie die Option **[!UICONTROL Ausgehende Transition erzeugen]** deaktiviert.
1. Klicken **[!UICONTROL Ok]** und speichern Sie den Workflow.
1. Starten Sie den Workflow.

   Danach wird die Empfängerliste erstellt. Sie können auf diese Liste über **[!UICONTROL Listen]** der Startseite.

   ![](assets/access-new-list.png)

   Sie können diesen Workflow wiederkehrend gestalten, indem Sie dem Workflow eine Planung hinzufügen. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/scheduler.html){target=&quot;_blank&quot;}.

## Profil aus einer Liste entfernen {#remove-a-profile-from-a-list}

Um ein Profil aus einer Liste zu entfernen, bearbeiten Sie die Liste und wählen Sie das Profil im **[!UICONTROL Inhalt]** und klicken Sie auf die **[!UICONTROL Löschen]** Symbol.

## Liste der Profile löschen {#delete-a-list-of-profiles}

Um eine Liste zu löschen, navigieren Sie im Campaign Explorer zu ihr, wählen Sie sie aus und klicken Sie mit der rechten Maustaste darauf. Auswählen **[!UICONTROL Löschen]**. In einer Warnmeldung werden Sie aufgefordert, den Löschvorgang zu bestätigen.

>[!NOTE]
>
>Die Löschung einer Liste hat außer der Aktualisierung der Profildaten keinen Einfluss auf die der Liste zugeordneten Profile.
