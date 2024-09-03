---
title: SMS mit Adobe Campaign versenden
description: Erste Schritte mit dem SMS-Versand in Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
badge: label="Eingeschränkte Verfügbarkeit" type="Informative"
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: af1d453179c2d739eca243b435dec90a4b8e2dd5
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 20%

---

# Erste Schritte mit SMS {#gs-sms-channel}

Verwenden Sie Adobe Campaign, um personalisierte SMS-Nachrichten zu senden.

>[!IMPORTANT]
>
>Diese Dokumentation gilt für Adobe Campaign v8.7.2 und höher.
>
>Für ältere Versionen lesen Sie bitte die [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

>[!NOTE]
>
>Die Option **Mobile App Channel (NMAC)** ermöglicht darüber hinaus den Versand von Push-Benachrichtigungen auf Mobilgeräte. Weiterführende Informationen finden Sie in [diesem Abschnitt](../push.md).

Dank der Einfachheit und der einfachen Bedienung von SMS ist SMS ein sehr wertvoller Kommunikationskanal, der neben seiner Robustheit und der unübertroffenen Kompatibilität gegenüber Milliarden von Terminals sehr wertvoll ist.

Es gibt zwei Möglichkeiten, eine SMS zu senden:

* Senden Sie es manuell über ein Telefon. Das ist die übliche Art, wie man direkt zwischen Leuten kommuniziert.
* Schicken Sie es aus dem Internet. So sendet Adobe Campaign Nachrichten. Dazu benötigen Sie einen SMS-Dienstleister, der eine Verbindung vom Internet zum Mobilfunknetz herstellt.

In dieser Dokumentation finden Sie die Schritte zum Konfigurieren, Senden und Überwachen eines SMS-Versands:

* **SMS-Kanal konfigurieren**

Zunächst müssen Sie den SMS-Kanal in Ihrer [Mid-Sourcing-Infrastruktur](sms-mid-sourcing.md) konfigurieren.

<!--The steps depend on the platform: either you have [a standalone instance](sms-standalone-instance.md) or you are in [a mid-sourcing infrastructure](sms-mid-sourcing.md).-->

Für diese Konfiguration müssen Sie die Parameter [Externes SMPP-Konto](smpp-external-account.md) und die Merkmale des [SMS-Kanals](sms-channel.md) kennen.

Überprüfen Sie anschließend Ihre [SMPP-Verbindung und erfahren Sie, wie Sie sie bei Bedarf beheben können.](smpp-connection.md)

* **Erstellen Ihres ersten SMS-Versands**

So starten Sie die Konfiguration Ihres SMS-Versands:

1. Erstellen Sie Ihren Versand und füllen Sie die [SMS-Versandeinstellungen](sms-delivery-settings.md) aus.

1. [Definieren Sie den Inhalt](sms-content.md) Ihres Versands.

1. [Wählen Sie die Zielgruppe aus](sms-audience.md).

Die Schritte zum Definieren einer Zielgruppe finden Sie auf [dieser Seite](../../audiences/create-audiences.md).

* **SMS validieren und senden**

Nach der Erstellung Ihres Versands:

1. [Testsendungen durchführen](sms-proofs.md), um das Rendering und den Inhalt zu validieren,

1. Dann senden Sie [ an die endgültige Zielgruppe](sms-send.md).

* **SMS überwachen und tracken**

Nach dem Versand erfahren Sie in [, wie Sie Ihre SMS überwachen und tracken](sms-monitor.md).
