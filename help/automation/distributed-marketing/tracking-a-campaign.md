---
product: campaign
title: Nachverfolgen einer Kampagne
description: Erfahren Sie, wie Sie eine Kampagne mit Campaign Distributed Marketing nachverfolgen.
feature: Distributed Marketing
version: Campaign v8, Campaign Classic v7
role: User
exl-id: 9904c1c6-c233-4aa2-a237-338ebde15661
TQID: https://experienceleague.adobe.com/v-ZkfPAMBCbVOb0FheuwmYILdV4uFjbGu6cv2uoKccc
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: cdc2fbe67fe123c895c8d3d71daffe022ba5c030
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 72%
---
# Nachverfolgen einer Kampagne{#tracking-a-campaign}



Zentrale Benutzer haben die Möglichkeit, die Bestellungen und Evaluierungen der angebotenen Kampagnenkits zu verfolgen.

Folgende Funktionen stehen ihnen hierzu zur Verfügung:

* [Filtern von Kits](#filter-packages),
* [Bearbeiten von Kits](#edit-packages),
* [Abbrechen von Kits](#cancel-a-package),
* [Zurücksetzen eines Packages](#reinitializing-a-package).

## Filtern von Kits {#filter-packages}

Im Tab **[!UICONTROL Kampagnen]** können Sie die Liste der **[!UICONTROL Kampagnenkits]** anzeigen, in der alle vorhandenen dezentralen Marketing-Kampagnen neu gruppiert werden können. Sie können diese Liste so filtern, dass nur Kampagnen angezeigt werden, die entweder veröffentlicht oder überfällig sind, deren Validierung ausstehend ist usw. Klicken Sie dazu auf die Links im oberen Abschnitt diese Ansicht oder verwenden Sie den Link **[!UICONTROL Liste filtern]** und wählen Sie den anzuzeigenden Status des Kampagnenkits.

![Kampagnenkit-Liste mit geöffnetem Statusfilter: In Bearbeitung, Genehmigung ausstehend, Genehmigt, Abgelehnt und mehr.](assets/mkg_dist_catalog_filter.png)

## Bearbeiten von Kits {#edit-packages}

Die Liste der **[!UICONTROL Kampagnenkits]** zeigt eine kurze Zusammenfassung jedes Kits.

Sie enthält folgende Informationen: Titel, Kampagnentyp, Referenzkampagne des Kits sowie sein Speicherordner.

Klicken Sie auf den Namen des Kits, um ihn zu bearbeiten. Sie können auch die Bestellungen nach Lokalstellen und Status anzeigen.

Diese Informationen werden auch in der Übersicht **[!UICONTROL Kampagnenbestellungen]** angezeigt, die alle erfolgten Bestellungen auflistet.

![Liste der Kampagnenbestellungen mit Angabe der Lokalstelle, der Kampagne und des Status (Verfügbar oder Storniert).](assets/mkg_dist_catalog_op_command_details.png)

Die zentrale Benutzerin bzw. der zentrale Benutzer kann die Bestellung bearbeiten. Dafür gibt es zwei Möglichkeiten:

1. Sie können auf den Titel der Bestellung klicken, um sie zu öffnen. Daraufhin werden Bestelldetails angezeigt.

   ![Wenn Sie in der Liste der Kampagnenbestellungen auf eine Bestellung klicken, wird deren Dashboard mit Status, Paket, Lokalstelle und Genehmigungen geöffnet.](assets/mkg_dist_catalog_op_command_edit1.png)

   Über den Tab **[!UICONTROL Bearbeiten > Allgemein]** können die von der Lokalstelle bei der Bestellung erfassten Informationen eingesehen werden.

   ![Registerkarte „Bestellbearbeitung“, Allgemein: Bezeichnung, Organisationseinheit, zugewiesener Benutzer, Status und Kommentar der Lokalstelle.](assets/mkg_dist_catalog_op_command_edit1a.png)

1. Der Benutzer kann auf den Titel des Kampagnenkits klicken, um ihn zu öffnen und gegebenenfalls bestimmte Parameter zu verändern.

   ![Öffnen eines Pakets aus der Liste und dann einer seiner Kampagnenbestellungen, wobei jeweils sein Dashboard angezeigt wird.](assets/mkg_dist_catalog_op_command_edit2.png)

## Abbrechen von Kits {#cancel-a-package}

Die Zentralstelle kann ein Kampagnenkit jederzeit abbrechen.

Klicken Sie hierzu auf die Schaltfläche **[!UICONTROL Abbrechen]** im **[!UICONTROL Dashboard]** des Kampagnenkits.

![Die Schaltfläche Paket abbrechen im Paket-Dashboard öffnet das Dialogfeld Aktion im Paket mit einem Kommentarfeld.](assets/mkg_dist_cancel_op_from_dashboard.png)

Sie haben die Möglichkeit, den Abbruch im Feld **[!UICONTROL Kommentar]** zu begründen.

Auf Niveau einer **lokalen Kampagne** löscht der Abbruch eines Kits diesen aus der Liste der für die Lokalstellen verfügbaren Kampagnen.

Auf Niveau einer **partizipativen Kampagne** hat der Abbruch eines Kits folgende Auswirkungen:

1. Abbruch aller mit diesem Kit verbundenen Bestellungen;

   ![Dashboard für abgebrochene Kampagnen mit dem Status „Storniert“.](assets/mkg_dist_mutual_op_cancelled.png)

1. Abbruch der Hauptkampagne und Anhalten aller aktiven Vorgänge (Workflows, Sendungen);

   ![Das Dashboard der Referenzkampagne wurde abgebrochen, wobei die E-Mail- und SMS-Sendungen als angehalten angezeigt wurden.](assets/mkg_dist_mutual_op_cancelled1.png)

1. Versand einer Benachrichtigung an alle betroffenen Lokalstellen.

   ![Abbruch der Paket-E-Mail, die eine Lokalstelle darüber informiert, dass die Kampagne zentral abgebrochen wurde.](assets/mkg_dist_mutual_op_cancelled2.png)

Abgebrochene Kits können weiterhin von der Zentralstelle aufgerufen und bei Bedarf neu initialisiert werden (siehe unten). Sie werden erst wieder den Lokalstellen angeboten, wenn sie validiert und gestartet wurden. Der Prozess zur Neuinitialisierung von Kits wird unten veranschaulicht.

## Zurücksetzen eines Packages {#reinitializing-a-package}

Das Zurücksetzen eines bereits veröffentlichten Kampagnenkits dient dazu, dieses zu bearbeiten und anschließend den Lokalstellen erneut zur Verfügung zu stellen.

1. Öffnen Sie hierzu das entsprechende Kit.
1. Öffnen Sie den Link **[!UICONTROL Kit zurücksetzen, um es erneut zu benutzen...]** und klicken Sie auf **[!UICONTROL OK]**.

   ![Initialisieren Sie das Bestätigungsdialogfeld für das Paket neu: Der Status wird mit der Schaltfläche OK in Bearbeitung geändert.](assets/mkg_dist_mutual_op_reinit.png)

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Speichern]**, um die Zurücksetzung zu bestätigen.

   ![Dashboard des Pakets wurde abgebrochen, wobei die Schaltfläche „Speichern“ hervorgehoben wurde, um die Neuinitialisierung zu genehmigen.](assets/mkg_dist_mutual_op_reinit2.png)

1. Der Status des Kits ändert sich in **[!UICONTROL In Bearbeitung]**. Ändern, validieren und veröffentlichen Sie es erneut, um es wieder der Liste der Kampagnenkits hinzuzufügen.

>[!NOTE]
>
>Sie haben auch die Möglichkeit, ein abgebrochenes Kampagnenkit zurückzusetzen.
