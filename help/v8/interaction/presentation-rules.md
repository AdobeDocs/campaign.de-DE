---
product: campaign
title: Unterbreitungsregeln
description: Unterbreitungsregeln
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: f9dd9ad6-48da-4a80-9405-109a433a1ed5
TQID: 'https://experienceleague.adobe.com/s2QV1BGLtUfyWg1BfYuryciF9STRK3HpIXNc6oQ0ATY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 63%
---
# Unterbreitungsregeln{#presentation-rules}



## Unterbreitungsregeln erstellen {#creating-a-presentation-rule}

In unserer Datenbank gibt es mehrere Reiseangebote für Europa, Afrika, die Vereinigten Staaten und Kanada. Wir möchten Angebote für eine Reise nach Kanada senden, aber wenn der Empfänger dieses Angebot ablehnt, möchten wir es nicht erneut an ihn senden.

Die zu erstellende Regel muss somit sicherstellen, dass Reisen nach Kanada jedem Empfänger nur einmal unterbreitet werden, sollte er sie bei der ersten Unterbreitung ablehnen.

1. Markieren Sie im Adobe Campaign-Navigationsbaum den Knoten **[!UICONTROL Administration]** > **[!UICONTROL Kampagnen]** > **[!UICONTROL Typologieverwaltung]** > **[!UICONTROL Typologieregeln]**.
1. Erstellen Sie eine neue Regel vom Typ **[!UICONTROL Angebotsunterbreitung]**.

   ![Formular zur Erstellung von Typologieregeln mit geöffneter Regeltypliste und ausgewählter Angebotsunterbreitung](assets/offer_typology_example_001.png)

1. Benennen Sie die Regel und geben Sie gegebenenfalls eine Beschreibung ein.

   ![Registerkarte „Allgemein“ der Typologieregel mit Titel, Unterbreitungstyp des Angebots, E-Mail-Kanal und eingegebener Beschreibung](assets/offer_typology_example_002.png)

1. Wählen Sie die Option **[!UICONTROL Alle Kanäle]** aus, damit die Regel universell gültig ist.

   ![Kanalliste der Typologieregel mit allen ausgewählten Kanälen](assets/offer_typology_example_003.png)

1. Klicken Sie auf den Link **[!UICONTROL Anwendungskriterien der Regel bearbeiten...]** und wählen Sie den Knoten **[!UICONTROL Kategorie]** als Ausdruck.

   ![Das Abfragefenster mit dem Dialogfeld Ausdruck auswählen wird geöffnet, um das Feld Kategorie auszuwählen](assets/offer_typology_example_004.png)

1. Wählen Sie als Wert aus dem Angebotskatalog die Kategorie Kanada aus und klicken Sie auf **[!UICONTROL OK]**, um das Abfragefenster zu schließen.

   ![Abfrage zur Kategorie ist gleich Kanada, wobei der Ordner „Kanada“ in der Kategoriestruktur der Reiseangebote ausgewählt ist](assets/offer_typology_example_005.png)

1. Wählen Sie dann im Tab **[!UICONTROL Angebotsunterbreitung]** die Dimensionen aus, die Sie auch auf Umgebungsebene konfiguriert haben.

   ![Registerkarte „Angebotsunterbreitung“ mit den Zielgruppendimensionen und Speicherdimensionen, die mit der Umgebung übereinstimmen](assets/offer_typology_example_006.png)

1. Geben Sie den Zeitraum an, in dem die Regel angewendet werden soll.

   ![Registerkarte Angebotsunterbreitung mit dem Feld Gleitzeitraum, Betroffener Zeitraum auf 10d gesetzt](assets/offer_typology_example_007.png)

1. Begrenzen Sie die maximale Vorschlagsanzahl auf einen Vorschlag, damit die Empfänger, die bereits eine Kanadareise abgelehnt haben, nicht erneut ein ähnliches Angebot erhalten.

   ![Registerkarte Angebotsunterbreitung mit dem Feld Maximale Anzahl von Vorschlägen auf 1 gesetzt](assets/offer_typology_example_008.png)

1. Wählen Sie aus der Dropdown-Liste den Filter **[!UICONTROL Angebote derselben Kategorie]** aus, um alle Angebote der Kategorie **Kanada** von der Unterbreitung auszuschließen.

   ![Dropdown-Liste Angebote in Vorschlägen, die mit Angeboten derselben Kategorie gezählt werden sollen](assets/offer_typology_example_020.png)

1. Wählen Sie den Vorschlagsstatus **[!UICONTROL Abgelehnte Vorschläge]**, damit nur die Vorschläge berücksichtigt werden, die der Empfänger nicht angenommen hat.

   ![Dropdown-Liste „Vorschlagsstatus“ in den Vorschlägen, die mit abgelehnten Vorschlägen gezählt werden sollen](assets/offer_typology_example_021.png)

1. Wählen Sie nun die von der Regel betroffenen Empfänger aus.

   Im vorliegenden Beispiel handelt es sich um **Vielreisende**.

   ![Assistent zum Bearbeiten von Filterabfragen, mit dem der Ordner der Empfänger von Vielreisenden als Regelziel ausgewählt wird](assets/offer_typology_example_009.png)

1. Referenzieren Sie die Regel in einer Angeboten vorbehaltenen Typologie.

   ![Registerkarte Typologien der Regel mit dem Dialogfeld Typologien hinzufügen, in dem die ausgewählte Typologie Angebote aufgeführt ist](assets/offer_typology_example_013.png)

1. Gehen Sie zum Abschluss in Ihre Angebotsumgebung, hier **Umgebung - Empfänger**, und referenzieren Sie im Tab **[!UICONTROL Eignung]** die Typologie, die auf die zuvor erstellte Regel verweist.

   ![Registerkarte Eignung der Angebotsumgebung mit der Typologieliste der Angebotsunterbreitung, in der Angebote angezeigt werden](assets/offer_typology_example_014.png)

## Unterbreitungsregeln anwenden {#applying-the-presentation-rule}

Nachfolgend wird aufgezeigt, wie die zuvor erstellte Typologieregel arbeitet.

Wir möchten einen ersten Angebotsvorschlag der Kategorie „Kanada“ versenden. Wenn das Angebot einmal von einer Empfängerin bzw. einem Empfänger abgelehnt wird, wird es ihr bzw. ihm nicht noch einmal unterbreitet.

1. Wählen Sie ein Profil aus dem Empfängerordner **Vielreisende** aus und prüfen Sie, für welche Angebote dieser Empfänger infrage kommt. Klicken Sie hierfür auf den Tab **[!UICONTROL Vorschläge]** und dann auf **[!UICONTROL Vorschau]**:

   Im vorliegenden Beispiel kommt **Peter Urlaubsreif** für ein Angebot aus der Kategorie **Kanada** infrage.

   ![Registerkarte „Empfängervorschläge“, Unterregisterkarte „Vorschau“, auf der das geeignete Angebot für die Kategorie „Nord- und Südamerika“ aufgeführt ist](assets/offer_typology_example_015.png)

1. Erstellen Sie einen ersten E-Mail-Versand mit Angeboten an die Zielgruppe **Vielreisende**.
1. Wählen Sie die Parameter der Angebotsmodul-Abfrage aus.

   Im vorliegenden Beispiel wird die Kategorie **Amerika** gewählt. Sie enthält die Unterkategorien **USA** und **Kanada**.

   ![Dialogfeld Angebotsverwaltung eines E-Mail-Versands mit der Kategorie „Nord- und Südamerika“ und 2 Vorschlägen pro Nachricht](assets/offer_typology_example_016.png)

1. Fügen Sie Ihre Angebote in den Text der Nachricht ein und versenden Sie die Nachricht. Weitere Informationen hierzu finden Sie unter [Informationen zu Outbound-Kanälen](https://experienceleague.adobe.com/de/docs/campaign/campaign-v8/offers/interaction-send-offers){target="_blank"} (Dokumentation zu Campaign v8).

   Der zuvor ausgewählte Empfänger hat das für ihn infrage kommende Angebot wie geplant erhalten.

1. Aus dem Vorschlagsverlauf ist ersichtlich, dass der Empfänger das Angebot abgelehnt hat.

   ![Vorschlagsverlauf des Empfängers mit dem Snowmobile-Angebot Kanada im Status „Abgelehnt“](assets/offer_typology_example_018.png)

1. Prüfen Sie, für welche Angebote er nun infrage kommt.

   Es zeigt sich, dass kein Angebot zu Kanada ausgewählt wurde.

   ![Registerkarte „Empfängervorschau“ mit geeigneten Angeboten für New York und Grand Canyon, ohne Kanada-Angebot](assets/offer_typology_example_019.png)
