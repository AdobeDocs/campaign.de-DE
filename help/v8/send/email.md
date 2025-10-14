---
title: Senden von E-Mails mit Adobe Campaign
description: Erste Schritte mit E-Mails in Adobe Campaign. Senden Sie personalisierte E-Mails an eine Zielguppenpopulation.
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 96f1518f252be7ffa27ba8157b8a090bf4d4510d
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 100%

---

# Entwerfen und Senden von E-Mails

Mit Adobe Campaign können Sie E-Mail-Sendungen erstellen, um personalisierte E-Mails an die Zielpopulation zu senden. [Weitere Informationen](../send/send.md)

>[!NOTE]
>
>Navigieren Sie zum Erstellen fesselnder und individuell zugeschnittener E-Mails zur [Web-Benutzeroberfläche](../start/campaign-ui.md#campaign-web-user-interface-ac-web-ui). Adobe Campaign verfügt über den E-Mail-Designer, eine intuitive Drag-and-Drop-Oberfläche, mit der Sie alle Inhalte für jede E-Mail entwerfen und verfeinern können.


Auf [dieser Seite](../start/create-message.md) erfahren Sie mehr über die wichtigsten Schritte zum Erstellen und Konfigurieren eines Versands.

## Erstellen eines E-Mail-Versands

Erstellen Sie personalisierte und kontextuelle E-Mails, die mit dem übrigen Kundenerlebnis konsistent sind.

![](assets/new-email-content.png)


Im folgenden Beispiel erfahren Sie, wie Sie einen E-Mail-Versand in Adobe Campaign erstellen, der personalisierte Daten, Links zu einer externen URL und einen Link zur Mirrorseite enthält.

1. **Erstellen eines Versands**

   Um einen neuen Versand zu erstellen, gehen Sie zur Registerkarte **Kampagnen**, klicken Sie auf **Sendungen** und anschließend auf die Schaltfläche **Erstellen** oberhalb der Liste der vorhandenen Sendungen.

   ![](assets/delivery_step_1.png)

1. **Auswählen der Vorlage**

   Wählen Sie eine Versandvorlage aus und geben Sie Ihrem Versand eine Bezeichnung. Diese Bezeichnung ist nur für Benutzer der Adobe Campaign-Konsole sichtbar, nicht aber für die Empfänger. Diese Bezeichnung wird in der Liste der Sendungen angezeigt. Bestätigen Sie die Angaben mit der Schaltfläche **[!UICONTROL Fortfahren]**.

   ![](assets/dce_delivery_model.png)

1. **Importieren von Content**

   Klicken Sie auf die Registerkarte **Quelle**, um Ihren HTML-Inhalt einzufügen.

   ![](assets/paste-content.png)

   >[!NOTE]
   >
   >Um Performance-Probleme zu vermeiden, dürfen die in den E-Mails enthaltenen Bilder nicht größer als 100 KB sein.

1. **Personalisieren Ihrer Nachricht**

   * Hinzufügen der Vor- und Nachnamen der Empfänger

     Um den Vor- und Nachnamen der Zielgruppenprofile in den Nachrichteninhalt einzufügen, platzieren Sie den Cursor an der gewünschten Stelle, klicken Sie auf das letzte Symbol in der Symbolleiste, klicken Sie dann auf **[!UICONTROL Einfügen]** und wählen Sie **[!UICONTROL Grußformeln]** aus.

     ![](assets/include-greetings.png)

     Navigieren Sie zur Registerkarte „Vorschau“, um die Personalisierung durch die Auswahl einer Empfängerin oder eines Empfängers zu überprüfen.

     ![](assets/perso-check.png)

     Weiterführende Informationen zu Personalisierungsoptionen finden Sie in [diesem Abschnitt](personalize.md).

   * Einfügen eines getrackten Links

     Um Versandempfänger über ein Bild oder einen Text zu einer externen Adresse weiterzuleiten, wählen Sie diese aus und klicken Sie in der Symbolleiste auf das Symbol **[!UICONTROL Link hinzufügen]**.

     Geben Sie die URL für den Link im Feld **URL** im Format **https://www.myURL.com** ein und bestätigen Sie dann Ihre Eingabe.

     ![](assets/add-a-link.png)

   * Hinzufügen einer Mirrorseite

     Um Empfangenden zu ermöglichen, Ihren Versandinhalt in einem Webbrowser zu sehen, können Sie einen Link zu einer [Mirrorseite](mirror-page.md) Ihrer Nachricht einfügen.

     Platzieren Sie den Cursor an der gewünschten Stelle, klicken Sie auf das letzte Symbol in der Symbolleiste, klicken Sie auf **[!UICONTROL Einfügen]** und wählen Sie **[!UICONTROL Mirrorseiten-Link]** aus.

     Weitere Informationen zur Verwaltung der Mirrorseite finden Sie in [diesem Abschnitt](mirror-page.md#link-to-mirror-page).

1. Sie können zusätzliche Parameter für Ihre E-Mail definieren, z. B. das Senden einer Kopie Ihrer Nachrichten an eine BBC-Adresse, das Ändern des Nachrichtenformats, das Festlegen einer bestimmten Codierung usw. Weiterführende Informationen finden Sie in [diesem Abschnitt](email-parameters.md).

1. Wenn der Inhalt fertig ist, klicken Sie auf **Speichern**: Er wird nun in Ihrer Versandliste auf der Registerkarte **[!UICONTROL Kampagnen > Sendungen]** angezeigt.

Ihr erster E-Mail-Versand ist fertig. Definieren Sie nun die Zielgruppe, validieren Sie den Versand und führen Sie ihn aus.

In diesem [Anwendungsfall](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html?lang=de){target="_blank"} erfahren Sie, wie Sie einen Workflow zum Importieren von E-Mail-Inhalten erstellen.

>[!MORELIKETHIS]
>
>* [Erstellen eines Versands](../start/create-message.md)
>* [Erstellen und Verwenden von E-Mail-Vorlagen](create-templates.md)
>* [Auswählen der Zielgruppe für Ihre E-Mail](../audiences/gs-audiences.md)
>* [Validieren eines Versands und Durchführen von Testsendungen](preview-and-proof.md)
>* [Konfigurieren und Durchführen des Versands](configure-and-send.md)
>* [Best Practices beim Versand](https://experienceleague.adobe.com/de/docs/campaign/campaign-v8/send/delivery-best-practices){target="_blank"}

## Testen und Validieren von E-Mails

Campaign bietet mehrere Möglichkeiten, E-Mails zu testen und zu validieren, bevor Sie sie an Ihre Zielgruppen senden. Auf [dieser Seite](../send/preview-and-proof.md) erfahren Sie, wie Sie Ihren E-Mail-Inhalt in der Vorschau anzeigen und testen können.

Sie haben folgende Möglichkeiten:

* [Durchführen eines Testversands](preview-and-proof.md)
* [Hinzufügen von Testadressen](../audiences/test-profiles.md)
* [Versand-Analyse-Protokolle überprüfen](delivery-analysis.md)

