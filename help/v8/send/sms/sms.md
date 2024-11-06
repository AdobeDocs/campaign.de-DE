---
title: SMS mit Adobe Campaign versenden
description: Erste Schritte mit dem SMS-Versand in Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 5b2638927e39b6f839fb3a8639fe106d2c519fbf
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 79%

---

# Erste Schritte mit SMS {#gs-sms-channel}

Mit Adobe Campaign können Sie personalisierte [SMS](../send/sms/sms.md) auf Mobiltelefonen bereitstellen.

Die Inhalt-Kachel von SMS bietet ebenfalls die Möglichkeit der Erstellung, Anpassung und Personalisierung von Nachrichteninhalten, jedoch ausschließlich im Textformat. Es ist außerdem möglich, vor dem Versand eine Vorschau der SMS zu erzeugen.

>[!NOTE]
>
>Sie können Adobe Campaign auch verwenden, um [LINE](../send/line.md) -Nachrichten mit Text und/oder Bildern und Links zu senden.

Um SMS mit Adobe Campaign an ein Mobiltelefon senden zu können, benötigen Sie:

* Ein externes Konto, das für den Kanal **[!UICONTROL Mobiltelefon (SMS)]** oder **[!UICONTROL LINE]** konfiguriert wurde.
* Eine SMS-Versandvorlage, die korrekt mit diesem externen Konto verknüpft ist.

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
