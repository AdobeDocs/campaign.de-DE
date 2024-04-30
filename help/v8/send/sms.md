---
title: SMS mit Adobe Campaign versenden
description: Erste Schritte mit dem SMS-Versand in Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: ht
source-wordcount: '460'
ht-degree: 100%

---

# SMS erstellen und versenden

Verwenden Sie Adobe Campaign, um personalisierte SMS-Nachrichten zu senden.

Informationen zu den ersten Schritten mit dem SMS-Kanal finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html?lang=de){target="_blank"}

>[!NOTE]
>
>Die Option **Mobile App Channel (NMAC)** ermöglicht darüber hinaus den Versand von Push-Benachrichtigungen auf Mobilgeräte. Weiterführende Informationen finden Sie in [diesem Abschnitt](push.md).

## SMS-Kanal konfigurieren

Folgende Voraussetzungen müssen gegeben sein, um Sendungen an Mobiltelefone richten zu können:

* ein externes Konto mit Angabe des Connectors und des Nachrichtentyps;

* Eine Versandvorlage, die auf das externe Konto Bezug nimmt.

Weitere Informationen zur Konfiguration eines SMS-Kanals finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=de#sending-messages){target="_blank"}

Achten Sie vor dem Versand von SMS-Nachrichten auf Folgendes:

* Stellen Sie sicher, dass die Empfängerprofile mindestens ein Mobiltelefon enthalten.
* Gehen Sie die [Best Practices zum Versand](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=de#sending-messages){target="_blank"} in Adobe Campaign Classic durch. Diese gelten auch für Campaign v8.

Außerdem sollten Sie mit dem Protokoll und den Einstellungen für SMS vertraut sein. Lesen Sie mehr über das Einrichten einer Verbindung zwischen Adobe Campaign und einem SMPP-Provider in [diesem Dokument](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=de#sending-messages){target="_blank"}.

## Den ersten SMS-Versand erstellen

1. Um einen neuen Versand zu erstellen, gehen Sie zur Registerkarte **[!UICONTROL Kampagnen]**, klicken Sie auf **[!UICONTROL Sendungen]** und anschließend auf die Schaltfläche **[!UICONTROL Erstellen]** oberhalb der Liste der vorhandenen Sendungen.

   ![](assets/delivery_step_1.png)

   Allgemeine Informationen zum Erstellen eines Versands finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=de#sending-messages){target="_blank"}.

1. Wählen Sie eine Versandvorlage aus, die auf das entsprechende externe Konto verweist, um SMS-Sendungen durchzuführen.

   ![](assets/sms-template-list.png)

   Wie Sie ein externes SMPP-Konto erstellen, erfahren Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=de#creating-an-smpp-external-account){target="_blank"}

   Wie Sie eine Versandvorlage erstellen, die an Mobilgeräte gesendet wird, erfahren Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=de#changing-the-delivery-template){target="_blank"}

1. Geben Sie für Ihren Versand einen Titel, einen Code und eine Beschreibung ein.

1. Klicken Sie auf **[!UICONTROL Fortfahren]**, um die Eingaben zu bestätigen und in das Fenster der Nachrichtenkonfiguration zu gelangen.

1. Geben Sie den Inhalt der Nachricht im Abschnitt **[!UICONTROL Textinhalt]** des Assistenten ein, einschließlich der ggf. benötigten Personalisierungsfelder.

   ![](assets/sms-content.png)

1. Zielpopulation bestimmen.

Die wichtigsten Schritte zum Erstellen und Entwerfen einer SMS werden in der Dokumentation zu Campaign Classic v7 beschrieben:

* SMS erstellen

  [Erfahren Sie, wie Sie einen SMS-Versand erstellen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=de#sending-messages){target="_blank"}

* Entwerfen des SMS-Inhalts

  [Erfahren Sie, wie Sie den SMS-Inhalt definieren](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=de#defining-the-sms-content){target="_blank"}

* Auswählen der Zielgruppe für Ihre E-Mail

  [Weitere Informationen zur Definition der Zielgruppenpopulation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html?lang=de){target="_blank"}

Die Schritte zum Definieren einer Zielgruppe finden Sie auf [dieser Seite](../start/audiences.md).

## Testen Ihrer SMS

Um das Rendering der Nachricht mit der Personalisierung anzuzeigen, klicken Sie auf **[!UICONTROL Vorschau]** und wählen Sie einen Empfänger aus.

![](assets/sms-preview.png)

Informationen zum Erzeugen eines Testversands finden Sie in den folgenden Abschnitten der Dokumentation zu Campaign Classic v7:

* Validieren eines Versands und Durchführen von Testsendungen
  [Wichtige Schritte zur Validierung eines Versands](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=de){target="_blank"}
* Hinzufügen von Testadressen
  [Erfahren Sie mehr über Testadressen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html?lang=de){target="_blank"}

## SMS-Sendungen durchführen und überwachen

Die wichtigsten Schritte zum Senden und Überwachen einer SMS werden in der Dokumentation zu Campaign Classic v7 beschrieben:

* SMS-Sendungen ausführen, überwachen und verfolgen

  [Erfahren Sie mehr über die Tools zum Senden, Überwachen und Nachverfolgen von SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=de#sending-messages){target="_blank"}

* Fehlerbehebung bei SMS-Sendungen

  [Erfahren Sie mehr über SMS-Fehlerbehebung](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=de#sending-messages){target="_blank"}
