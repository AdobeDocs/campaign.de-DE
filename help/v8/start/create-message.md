---
solution: Campaign
product: Adobe Campaign
title: Erste Schritte mit Nachrichten
description: Erste Schritte mit Nachrichten
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 23%

---

# Erste Schritte mit Nachrichten{#gs-ac-audiences}

Mit Adobe Campaign können Sie kanalübergreifende Kampagnen wie E-Mails, SMS, LINE-Nachrichten, Push-Benachrichtigungen und Briefpost senden und deren Effektivität mithilfe verschiedener dedizierter Berichte messen. Diese Nachrichten werden mittels Sendungen entworfen und gesendet und können für jeden Empfänger personalisiert werden.

Zu den Kernfunktionen zählen Targeting, Definition und Personalisierung von Nachrichten, Ausführung von Mitteilungen und die damit verbundenen operativen Berichte. Das wichtigste funktionale Zugangsportal ist der Versand-Assistent. Dieser Zugriffspunkt führt zu mehreren Funktionen, die von Adobe Campaign abgedeckt werden.

Erfahren Sie, wie Sie einen Versand in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html) erstellen.

Adobe Campaign v8 enthält die folgenden Versand-Kanal:

* **E-Mail-Kanal**: Ein E-Mail-Versand richtet personalisierte elektronische Nachrichten an eine zuvor bestimmte Zielpopulation. Weiterführende Informationen finden Sie auf [dieser Seite](../send/email.md).

* **Briefpost-Kanal**: Ein Briefpost-Versand erzeugt eine Ausgabedatei, die die Daten der Zielpopulation enthält.  Weiterführende Informationen finden Sie auf [dieser Seite](../send/direct-mail.md)

* **Mobile Kanal**: Mit Versänden auf mobilen Kanälen können Sie personalisierte SMS an die Bevölkerung der Zielgruppe senden.  Weiterführende Informationen finden Sie auf [dieser Seite](../send/sms.md)

* **Mobile Application Kanal**: Mit mobilen App-Versänden können Sie Benachrichtigungen an iOS- und Android-Systeme senden.  Weiterführende Informationen finden Sie auf [dieser Seite](../send/push.md)

## Wählen Sie, wie Ihre Nachrichten gesendet werden sollen

Nachdem die Nachricht erstellt und der Inhalt entworfen und getestet wurde, können Sie festlegen, wie Sie sie senden möchten. Kampagne Angebot eine Reihe von Funktionen für:

* Nachrichten manuell an die Hauptversion der Zielgruppe senden
:arrow_upper_right: [Erfahren Sie, wie Sie Nachrichten senden](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)
* Nachrichten senden, die einer [Marketing-Kampagne](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html) zugeordnet sind
:arrow_upper_right: [Erfahren Sie, wie Sie Nachrichten im Kontext einer Kampagne](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html) senden.
* Senden von Nachrichten über einen [Workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
:arrow_upper_right: [Erfahren Sie, wie Sie E-Mail-Versand automatisieren.](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html)
* [Trigger-](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html) Meldungen aus einem Ereignis :arrow_upper_right:  [Verwendungsfall: Erfahren Sie, wie Sie eine transaktionale E-Mail mit einer Anlage senden](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html)
* Nachrichten planen
:arrow_upper_right: [Anwendungsfall: Lernen Sie, wie Sie eine Geburtstagsemail](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?) planen und versenden.


## hinzufügen

Nachrichten, die von Adobe Campaign geliefert werden, können auf verschiedene Weise personalisiert werden.

Sie haben folgende Möglichkeiten:

* Dynamische Personalisierungsfelder einfügen.
:arrow_upper_right: Erfahren Sie, wie Sie Personalisierungsfelder in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html) verwenden.
* Vordefinierte Personalisierungsbausteine einfügen.
:arrow_upper_right: Erfahren Sie, was ein Personalisierungsblock ist und wie er in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html) verwendet wird.
* Bedingte Inhalte erstellen.
:arrow_upper_right: Erfahren Sie, wie Sie bedingten Inhalt in die [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html) einfügen

## Transaktionsnachrichten senden

Transactional Messaging (Message Center) ist das Kampagne-Modul, das zum Verwalten von Trigger-Nachrichten entwickelt wurde.

:bulb: Weitere Informationen zur Funktion für Transaktionsnachrichten in [diesem Abschnitt ](../dev/architecture.md#transac-msg-archi)

:bulb: Die Schritte zum Konfigurieren und Senden von Transaktionsnachrichten sind in [dieser Seite ](../send/transactional.md) beschrieben.

:arrow_upper_right: Entdecken Sie diese Funktion in einem End-to-End-Anwendungsfall in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=en#transactional-messaging)

## Versand und Trackinglogs

Die Überwachung Ihrer Sendungen nach deren Versand ist ein wichtiger Schritt, um sicherzustellen, dass Ihre Marketing-Kampagnen effizient sind und Ihre Kunden erreichen. Sie können nach dem Senden eines Versands überwachen und verstehen, wie Versand-Fehler und Quarantänen verwaltet werden.

:arrow_upper_right: [Erfahren Sie, wie Sie Ihre Versand in diesem Abschnitt überwachen.](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)


**Verwandte Themen**

:arrow_upper_right:  [Best Practices für Versand](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html)

:arrow_upper_right:  [Testen und Senden einer E-Mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

:arrow_upper_right:  [Testversand senden](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
