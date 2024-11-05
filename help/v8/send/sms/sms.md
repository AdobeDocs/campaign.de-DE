---
title: SMS mit Adobe Campaign versenden
description: Erste Schritte mit dem SMS-Versand in Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 70af3bceee67082d6a1bb098e60fd2899dc74600
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 100%

---

# Erste Schritte mit SMS {#gs-sms-channel}

Verwenden Sie Adobe Campaign, um personalisierte SMS-Nachrichten zu senden.

>[!NOTE]
>
>Die Option **Mobile App Channel (NMAC)** ermöglicht darüber hinaus den Versand von Push-Benachrichtigungen auf Mobilgeräte. Weiterführende Informationen finden Sie in [diesem Abschnitt](../push.md).

Die Einfachheit und Anwenderfreundlichkeit von SMS machen sie neben ihrer Robustheit und der konkurrenzlosen Kompatibilität mit Milliarden von Endgeräten zu einem sehr wertvollen Kommunikationskanal.

Es gibt zwei Hauptmöglichkeiten, eine SMS zu senden:

* Manuelles Senden von einem Telefon. Dies ist die übliche Art, die für die Kommunikation zwischen Personen verwendet wird.
* Absenden aus dem Internet. Dies ist die Art, die Adobe Campaign zum Senden von Nachrichten verwendet. Dazu benötigen Sie einen SMS-Dienstleister, der als Brücke vom Internet zum Mobilfunknetz fungiert.

Diese Dokumentation enthält die Schritte zum Konfigurieren, Senden und Überwachen eines SMS-Versands:

* **Konfigurieren des SMS-Kanals**

Zunächst müssen Sie den SMS-Kanal in Ihrer [Mid-Sourcing-Infrastruktur](sms-mid-sourcing.md) konfigurieren.

<!--The steps depend on the platform: either you have [a standalone instance](sms-standalone-instance.md) or you are in [a mid-sourcing infrastructure](sms-mid-sourcing.md).-->

Für diese Konfiguration müssen Sie die [Parameter des externen SMPP-Kontos](smpp-external-account.md) und die [Merkmale des SMS-Kanals](sms-channel.md) kennen.

Überprüfen Sie nach dieser Einrichtung Ihre [SMPP-Verbindung und informieren Sie sich, wie Sie bei Bedarf Fehler beheben können](smpp-connection.md).

* **Erstellen des ersten SMS-Versands**

So starten Sie mit der Konfiguration Ihres SMS-Versands:

1. Erstellen Sie Ihren Versand und füllen Sie die [SMS-Versandeinstellungen](sms-delivery-settings.md) aus.

1. [Definieren Sie den Inhalt](sms-content.md) Ihres Versands.

1. [Wählen Sie die Zielgruppe aus](sms-audience.md)

Die Schritte zum Definieren einer Zielgruppe finden Sie auf [dieser Seite](../../audiences/create-audiences.md).

* **Validieren und Senden von SMS**

Nach dem Erstellen Ihres Versands:

1. [Senden Sie Testsendungen](sms-proofs.md), um das Rendern und den Inhalt zu validieren,

1. Anschließend [senden Sie an die endgültige Zielgruppe](sms-send.md).

* **Überwachen und Verfolgen von SMS**

Erfahren Sie, wie Sie nach dem Senden [Ihre SMS überwachen und verfolgen](sms-monitor.md).
