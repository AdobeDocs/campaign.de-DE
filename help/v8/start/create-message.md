---
title: Erste Schritte mit Nachrichten
description: Erste Schritte mit Nachrichten
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 93%

---

# Erste Schritte mit Nachrichten{#gs-ac-audiences}

Mit Adobe Campaign können Sie Cross-Channel-Kampagnen wie E-Mails, SMS, Push-Benachrichtigungen und Briefpost senden und deren Effektivität mithilfe verschiedener dedizierter Berichte messen. Diese Nachrichten werden mittels Sendungen entworfen und gesendet und können für jeden Empfänger personalisiert werden.

Zu den Kernfunktionen zählen Zielgruppenbestimmung, Definition und Personalisierung von Nachrichten, Ausführung der Kommunikation und die damit verbundenen operativen Berichte. Der wichtigste funktionale Zugangspunkt ist der Versandassistent. Dieser Zugriffspunkt führt zu mehreren Funktionen, die von Adobe Campaign abgedeckt werden.

Adobe Campaign v8 enthält die folgenden Versandkanäle:

* **E-Mail-Kanal**: Ein E-Mail-Versand richtet personalisierte elektronische Nachrichten an eine zuvor bestimmte Zielpopulation. Weiterführende Informationen finden Sie auf [dieser Seite](../send/email.md).

* **Briefpost-Kanal**: Ein Briefpost-Versand erzeugt eine Ausgabedatei, die die Daten der Zielpopulation enthält.  Weiterführende Informationen finden Sie auf [dieser Seite](../send/direct-mail.md)

* **Mobile-Kanal**: Ein Versand über den Mobile-Kanal richtet personalisierte SMS an eine zuvor bestimmte Zielpopulation.  Weiterführende Informationen finden Sie auf [dieser Seite](../send/sms.md)

* **Mobile-App-Kanal**: Mit Mobile-App-Sendungen können Sie Benachrichtigungen an iOS- und Android-Systeme senden.  Weiterführende Informationen finden Sie auf [dieser Seite](../send/push.md)

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Auswahl der Versandart für Ihre Nachrichten{#gs-send-msg}

Sobald Ihre Nachricht erstellt und ihr Inhalt entworfen und getestet wurde, können Sie wählen, wie Sie sie versenden möchten. Campaign bietet eine Reihe von Funktionen, um:

* Manuelles Senden von Nachrichten an die Hauptzielgruppe

  ![](assets/send-email.png)

  In [diesem Abschnitt](../send/send.md) erfahren Sie, wie Sie Nachrichten senden können

* Senden von Nachrichten, die einer [Marketing-Kampagne](campaigns.md) zugeordnet sind

  ![](assets/deliveries-in-a-campaign.png)

  Erfahren Sie, wie Sie im Kontext einer Kampagne Nachrichten senden können in [diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=de){target="_blank"}

* Senden von Nachrichten über einen [Workflow](../config/workflows.md)

  ![](assets/send-in-a-wf.png)

   Auf [dieser Seite](../../automation/workflow/delivery.md) erfahren Sie, wie Sie einen E-Mail-Versand automatisieren können

* [Auslösen von Nachrichten](../send/transactional.md) durch ein Ereignis

* Planen von Nachrichten

  ![](assets/schedule-send.png)

[Anwendungsfall: Erfahren Sie, wie Sie eine Geburtstags-E-Mail planen und senden.](../../automation/workflow/send-a-birthday-email.md)


## Hinzufügen von Personalisierung{#personalization}

Nachrichten, die von Adobe Campaign versendet werden, können auf verschiedene Weise personalisiert werden. [Weitere Informationen zu Personalisierungsfunktionen](../send/personalize.md)

Sie haben folgende Möglichkeiten:

* Dynamische Personalisierungsfelder einfügen. [Weitere Informationen](../send/personalization-fields.md)
* Vordefinierte Gestaltungsbausteine einfügen. [Weitere Informationen](../send/personalization-blocks.md)
* Bedingte Inhalte erstellen. [Weitere Informationen](../send/conditions.md)

## Senden von Transaktionsnachrichten{#gs-transac-messages}

Das Campaign-Modul &quot;Transaktionsnachricht (Message Center)&quot; wurde zum Verwalten von Trigger-Nachrichten entwickelt.

Weitere Informationen zur Funktion für Transaktionsnachrichten finden Sie in [diesem Abschnitt](../architecture/architecture.md#transac-msg-archi).

Die Schritte zum Konfigurieren und Senden von Transaktionsnachrichten werden auf [dieser Seite](../send/transactional.md) ausführlich beschrieben.


## Versand- und Trackinglogs{#gs-tracking-logs}

Die Überwachung Ihrer Sendungen nach deren Versand ist ein wichtiger Schritt, um sicherzustellen, dass Ihre Marketing-Kampagnen effizient sind und Ihre Kunden erreichen. Sie können nach dem Versand überwachen sowie nachvollziehen, wie Zustellungsfehler und Quarantänen gehandhabt werden.

Informationen zur Überwachung Ihrer Sendungen finden Sie unter [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=de#sending-messages){target="_blank"}

