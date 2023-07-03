---
title: Senden von E-Mails mit Adobe Campaign
description: Erste Schritte mit E-Mails in Adobe Campaign. Senden Sie personalisierte E-Mails an eine Zielpopulation.
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 500de76853772313b1aac655da2f1b3562de2c55
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 87%

---

# Entwerfen und Senden von E-Mails

Durch einen E-Mail-Versand können Sie personalisierte E-Mails an eine Zielpopulation senden. [Weitere Informationen](../send/send.md)

## Den ersten E-Mail-Versand erstellen

Erstellen Sie personalisierte und kontextuelle E-Mails, die mit dem übrigen Kundenerlebnis konsistent sind.

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

     Gehen Sie in den Vorschau -Tab, um die Personalisierung durch Auswahl eines Empfängers zu überprüfen.

     ![](assets/perso-check.png)

     Weiterführende Informationen zu Personalisierungsoptionen finden Sie in [diesem Abschnitt](personalize.md).

   * Einfügen eines getrackten Links

     Um Versandempfänger über ein Bild oder einen Text zu einer externen Adresse weiterzuleiten, wählen Sie diese aus und klicken Sie in der Symbolleiste auf das Symbol **[!UICONTROL Link hinzufügen]**.

     Geben Sie die URL für den Link im Feld **URL** im Format **https://www.myURL.com** ein und bestätigen Sie dann Ihre Eingabe.

     ![](assets/add-a-link.png)

   * Hinzufügen einer Mirror-Seite

     Um Empfangenden zu ermöglichen, Ihren Versandinhalt in einem Webbrowser zu sehen, können Sie einen Link zu einer [Mirror-Seite](mirror-page.md) Ihrer Nachricht einfügen.

     Platzieren Sie den Cursor an der gewünschten Stelle, klicken Sie auf das letzte Symbol in der Symbolleiste, klicken Sie auf **[!UICONTROL Einfügen]** und wählen Sie **[!UICONTROL Mirrorseiten-Link]** aus.

     Weitere Informationen zur Verwaltung der Mirrorseite finden Sie unter [diesem Abschnitt](mirror-page.md#link-to-mirror-page).

1. Sie können zusätzliche Parameter für Ihre E-Mail definieren, z. B. das Senden einer Kopie Ihrer Nachrichten an eine BBC-Adresse, das Ändern des Nachrichtenformats, das Festlegen einer bestimmten Kodierung usw. Weiterführende Informationen finden Sie in [diesem Abschnitt](email-parameters.md).

1. Wenn der Inhalt fertig ist, klicken Sie auf **Speichern**: Er wird nun in Ihrer Versandliste auf der Registerkarte **[!UICONTROL Kampagnen > Sendungen]** angezeigt.

Ihr erster E-Mail-Versand ist fertig. Definieren Sie nun die Audience, validieren Sie den Versand und führen Sie ihn aus.

In diesem [Anwendungsfall](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html?lang=de) erfahren Sie, wie Sie E-Mail-Inhalte importieren können.

Weitere Informationen finden Sie in den folgenden Abschnitten:

<!--[Design an email in Campaign]-->
* [Erstellen und Verwenden von E-Mail-Vorlagen](../send/create-templates.md)
* [Auswählen der Audience für Ihre E-Mail](../audiences/gs-audiences.md)
* [Validieren eines Versands und Durchführen von Testsendungen](preview-and-proof.md)
* [Konfigurieren und Durchführen des Versands](configure-and-send.md)

## Testen und Validieren von E-Mails

Campaign bietet mehrere Möglichkeiten, E-Mails zu testen und zu validieren, bevor Sie sie an Ihre Audiences senden. Erfahren Sie, wie Sie Ihren E-Mail-Inhalt in der Vorschau anzeigen und testen können. [diesem Abschnitt](../send/preview-and-proof.md).

Sie haben folgende Möglichkeiten:

* [Durchführen eines Testversands](preview-and-proof.md)
* [Testadressen hinzufügen](../audiences/test-profiles.md)
* [Versand-Analyse-Protokolle überprüfen](delivery-analysis.md)

