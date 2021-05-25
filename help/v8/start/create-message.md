---
solution: Campaign v8
product: Adobe Campaign
title: Erste Schritte mit Nachrichten
description: Erste Schritte mit Nachrichten
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: c659c31c15916077e71c63f3b3f4ca135d4d7f7d
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 19%

---

# Erste Schritte mit Nachrichten{#gs-ac-audiences}

Mit Adobe Campaign können Sie kanalübergreifende Kampagnen wie E-Mails, SMS, Push-Benachrichtigungen und Briefpost versenden und deren Effektivität mithilfe diverser Berichte messen. Diese Nachrichten werden mittels Sendungen entworfen und gesendet und können für jeden Empfänger personalisiert werden.

Zu den Kernfunktionen gehören die Zielgruppenbestimmung, Definition und Personalisierung von Nachrichten, die Ausführung von Mitteilungen und die damit verbundenen operativen Berichte. Hauptfunktionszugangspunkt ist der Versand-Assistent. Dieser Zugriffspunkt führt zu mehreren Funktionen, die von Adobe Campaign abgedeckt werden.

Wichtige Schritte zum Erstellen eines Versands finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html).

Adobe Campaign v8 enthält die folgenden Versandkanäle:

* **E-Mail-Kanal**: Ein E-Mail-Versand richtet personalisierte elektronische Nachrichten an eine zuvor bestimmte Zielpopulation. Weiterführende Informationen finden Sie auf [dieser Seite](../send/email.md).

* **Briefpost-Kanal**: Ein Briefpost-Versand erzeugt eine Ausgabedatei, die die Daten der Zielpopulation enthält.  Weiterführende Informationen finden Sie auf [dieser Seite](../send/direct-mail.md)

* **Mobile-Kanal**: Sendungen über Mobile-Kanäle ermöglichen den Versand personalisierter SMS an die Zielpopulation.  Weiterführende Informationen finden Sie auf [dieser Seite](../send/sms.md)

* **Mobile-App-Kanal**: Mit Mobile-App-Sendungen können Sie Benachrichtigungen an iOS- und Android-Systeme senden.  Weiterführende Informationen finden Sie auf [dieser Seite](../send/push.md)

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Nachrichten senden

Nachdem Ihre Nachricht erstellt und ihr Inhalt entworfen und getestet wurde, können Sie auswählen, wie Sie sie senden möchten. Campaign bietet eine Reihe von Funktionen für:

* Nachrichten manuell an die Hauptzielgruppe senden
:arrow_upper_right: [Erfahren Sie, wie Sie Nachrichten senden](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)
* Nachrichten senden, die mit einer [Marketing-Kampagne](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html) verknüpft sind
:arrow_upper_right: [Erfahren Sie, wie Sie Nachrichten im Kontext einer Kampagne senden](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html).
* Nachrichten über einen [Workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html) senden
:arrow_upper_right: [Erfahren Sie, wie Sie E-Mail-Sendungen automatisieren](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html)
* [Trigger-](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html) Meldungen aus einem Ereignis :arrow_upper_right:  [Anwendungsfall: Erfahren Sie, wie Sie eine Transaktions-E-Mail mit einem Anhang senden.](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html)
* Versandplanung
:arrow_upper_right: [Anwendungsfall: Erfahren Sie, wie Sie Geburtstags-E-Mails planen und senden](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?)


## Personalisierung hinzufügen

Die von Adobe Campaign bereitgestellten Nachrichten können auf unterschiedliche Weise personalisiert werden.

Sie haben folgende Möglichkeiten:

* Dynamische Personalisierungsfelder einfügen.
:arrow_upper_right: Erfahren Sie, wie Sie Personalisierungsfelder in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html) verwenden.
* Vordefinierte Personalisierungsbausteine einfügen.
:arrow_upper_right: Erfahren Sie, was ein Gestaltungsbaustein ist und wie er in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html) verwendet wird.
* Bedingte Inhalte erstellen.
:arrow_upper_right: Erfahren Sie, wie Sie bedingte Inhalte in die [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html) einfügen.

## Transaktionsnachrichten senden

Transaktionsnachrichten (Message Center) sind das Campaign-Modul zur Verwaltung von Trigger-Nachrichten.

:bulb: Weitere Informationen zur Funktion für Transaktionsnachrichten finden Sie in [diesem Abschnitt](../dev/architecture.md#transac-msg-archi)

:bulb: Die Schritte zum Konfigurieren und Senden von Transaktionsnachrichten werden auf [dieser Seite](../send/transactional.md) beschrieben.

:arrow_upper_right: Entdecken Sie diese Funktion in einem durchgängigen Anwendungsbeispiel in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=en#transactional-messaging)

## Versand- und Trackinglogs

Die Überwachung Ihrer Sendungen nach deren Versand ist ein wichtiger Schritt, um sicherzustellen, dass Ihre Marketing-Kampagnen effizient sind und Ihre Kunden erreichen. Sie können den Versand nach einem Versand überwachen und wissen, wie fehlgeschlagene Sendungen und Quarantänen verwaltet werden.

:arrow_upper_right: [Informationen zum Überwachen Ihrer Sendungen finden Sie in diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)


**Verwandte Themen**

:arrow_upper_right:  [Best Practices beim Versand](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html)

:arrow_upper_right:  [Testen und Senden einer E-Mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

:arrow_upper_right:  [Testsendungen senden](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
