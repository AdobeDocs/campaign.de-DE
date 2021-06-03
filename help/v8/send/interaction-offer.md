---
product: Adobe Campaign
title: Kampagneninteraktionsangebot
description: Erfahren Sie, wie Sie ein Angebot erstellen
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 60%

---

# Angebot erstellen

Gehen Sie wie folgt vor, um ein Angebot zu erstellen:

1. Gehen Sie zum Tab **[!UICONTROL Kampagnen]** und klicken Sie auf den Link **[!UICONTROL Angebote]** .

1. Wählen Sie die **[!UICONTROL Erstellen]**-Schaltfläche aus.

1. Benennen Sie das Angebot und wählen Sie die Kategorie aus, zu der es gehören soll.

1. Klicken Sie auf **[!UICONTROL Speichern]**, um die Erstellung abzuschließen.

   Das Angebot ist nun in der Plattform verfügbar und kann konfiguriert werden.

## Eignungseinstellungen

Sie können jetzt die Registerkarte **[!UICONTROL Eignung]** verwenden, um Folgendes zu definieren:

* Die Eignungsdauer des Angebots. [Mehr dazu](#eligibility-period)
* Filter für die Ziel-Population des Angebots. [Mehr dazu](#filters-on-the-target)
* Die Angebotsgewichtung. [Mehr dazu](#offer-weight)

### Eignungszeitraum des Angebots{#eligibility-period}

Definieren Sie im Tab **[!UICONTROL Eignung]** des Angebots die Eignungsdauer des Angebots. Verwenden Sie die Dropdownlisten, um ein Start- und ein Enddatum im Kalender auszuwählen.

![](assets/offer_eligibility_create_002.png)

Außerhalb dieses Zeitraums wird das Angebot nicht ausgewählt. Wenn Sie auch die Eignungstermine für die Angebotskategorie konfiguriert haben, gilt der restriktivste Zeitraum.

### Filter zur Zielgruppe {#filters-on-the-target} hinzufügen

Wenden Sie im Tab **[!UICONTROL Eignung]** des Angebots Filter auf die Angebotszielgruppe an.

Klicken Sie dazu auf den Link **[!UICONTROL Abfrage bearbeiten]** und wählen Sie den anzuwendenden Filter aus.

![](assets/offer_eligibility_create_003.png)

Wenn bereits vordefinierte Filter erstellt wurden, können Sie diese in der Liste der Benutzerfilter auswählen. [Mehr dazu](interaction-predefined-filters.md)

![](assets/offer_eligibility_create_004.png)

### Angebotsgewichtung festlegen {#offer-weight}

Um dem Angebotsmodul die Möglichkeit zu geben, zwischen verschiedenen für eine Person geeigneten Angeboten zu wählen, ist es empfehlenswert, jedem Angebot eine Gewichtung zuzuweisen. Sie können darüber hinaus Filter auf die Zielgruppe anwenden oder die Platzierung, auf die sich das Gewicht beziehen soll, einschränken. Ein Angebot mit einer höheren Gewichtung wird demzufolge einem Angebot mit niedriger Gewichtung vorgezogen.

Es besteht weiterhin die Möglichkeit, für ein Angebot verschiedene Gewichtungen zu definieren, z. B. in Bezug auf einen Zeitraum, eine Zielgruppe oder auch eine Platzierung.

Ein Angebot kann für Kontakte im Alter von 18 bis 25 Jahren eine Gewichtung A aufweisen und eine Gewichtung B für alle Kontakte über 25 Jahre. Einem Angebot, dessen Verwendungszeitraum auf die Sommermonate beschränkt ist, kann im Juli eine Gewichtung A und im August eine Gewichtung B zugewiesen werden.

>[!NOTE]
>
>Die zugewiesene Gewichtung kann vorübergehend entsprechend den Parametern der Kategorie geändert werden, zu der das Angebot gehört. [Mehr dazu](interaction-offer-catalog.md#creating-offer-categories)

Gehen Sie wie folgt vor, um eine Gewichtung zu konfigurieren:

1. Klicken Sie im Tab **[!UICONTROL Eignung]** des Angebots auf **[!UICONTROL Hinzufügen]**.

   ![](assets/offer_weight_create_001.png)

1. Ändern Sie den Titel und weisen Sie eine Gewichtung zu. Der Standardwert ist 1.

   ![](assets/offer_weight_create_006.png)

   >[!CAUTION]
   >
   >Bei Angabe von 0 wird das Angebot als für die Zielgruppe nicht infrage kommend angesehen.

1. Geben Sie gegebenenfalls ein Start- und ein Enddatum ein.

   ![](assets/offer_weight_create_002.png)

1. Beschränken Sie bei Bedarf die Anwendung der Gewichtung auf eine bestimmte Platzierung.

   ![](assets/offer_weight_create_003.png)

1. Konfigurieren Sie einen Zielgruppenfilter.

   ![](assets/offer_weight_create_004.png)

1. Klicken Sie zum Abschluss auf **[!UICONTROL OK]**.

   ![](assets/offer_weight_create_005.png)

   >[!NOTE]
   >
   >Wenn ein bestimmtes Angebot mit verschiedenen Gewichtungen für einen Kontakt infrage kommt, wählt das Angebotsmodul die höchste Gewichtung aus. Das Angebotsmodul schlägt pro Abfrage einem Kontakt jedes Angebot maximal einmal vor.

### Übersicht der für ein Angebot konfigurierten Eignungsregeln {#a-summary-of-offer-eligibility-rules}

Im Dashboard des Angebots können Sie auf die Details der Eignungskonfiguration zugreifen.

Klicken Sie hierfür auf den Link **[!UICONTROL Planung und Eignungsregeln des Angebots]**.

![](assets/offer_eligibility_create_005.png)

## Angebotsinhalt {#creating-the-offer-content} erstellen

Verwenden Sie den Tab **[!UICONTROL Inhalt]** , um den Angebotsinhalt zu definieren.

![](assets/offer_content_create_001.png)

1. Definieren Sie die verschiedenen Parameter des Angebotsinhalts.

   * **[!UICONTROL Titel]**: Geben Sie den Titel an, der bei Unterbreitung des Angebots angezeigt werden soll. (Hinweis: Es handelt sich hierbei nicht um den Titel, der im Tab **[!UICONTROL Allgemein]** vergeben wurde.)
   * **[!UICONTROL Ziel-URL]** : die URL Ihres Angebots angeben. Sie muss mit &quot;http://&quot;oder &quot;https://&quot;beginnen.
   * **[!UICONTROL Bild-URL]**: Geben Sie die URL oder einen Zugangspfad für das Bild Ihres Angebots an.
   * **[!UICONTROL HTML-Inhalt]**/**[!UICONTROL Textinhalt]**: Geben Sie den Body Ihres Angebots in den Tab Ihrer Wahl ein. Um Tracking zu generieren, muss der **[!UICONTROL HTML-Inhalt]** aus HTML-Elementen bestehen, die in ein `<div>`-Typelement eingeschlossen werden können. Beispielsweise erzeugt ein `<table>`-Element auf der HTML-Seite Folgendes:

   ```
      <div> 
       <table>
        <tr>
         <th>Month</th>
         <th>Savings</th>   
        </tr>   
        <tr>    
         <td>January</td>
         <td>$100</td>   
        </tr> 
       </table> 
      </div>
   ```

   Erfahren Sie, wie Sie die Annahme-URL in [diesem Abschnitt](interaction-offer-spaces.md#configuring-the-status-when-the-proposition-is-accepted) definieren.

   ![](assets/offer_content_create_002.png)

   Durch Klick auf den Link **[!UICONTROL Inhaltsdefinition]** können Sie prüfen, welche Felder in der Platzierungskonfiguration als Pflichtfelder definiert wurden. [Mehr dazu](interaction-offer-spaces.md)

   ![](assets/offer_content_create_003.png)

   In unserem Beispiel muss das Angebot mindestens einen Titel, ein Bild, einen HTML-Inhalt und eine Ziel-URL aufweisen.

## Angebotsvorschau {#previewing-the-offer}

Sobald der Angebotsinhalt konfiguriert wurde, können Sie das Angebot so anzeigen, wie es für den Empfänger erscheinen wird.

Gehen Sie dazu wie folgt vor:

1. Klicken Sie auf den **[!UICONTROL Vorschau]**-Tab.

   ![](assets/offer_preview_create_001.png)

1. Wählen Sie die Darstellung aus, die Sie prüfen möchten.

   ![](assets/offer_preview_create_002.png)

1. Wenn Sie den Inhalt des Angebots personalisiert haben, ist die Auswahl eines Empfängers erforderlich, um die Personalisierung prüfen zu können.

<!--

## Create a hypothesis on an offer {#creating-a-hypothesis-on-an-offer}

You can create hypotheses on your offer propositions. This lets you determine the impact of your offers on purchases carried out for the product concerned.

>[!NOTE]
>
>These hypotheses are carried out via Response Manager. Please check your license agreement.

Hypotheses carried out on an offer proposition are referenced in their **[!UICONTROL Measure]** tab.

Creating hypotheses is detailed in [this page](../../campaign/using/about-response-manager.md).

-->

## Angebot genehmigen und aktivieren{#approve-offers}

Sie können das Angebot nun genehmigen und aktivieren, um es in der Umgebung **Live** verfügbar zu machen.

[!DNL :arrow_upper_right:] Weitere Informationen hierzu finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=en#approving-offer-content)

## Angebotsunterbreitung verwalten{#offer-presentation}

Campaign ermöglicht die Steuerung der Angebotsvorschlagsströme mithilfe von Unterbreitungsregeln. Diese Regeln gelten speziell für Campaign Interaction und sind **Typologieregeln**. Sie ermöglichen den Ausschluss von Angeboten, die auf dem Verlauf der einem Empfänger bereits unterbreiteten Vorschläge basieren. Sie werden in der Umgebung referenziert.

[!DNL :arrow_upper_right:] Weitere Informationen hierzu finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/managing-offer-presentation.html?lang=en#managing-offers)

## Angebotssimulation

Mithilfe von Simulationen können Sie die Verteilung der Angebote einer Kategorie oder einer Umgebung evaluieren, bevor Sie den Vorschlag den Empfängern unterbreiten.

Bei der Simulation werden die Kontexte und Eignungsregeln berücksichtigt, die zuvor für Angebote und deren Unterbreitungsregeln galten. Auf diese Weise können Sie verschiedene Versionen Ihres Angebotsvorschlags testen und verfeinern, ohne tatsächlich ein Angebot zu verwenden oder eine Zielgruppe zu häufig oder zu wenig anzusprechen, da die Simulation keine Auswirkungen auf die Zielgruppenempfänger hat.

[!DNL :arrow_upper_right:] Weiterführende Informationen zur Angebotssimulation finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/simulating-offers/about-offers-simulation.htm)
