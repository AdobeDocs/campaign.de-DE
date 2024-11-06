---
title: SMS mit Adobe Campaign versenden
description: Erste Schritte mit dem SMS-Versand in Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 0ef082b49261d0d2de5a6891a4a7f0cf5aafa221
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 20%

---

# Erste Schritte mit SMS {#gs-sms-channel}

Verwenden Sie Adobe Campaign, um Ihren Kunden auf ihren Mobilgeräten Textnachrichten zu senden. Sie können Nachrichten im Textformat im SMS-Editor erstellen, personalisieren und in der Vorschau anzeigen.

Um SMS mit Adobe Campaign an Mobilgeräte zu senden, benötigen Sie:

* Ein externes Konto, das für den Kanal **[!UICONTROL Mobiltelefon (SMS)]** konfiguriert wurde. Erfahren Sie, wie Sie den SMS-Kanal in Ihrer [Mid-Sourcing-Infrastruktur](sms-mid-sourcing.md) konfigurieren. Für diese Konfiguration müssen Sie die Parameter [Externes SMPP-Konto](smpp-external-account.md) und die Merkmale des [SMS-Kanals](sms-channel.md) kennen.
Überprüfen Sie nach der Einrichtung Ihre SMPP-Verbindung und erfahren Sie, wie Sie sie bei Bedarf beheben können. [Weitere Informationen](smpp-connection.md).

* Eine SMS-Versandvorlage, die korrekt mit diesem externen Konto verknüpft ist.


>[!NOTE]
>
>Sie können Adobe Campaign auch verwenden, um [LINE](../../send/line.md) -Nachrichten mit Text und/oder Bildern und Links zu senden.


<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="create-sms.md">
<img alt="SMS erstellen" src="../../assets/do-not-localize/sms-sending.jpg">
</a>
<div><a href="create-sms.md"><strong>SMS-Versand erstellen</strong>
</div>
<p>
</td>
<td>
<a href="sms-content.md">
<img alt="SMS-Inhalte" src="../../assets/do-not-localize/sms.jpg">
</a>
<div>
<a href="sms-content.md"><strong>SMS-Inhalt definieren</strong></a>
</div>
<p></td>
<td>
<a href="sms-audience.md">
<img alt="Zielgruppe" src="../../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-audience.md"><strong>Audience auswählen</strong></a>
</div>
<p>
</td>
<td>
<a href="smpp-external-account.md">
<img alt="Konfiguration" src="../../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="smpp-external-account.md"><strong>Konfigurieren des SMS-Kanals</strong></a>
</div>
<p>
</td>
</tr></table>
