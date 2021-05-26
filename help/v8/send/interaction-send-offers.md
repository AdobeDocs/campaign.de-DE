---
solution: Campaign v8
product: Adobe Campaign
title: Kampagnen-Interaction-Angebotskatalog
description: Erfahren Sie, wie Sie einen Angebotskatalog erstellen
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 74%

---

# Angebot senden

Damit ein Angebot vom Angebotsmodul ausgewählt werden kann, wurde es validiert und in einer **Live**-Umgebung verfügbar. [Mehr dazu](interaction-offer.md#approve-offers)

Die Angebotsunterbreitung über einen ausgehenden Kommunikationskanal erfolgt per Briefpost, E-Mail oder Mobile-Versand. Sie können auch den Einzelmodus mit Transaktionsnachrichten (Message Center) verwenden.

## Einfügen eines Angebots in einen Versand {#offer-into-a-delivery}

Gehen Sie wie folgt vor, um Angebotsvorschläge in einen Versand einzufügen:

1. Klicken Sie im Versandfenster auf das Symbol **Angebote**.

   ![](assets/offer_delivery_001.png)

1. Wählen Sie die Ihrer Angebotsumgebung entsprechende Platzierung aus.

   ![](assets/offer_delivery_002.png)

1. Wählen Sie die Kategorie aus, der die zu unterbreitenden Angebote angehören, oder ein oder mehrere Themen, um die vom Angebotsmodul getroffene Auswahl einzugrenzen. Es wird empfohlen, nur eins der beiden Felder zu verwenden, um die Auswahlmöglichkeiten nicht zu stark einzuschränken.

   ![](assets/offer_delivery_003.png)

   ![](assets/offer_delivery_004.png)

1. Geben Sie die Anzahl an Angeboten an, die im Nachrichten-Textkörper erscheinen sollen.

   ![](assets/offer_delivery_005.png)

1. Wählen Sie bei Bedarf die Option **[!UICONTROL Nicht infrage kommende Empfänger ausschließen]** aus. [Weitere Informationen](#parameters-for-calling-offer-engine).

   ![](assets/offer_delivery_006.png)

1. Wählen Sie bei Bedarf die Option **[!UICONTROL Keine Anzeige, wenn keine Angebote ausgewählt sind]** aus. [Weitere Informationen](#parameters-for-calling-offer-engine).

   ![](assets/offer_delivery_007.png)

1. Fügen Sie die Eigenschaften mithilfe der Zusammenführungsfelder in den Versandinhalt ein. Die Anzahl der verfügbaren Vorschläge hängt von der Konfiguration des Angebotsmodulaufrufs ab und ihre Reihenfolge hängt von der Priorität der Angebote ab.

   ![](assets/offer_delivery_008.png)

1. Schließen Sie den Inhalt ab, testen Sie Ihren Versand und senden Sie ihn.

   ![](assets/offer_delivery_010.png)


### Parameter des Angebotsmoduls {#parameters-for-calling-offer-engine}

* **[!UICONTROL Platzierung]**: Zur Aktivierung des Angebotsmoduls ist die Angabe einer Platzierung aus der Angebotsumgebung zwingend erforderlich.
* **[!UICONTROL Kategorie]**: spezifischer Ordner, indem die Angebote gespeichert werden. Wenn keine Kategorie angegeben wird, berücksichtigt das Angebotsmodul alle in der Umgebung enthaltenen Angebote, es sei denn, die Auswahl wird durch ein Thema eingegrenzt.
* **[!UICONTROL Themen]**: zuvor auf Kategorieebene definierte Schlüsselwörter, die wie ein Filter agieren. Die zu unterbreitenden Angebote werden den Themen entsprechend aus einer Gruppe von Kategorien ausgewählt.
* **[!UICONTROL Vorschlagsanzahl]**: Anzahl von Angeboten, die in den Nachrichten-Textkörper eingeschlossen werden können. Auch wenn sie nicht in die Nachricht eingeschlossen werden, werden die Angebote erzeugt aber nicht unterbreitet.
* **[!UICONTROL Nicht infrage kommende Empfänger ausschließen]**: Diese Option erlaubt es, Empfänger, für die nicht ausreichend Angebote infrage kommen, vom Versand auszuschließen. Wenn Sie diese Option nicht ankreuzen, erhält ein Empfänger den Versand, auch wenn für ihn nicht die gewünschte Anzahl an Angeboten ausgewählt werden konnte. Seine Nachricht enthält somit weniger oder gar keine Angebote.
* **[!UICONTROL Leere Darstellung anzeigen, wenn kein Angebot ausgewählt wurde]**: Mithilfe dieser Option wählen Sie den Umgang mit Nachrichten aus, für die ein einzufügender Vorschlag nicht (mehr) existiert. Wenn Sie die Option ankreuzen, erscheint in der Nachricht nichts, was sich auf den fehlenden Vorschlag bezieht, und der Versand wird wie üblich verarbeitet. Im anderen Fall wird die gesamte Nachricht vom Versand ausgeschlossen und die entsprechenden Empfänger erhalten keine Nachricht.

## Angebote in Workflows versenden

Verschiedene Workflow-Aktivitäten ermöglichen es Ihnen, die Darstellung von Angeboten zu definieren:

* Anreicherung
* Angebotsmodul
* Angebote pro Segment

### Anreicherung {#enrichment}

Die Aktivität **Anreicherung** ermöglicht das Hinzufügen von Angeboten oder Links zu Angeboten für Versandempfänger.

:[!DNL :arrow_upper_right:]: Weitere Informationen zur Anreicherungsaktivität finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/enrichment.html)

Sie können beispielsweise aus einer Abfrage stammende Empfängerdaten vor Durchführung eines Versands anreichern.

![](assets/int_enrichment_offer1.png)

Zwei Methoden ermöglichen in diesem Fall die Auswahl der Angebotsvorschläge:

* Konfiguration eines Angebots oder einer Abfrage des Angebotsmoduls;
* Referenzierung einer Relation zu einem Angebot.

#### Geben Sie ein Angebot oder einen Aufruf an das Angebotsmodul an {#specifying-an-offer-or-a-call-to-the-offer-engine}

Nach der Konfiguration Ihrer **Abfrage** -Aktivität:

1. Fügen Sie die Aktivität **Anreicherung** hinzu und öffnen Sie sie.
1. Wählen Sie **[!UICONTROL Daten hinzufügen]** im Tab **[!UICONTROL Anreicherung]**.
1. Wählen Sie **[!UICONTROL Angebotsvorschlag]** als hinzuzufügenden Datentyp aus.

   ![](assets/int_enrichment_offer2.png)

1. Geben Sie eine Kennung und einen Titel für den hinzuzufügenden Vorschlag an.
1. Konfigurieren Sie die Angebotsauswahl. Zwei Optionen stehen zur Auswahl:

   * **[!UICONTROL Suche nach dem besten Angebot in einer Kategorie]**: Wenn Sie diese Option ankreuzen, berechnet das Angebotsmodul automatisch das oder die einzufügenden Angebote, die den angegebenen Parametern (Platzierung, Kategorie oder Themen, Kontaktdatum, Anzahl beizubehaltender Angebote) entsprechen. Es wird empfohlen, entweder eine **[!UICONTROL Kategorie]** oder **[!UICONTROL Themen]** anzugeben.

      ![](assets/int_enrichment_offer3.png)

   * **[!UICONTROL Vordefiniertes Angebot]**: Bei Ankreuzen dieser Option können Sie ohne Abfrage des Angebotsmoduls direkt das einzufügende Angebot konfigurieren (Platzierung, Kontaktdatum).

      ![](assets/int_enrichment_offer4.png)

1. Konfigurieren Sie dann eine Versandaktivität, die dem von Ihnen gewählten Kanal entspricht. [Weitere Informationen](#offer-into-a-delivery).

   >[!NOTE]
   >
   >Die Anzahl an für die Vorschau verfügbaren Vorschlägen hängt von der Konfiguration der Anreicherung und nicht von im Versand konfigurierten Parametern ab.

#### Link zu einem Angebot {#referencing-a-link-to-an-offer} referenzieren

Sie können auch auf einen Link zu einem Angebot in einer Aktivität vom Typ **Anreicherung** verweisen.

Gehen Sie dazu wie folgt vor:

1. Klicken Sie im Tab **[!UICONTROL Anreicherung]** der Aktivität auf den Link **[!UICONTROL Daten hinzufügen...]**.
1. Wählen Sie im folgenden Fenster den Datentyp **[!UICONTROL Relation]** aus.
1. Definieren Sie nun den Relationstyp und das Ziel der Relation. Im vorliegenden Beispiel handelt es sich beim Ziel um das Angebotsschema.

   ![](assets/int_enrichment_link1.png)

1. Definieren Sie die Art der Relation zwischen den Daten der Eingangstabelle der Anreicherungsaktivität (hier die Empfängertabelle) und der Angebotstabelle. Sie können beispielsweise einem Empfänger einen Angebotscode zuordnen.

   ![](assets/int_enrichment_link2.png)

1. Konfigurieren Sie dann eine Versandaktivität, die dem von Ihnen gewählten Kanal entspricht. [Weitere Informationen](#offer-into-a-delivery).

   >[!NOTE]
   >
   >Die Anzahl an für die Vorschau verfügbaren Vorschlägen hängt von den im Versand konfigurierten Parametern ab.

#### Rangansicht und Gewichtung von Angeboten speichern {#storing-offer-rankings-and-weights}

Standardmäßig werden Rang und Gewichtung bei Verwendung der Aktivität **Anreicherung** nicht in der Vorschlagstabelle gespeichert.

>[!NOTE]
>
>Die Aktivität **[!UICONTROL Angebotsmodul]** speichert diese Informationen standardmäßig.

Gehen Sie wie folgt vor, wenn Sie diese Informationen dennoch speichern möchten:

1. Erstellen Sie eine Angebotsmodul-Abfrage in einer Anreicherungsaktivität, die nach einer Abfrage und vor einer Versandaktivität platziert wird. [Weitere Informationen](#specifying-an-offer-or-a-call-to-the-offer-engine).
1. Klicken Sie im Anreicherung-Tab der gleichnamigen Aktivität auf den Link **[!UICONTROL Zusätzliche Daten bearbeiten...]**.

   ![](assets/ita_enrichment_rankweight_1.png)

1. Fügen Sie für den Rang die Spalte **[!UICONTROL @rank]** und die Gewichtung die Spalte **[!UICONTROL @weight]** hinzu.

   ![](assets/ita_enrichment_rankweight_2.png)

1. Bestätigen Sie Ihre Wahl und speichern Sie den Workflow.

Der Versand speichert nun automatisch Rang und Gewichtung der Angebote. Die Informationen können im Tab **[!UICONTROL Angebote]** des Versands eingesehen werden.

### Angebotsmodul {#offer-engine}

Auch die Aktivität **[!UICONTROL Angebotsmodul]** ermöglicht die Konfiguration einer einem Versand vorangestellten Modulabfrage.

:[!DNL :arrow_upper_right:]: Weitere Informationen zur Aktivität **Angebotsmodul** finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/offer-engine.html)

Diese Aktivität basiert auf demselben Prinzip wie die Aktivität **Anreicherung** mit einem Engine-Aufruf, indem die eingehenden Populationsdaten mit einem vom Angebotsmodul berechneten Angebot vor einem Versand angereichert werden.

![](assets/int_offerengine_activity2.png)

Nach der Konfiguration Ihrer **Abfrage** -Aktivität:

1. Platzieren Sie im Anschluss an die Abfrage ein **[!UICONTROL Angebotsmodul]** und öffnen Sie es zur weiteren Bearbeitung.
1. Konfigurieren Sie die verschiedenen Parameter der Abfrage des Angebotsmoduls (Platzierung, Kategorie oder Themen, Kontaktdatum, Anzahl beizubehaltender Angebote). Das Modul berechnet automatisch die den Parametern entsprechenden Angebote.

   >[!CAUTION]
   >
   >Wenn Sie diese Aktivität nutzen, werden nur die im Versand verwendeten Vorschläge gespeichert.

   ![](assets/int_offerengine_activity1.png)

1. Konfigurieren Sie dann eine Versandaktivität, die dem von Ihnen gewählten Kanal entspricht. [Weitere Informationen](#inserting-an-offer-proposition-into-a-delivery).

### Angebote pro Segment {#offers-by-cell}

Mithilfe der Aktivität **[!UICONTROL Angebote pro Segment]** lässt sich die eingehende Population (die beispielsweise aus einer Abfrage hervorgeht) in mehrere Zielgruppen aufspalten, um so je Segment spezifische Angebote zu unterbreiten.

:[!DNL :arrow_upper_right:]: Weitere Informationen zur Aktivität **Angebot nach Zelle** finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/offers-by-cell.html)

Gehen Sie dazu wie folgt vor:

1. Platzieren Sie im Anschluss an die Abfrage eine Aktivität **[!UICONTROL Angebote pro Segment]** und öffnen Sie sie zur weiteren Bearbeitung.
1. Wählen Sie im **[!UICONTROL Allgemein]**-Tab die Platzierung, über die Sie Angebote unterbreiten möchten.
1. Definieren Sie nun im **[!UICONTROL Segmente]**-Tab über die Schaltfläche **[!UICONTROL Hinzufügen]** die verschiedenen Segmente:

   * Konfigurieren Sie anhand der verfügbaren Filter und Begrenzungen die Population des Segments.
   * Wählen Sie dann das Angebot aus, das Sie dem Segment unterbreiten möchten. Es stehen die Angebote zur Verfügung, die der Konfiguration der zuvor ausgewählten Platzierung entsprechen.

      ![](assets/int_offer_per_cell1.png)

1. Konfigurieren Sie dann eine Versandaktivität, die dem von Ihnen gewählten Kanal entspricht.

<!--

## Delivering with delivery outlines {#delivering-with-delivery-outlines}

You can also present offers in a delivery using delivery outlines.

For more information on delivery outlines, refer to the Campaign - MRM guide.

1. Create a new campaign or access an existing campaign.
1. Access the delivery outlines via the campaign's **[!UICONTROL Edit]** > **[!UICONTROL Documents]** tab.
1. Add an outline then insert as many offers as you like into it by right-clicking on the outline and selecting **[!UICONTROL New]** > **[!UICONTROL Offer]**, then save the campaign.


1. Create a delivery whose delivery outlines you have access to (for example, a direct mail delivery).
1. When editing the delivery, click **[!UICONTROL Select a delivery outline]**.

   >[!NOTE]
   >
   >Depending on the type of delivery, this option can be found in the **[!UICONTROL Properties]** > **[!UICONTROL Advanced]** menu (for email deliveries for example).


1. Using the **[!UICONTROL Offers]** button, you can then configure the offer space as well as the number of offers to present in the delivery.


1. Add the propositions into the delivery body using the personalization fields (for more on this, refer to the [Inserting an offer proposition into a delivery](#inserting-an-offer-proposition-into-a-delivery) section), or in the case of a direct mail delivery, by editing the extraction file format.

   Propositions will be selected from the offers referenced in the delivery outline.

   >[!NOTE]
   >
   >Information regarding the offer rankings and weights is only saved in the proposition table if the offers are generated directly in the delivery.
-->
