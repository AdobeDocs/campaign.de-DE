---
product: Adobe Campaign
title: SMS mit Adobe Campaign versenden
description: Erste Schritte mit dem SMS-Versand in Campaign
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 45%

---

# SMS erstellen und versenden

Verwenden Sie Adobe Campaign, um personalisierte SMS-Nachrichten zu senden.

[!DNL :arrow_upper_right:] Informationen zu den ersten Schritten mit dem SMS-Kanal finden Sie in der  [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html?lang=de#sending-messages){target=&quot;_blank&quot;}

>[!NOTE]
>
>Mit Adobe Campaign können Sie Push-Benachrichtigungen auch auf Mobiltelefone über die Option **Adobe Campaign Mobile App Channel (NMAC)** senden. Weiterführende Informationen finden Sie in [diesem Abschnitt](push.md).

## SMS-Kanal konfigurieren

Folgende Voraussetzungen müssen gegeben sein, um Sendungen an Mobiltelefone richten zu können:

* ein externes Konto mit Angabe des Connectors und des Nachrichtentyps;

* Eine Versandvorlage, die auf das externe Konto Bezug nimmt.

[!DNL :arrow_upper_right:]  Informationen zum Konfigurieren eines SMS-Kanals finden Sie in der Dokumentation zu  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=de#sending-messages){target=&quot;_blank&quot;}

Achten Sie vor dem Versand von SMS-Nachrichten auf Folgendes:

* Stellen Sie sicher, dass die Empfängerprofile mindestens ein Mobiltelefon enthalten.
* Überprüfen Sie die Adobe Campaign Classic [Best Practices beim Versand](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=de#sending-messages){target=&quot;_blank&quot;}, die auch für Campaign v8 gelten.

Außerdem sollten Sie mit dem Protokoll und den Einstellungen für SMS vertraut sein. Gehen Sie in [diesem Dokument](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=de#sending-messages){target=&quot;_blank&quot;} durch die Verbindungskonfiguration zwischen Adobe Campaign und einem SMPP-Provider.

## Erstellen des ersten SMS-Versands

1. Um einen neuen Versand zu erstellen, gehen Sie zur Registerkarte **[!UICONTROL Kampagnen]**, klicken Sie auf **[!UICONTROL Sendungen]** und anschließend auf die Schaltfläche **[!UICONTROL Erstellen]** oberhalb der Liste der vorhandenen Sendungen.

   ![](assets/delivery_step_1.png)

   [!DNL :arrow_upper_right:] Allgemeine Informationen zum Erstellen eines Versands finden Sie in der  [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=de#sending-messages){target=&quot;_blank&quot;}.

1. Wählen Sie eine Versandvorlage aus, die auf das entsprechende externe Konto verweist, um SMS-Sendungen durchzuführen.

   ![](assets/sms-template-list.png)

   [!DNL :arrow_upper_right:] Erfahren Sie, wie Sie ein externes SMPP-Konto in der  [Campaign Classic v7-Dokumentation erstellen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account){target=&quot;_blank&quot;}

   [!DNL :arrow_upper_right:] Erfahren Sie in der  [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template){target=&quot;_blank&quot;}, wie Sie eine Versandvorlage erstellen, die auf Mobiltelefone bereitgestellt wird.

1. Geben Sie für Ihren Versand einen Titel, einen Code und eine Beschreibung ein.

1. Klicken Sie auf **[!UICONTROL Weiter]** , um das Fenster zur Nachrichtenkonfiguration zu bestätigen und anzuzeigen.

1. Geben Sie den Inhalt der Nachricht im Abschnitt **[!UICONTROL Textinhalt]** des Assistenten ein, einschließlich der Personalisierungsfelder nach Bedarf.

   ![](assets/sms-content.png)

1. Zielpopulation bestimmen.

Die wichtigsten Schritte zum Erstellen und Entwerfen einer SMS werden in der Dokumentation zu Campaign Classic v7 beschrieben:

* SMS erstellen

   [!DNL :arrow_upper_right:] [Erfahren Sie, wie Sie einen SMS-Versand erstellen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* SMS-Inhalt gestalten

   [!DNL :arrow_upper_right:] [Erfahren Sie, wie Sie den SMS-Inhalt definieren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content){target=&quot;_blank&quot;}

* Auswählen der Audience für Ihre E-Mail

   [!DNL :arrow_upper_right:] [Weitere Informationen zur Definition der Zielpopulation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html?lang=de){target=&quot;_blank&quot;}

[!DNL :bulb:] Die Schritte zum Definieren einer Zielgruppe werden auf  [dieser Seite](../start/audiences.md) beschrieben.

## Testen Ihrer SMS

Um das Rendering der Nachricht mit ihrer Personalisierung anzuzeigen, klicken Sie auf **[!UICONTROL Vorschau]** und wählen Sie einen Empfänger aus.

![](assets/sms-preview.png)

Informationen zum Testversand finden Sie in den folgenden Abschnitten der Dokumentation zu Campaign Classic v7:

* Validieren eines Versands und Durchführen von Testsendungen
   [!DNL :arrow_upper_right:] [Wichtige Schritte zur Validierung eines Versands](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=de){target=&quot;_blank&quot;}
* Testadressen hinzufügen
   [!DNL :arrow_upper_right:] [Erfahren Sie mehr über Testadressen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html?lang=de){target=&quot;_blank&quot;}

## SMS-Sendungen senden und überwachen

Die wichtigsten Schritte zum Senden und Überwachen einer SMS werden im Campaign Classic v7-Handbuch beschrieben:

* SMS-Sendungen ausführen, überwachen und verfolgen

   [!DNL :arrow_upper_right:] [Erfahren Sie mehr über die Tools zum Senden, Überwachen und Verfolgen von SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* Fehlerbehebung bei SMS-Sendungen

   [!DNL :arrow_upper_right:] [Informationen zur SMS-Fehlerbehebung](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages){target=&quot;_blank&quot;}
