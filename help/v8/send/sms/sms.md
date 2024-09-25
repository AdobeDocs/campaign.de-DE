---
title: SMS mit Adobe Campaign versenden
description: Erste Schritte mit dem SMS-Versand in Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
badge: label="Eingeschränkte Verfügbarkeit" type="Informative"
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: af1d453179c2d739eca243b435dec90a4b8e2dd5
workflow-type: ht
source-wordcount: '303'
ht-degree: 100%

---

# Erste Schritte mit SMS {#gs-sms-channel}

Verwenden Sie Adobe Campaign, um personalisierte SMS-Nachrichten zu senden.

>[!IMPORTANT]
>
>Diese Dokumentation gilt für Adobe Campaign v8.7.2 und höher.
>
>Für ältere Versionen lesen Sie die [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/de/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

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
