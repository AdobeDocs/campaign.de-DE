---
product: Adobe Campaign
title: Erste Schritte mit Nachrichten
description: Erste Schritte mit Nachrichten
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 9cb1b38456601bce21d458fea42a5c112d9fafb4
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 97%

---

# Erste Schritte mit Nachrichten{#gs-ac-audiences}

Mit Adobe Campaign können Sie Cross-Channel-Kampagnen wie E-Mails, SMS, Push-Benachrichtigungen und Briefpost senden und deren Effektivität mithilfe verschiedener dedizierter Berichte messen. Diese Nachrichten werden mittels Sendungen entworfen und gesendet und können für jeden Empfänger personalisiert werden.

Zu den Kernfunktionen zählen Zielgruppenbestimmung, Definition und Personalisierung von Nachrichten, Ausführung der Kommunikation und die damit verbundenen operativen Berichte. Der wichtigste funktionale Zugangspunkt ist der Versandassistent. Dieser Zugriffspunkt führt zu mehreren Funktionen, die von Adobe Campaign abgedeckt werden.

In der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=de#sending-messages) lernen Sie die wichtigsten Schritte zur Erstellung eines Versands kennen.

Adobe Campaign v8 enthält die folgenden Versandkanäle:

* **E-Mail-Kanal**: Ein E-Mail-Versand richtet personalisierte elektronische Nachrichten an eine zuvor bestimmte Zielpopulation. Weiterführende Informationen finden Sie auf [dieser Seite](../send/email.md).

* **Briefpost-Kanal**: Ein Briefpost-Versand erzeugt eine Ausgabedatei, die die Daten der Zielpopulation enthält.  Weiterführende Informationen finden Sie auf [dieser Seite](../send/direct-mail.md)

* **Mobile-Kanal**: Ein Versand über den Mobile-Kanal richtet personalisierte SMS an eine zuvor bestimmte Zielpopulation.  Weiterführende Informationen finden Sie auf [dieser Seite](../send/sms.md)

* **Mobile-App-Kanal**: Mit Mobile-App-Sendungen können Sie Benachrichtigungen an iOS- und Android-Systeme senden.  Weiterführende Informationen finden Sie auf [dieser Seite](../send/push.md)

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Auswahl der Versandart für Ihre Nachrichten

Sobald Ihre Nachricht erstellt und ihr Inhalt entworfen und getestet wurde, können Sie wählen, wie Sie sie versenden möchten. Campaign bietet eine Reihe von Funktionen, um:

* Manuelles Senden von Nachrichten an die Hauptzielgruppe

   ![](assets/send-email.png)

   [!DNL :arrow_upper_right:] [Erfahren Sie, wie Sie Nachrichten senden.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html?lang=de#sending-messages)
* Senden von Nachrichten, die einer [Marketing-Kampagne](campaigns.md) zugeordnet sind

   ![](assets/deliveries-in-a-campaign.png)

   [!DNL :arrow_upper_right:] [Erfahren Sie, wie Sie Nachrichten im Kontext einer Kampagne senden.](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=de)
* Senden von Nachrichten über einen [Workflow](../config/workflows.md)

   ![](assets/send-in-a-wf.png)

   [!DNL :arrow_upper_right:] [Erfahren Sie, wie Sie E-Mail-Sendungen automatisieren können.](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html?lang=de)
* [Auslösen von Nachrichten durch ein Ereignis](../send/transactional.md)
   [!DNL :arrow_upper_right:] [Anwendungsfall: Erfahren Sie, wie Sie eine Transaktions-E-Mail mit einem Anhang senden.](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=en)
* Planen eines Nachrichtenversandes

   ![](assets/schedule-send.png)

   [!DNL :arrow_upper_right:] [Anwendungsfall: Erfahren Sie, wie Sie eine Geburtstags-E-Mail planen und senden.](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=de)


## Personalisierung hinzuzufügen

Nachrichten, die von Adobe Campaign versendet werden, können auf verschiedene Weise personalisiert werden.

Sie haben folgende Möglichkeiten:

* Dynamische Personalisierungsfelder einfügen.
   [!DNL :arrow_upper_right:] Erfahren Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=de), wie Sie Personalisierungsfelder verwenden können.
* Vordefinierte Personalisierungsbausteine einfügen.
   [!DNL :arrow_upper_right:] Erfahren Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html?lang=de), was ein Gestaltungsbaustein ist und wie Sie ihn verwenden.
* Bedingte Inhalte erstellen.
   [!DNL :arrow_upper_right:] Erfahren Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html?lang=de), wie Sie bedingte Inhalte einfügen können.

## Senden von Transaktionsnachrichten

Transaktionsnachricht (Message Center) ist das Campaign-Modul, das zum Verwalten von Trigger-Nachrichten entwickelt wurde.

[!DNL :bulb:] Weitere Informationen zur Funktion für Transaktionsnachrichten finden Sie in [diesem Abschnitt](../dev/architecture.md#transac-msg-archi).

[!DNL :bulb:] Die Schritte zum Konfigurieren und Senden von Transaktionsnachrichten werden auf [dieser Seite](../send/transactional.md) ausführlich beschrieben.

[!DNL :arrow_upper_right:] In der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=en) können Sie diese Funktion in einem End-to-End-Anwendungsfall kennenlernen.

## Versand- und Trackinglogs

Die Überwachung Ihrer Sendungen nach deren Versand ist ein wichtiger Schritt, um sicherzustellen, dass Ihre Marketing-Kampagnen effizient sind und Ihre Kunden erreichen. Sie können nach dem Versand überwachen sowie nachvollziehen, wie Zustellungsfehler und Quarantänen gehandhabt werden.

[!DNL :arrow_upper_right:] [Erfahren Sie in diesem Abschnitt, wie Sie Ihre Sendungen überwachen.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=de#sending-messages)


**Verwandte Themen**

[!DNL :arrow_upper_right:]  [Best Practices beim Versand](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=de)

[!DNL :arrow_upper_right:]  [Testen und Senden einer E-Mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

[!DNL :arrow_upper_right:]  [Durchführen eines Testversands](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=de)
