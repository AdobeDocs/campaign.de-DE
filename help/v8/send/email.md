---
product: Adobe Campaign
title: E-Mails mit Adobe Campaign senden
description: Erste Schritte mit E-Mails in Campaign
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: ht
source-wordcount: '618'
ht-degree: 100%

---

# E-Mails entwerfen und senden

Ein E-Mail-Versand richtet personalisierte E-Mails an eine zuvor bestimmte Zielpopulation.

↗️ Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html?lang=de).

## Den ersten E-Mail-Versand erstellen

Erstellen Sie personalisierte und kontextrelevante E-Mails, die mit dem übrigen Kundenerlebnis konsistent sind.

![](assets/new-email-content.png)


Im folgenden Beispiel erfahren Sie, wie Sie einen E-Mail-Versand in Adobe Campaign erstellen, der personalisierte Daten, Links zu einer externen URL und einen Link zur Mirror-Seite enthält.

1. **Erstellen eines Versands**

   Um einen neuen Versand zu erstellen, gehen Sie zur Registerkarte **Kampagnen**, klicken Sie auf **Sendungen** und anschließend auf die Schaltfläche **Erstellen** oberhalb der Liste der vorhandenen Sendungen.

   ![](assets/delivery_step_1.png)

1. **Auswählen der Vorlage**

   Wählen Sie eine Versandvorlage aus und geben Sie Ihrem Versand eine Bezeichnung. Diese Bezeichnung ist nur für Benutzer der Adobe Campaign-Konsole sichtbar, nicht aber für die Empfänger. Diese Bezeichnung wird in der Liste der Sendungen angezeigt. Bestätigen Sie die Angaben mit der Schaltfläche **[!UICONTROL Fortfahren]**.

   ![](assets/dce_delivery_model.png)

1. **Importieren von Content**

   Klicken Sie auf die Registerkarte **Quelle**, um Ihren HTML-Inhalt einzufügen.

   ![](assets/paste-content.png)


1. **Personalisieren Ihrer Nachricht**


   * Hinzufügen der Vor- und Nachnamen der Empfänger

      Um den Vor- und Nachnamen der Zielgruppenprofile in den Nachrichteninhalt einzufügen, platzieren Sie den Cursor an der gewünschten Stelle, klicken Sie auf das letzte Symbol in der Symbolleiste, klicken Sie dann auf **[!UICONTROL Einfügen]** und wählen Sie **[!UICONTROL Grußformeln]** aus.

      ![](assets/include-greetings.png)

      Navigieren Sie zur Registerkarte &quot;Vorschau&quot;, um die Personalisierung durch die Auswahl eines Empfängers zu überprüfen.

      ![](assets/perso-check.png)

   * Einfügen eines getrackten Links

      Um Versandempfänger über ein Bild oder einen Text zu einer externen Adresse weiterzuleiten, wählen Sie diese aus und klicken Sie in der Symbolleiste auf das Symbol **[!UICONTROL Link hinzufügen]**.

      Geben Sie die URL für den Link im Feld **URL** im Format **https://www.myURL.com** ein und bestätigen Sie dann Ihre Eingabe.

      ![](assets/add-a-link.png)

   * Hinzufügen einer Mirror-Seite

      Um Empfängern zu ermöglichen, Ihren Versandinhalt in einem Webbrowser zu sehen, können Sie einen Link zu einer Mirror-Seite Ihrer Nachricht einfügen.

      Platzieren Sie den Cursor an der gewünschten Stelle, klicken Sie auf das letzte Symbol in der Symbolleiste, klicken Sie auf **[!UICONTROL Einfügen]** und wählen Sie **[!UICONTROL Mirrorseiten-Link]** aus.
   Wenn der Inhalt fertig ist, klicken Sie auf **Speichern**: Er wird nun in Ihrer Versandliste auf der Registerkarte **[!UICONTROL Kampagnen > Sendungen]** angezeigt. Ihr erster E-Mail-Versand ist fertig. Definieren Sie nun die Audience, validieren Sie den Versand und führen Sie ihn aus.


Weitere Informationen finden Sie in den folgenden Abschnitten der Dokumentation zu Campaign Classic v7:

* Erstellen einer E-Mail in Campaign

↗️ [Weitere Informationen zum Erstellen von E-Mails](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html?lang=de)
* E-Mail-Inhalt importieren
↗️ [Anwendungsfall: Erstellen eines Workflows zum Laden eines Versand-Inhalts](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html?lang=de).
* E-Mail-Vorlage erstellen und verwenden
↗️ [Weitere Informationen zu E-Mail-Vorlagen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=de).
* Die Audience Ihrer E-Mail auswählen
↗️ [Erfahren Sie, wie Sie die Zielpopulation definieren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html?lang=de).
* Validieren eines Versands und Durchführen von Testsendungen
↗️ [Lernen Sie die wichtigsten Schritte zur Validierung eines Versands kennen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=de).
* [Testadressen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html?lang=de) hinzufügen

## Testen und Validieren von E-Mails

Campaign bietet mehrere Möglichkeiten, E-Mails zu testen und zu validieren, bevor Sie sie an Ihre Audiences senden.

↗️ [Wenden Sie die in der Dokumentation zu Campaign Classic v7 aufgeführten Best Practices an](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html?lang=de).

Sie haben folgende Möglichkeiten:

* Versand-Analyse-Protokolle überprüfen
* Durchführen eines Testversands
* Testadressen hinzufügen
* Kontrollgruppen verwenden
* E-Mail-Rendering prüfen

↗️ [Weitere Informationen finden Sie in der Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=de).

## E-Mails überwachen

Nach dem Versand können Sie im Versand-Dashboard den Versandstatus überprüfen und auf Versandprotokolle und Berichte zugreifen, die bestätigen, dass die Nachrichten korrekt versendet wurden.

↗️ [Weitere Informationen finden Sie in der Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html?lang=de).

