---
title: SMS mit Adobe Campaign versenden
description: Erste Schritte mit dem SMS-Versand in Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 95dca48ae0e2ee82b80464cdf9414538776969ad
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 100%

---

# Erste Schritte mit SMS {#gs-sms-channel}

Verwenden Sie Adobe Campaign, um Textnachrichten an die Mobilgeräte Ihrer Kundinnen und Kunden zu senden. Im SMS-Editor können Sie Nachrichten im Textformat erstellen, personalisieren und in der Vorschau anzeigen.

Um SMS mit Adobe Campaign an Mobilgeräte zu senden, benötigen Sie Folgendes:

* Ein externes Konto, das für den Kanal **[!UICONTROL Mobiltelefon (SMS)]** konfiguriert wurde. Erfahren Sie, wie Sie den SMS-Kanal in Ihrer [Mid-Sourcing-Infrastruktur](sms-mid-sourcing.md) konfigurieren.  Für diese Konfiguration müssen Sie die [Parameter des externen SMPP-Kontos](smpp-external-account.md) und die [Merkmale des SMS-Kanals](sms-channel.md) kennen.
Überprüfen Sie nach dieser Einrichtung Ihre SMPP-Verbindung und informieren Sie sich, wie Sie bei Bedarf Fehler beheben können.  [Weitere Informationen](smpp-connection.md).

* Eine SMS-Versandvorlage, die korrekt mit diesem externen Konto verknüpft ist.


>[!NOTE]
>
>Sie können mit Adobe Campaign auch [Push-Benachrichtigungen](../push.md) und [LINE](../line.md)-Nachrichten an Mobilgeräte versenden.


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
<img alt="SMS-Inhalt" src="../../assets/do-not-localize/sms-create.jpeg">
</a>
<div>
<a href="sms-content.md"><strong>Definieren Ihres SMS-Inhalts</strong></a>
</div>
<p></td>
<td>
<a href="sms-audience.md">
<img alt="SMS-Zielgruppe" src="../../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-audience.md"><strong>Zielgruppe auswählen</strong></a>
</div>
<p>
</td>
<td>
<a href="smpp-external-account.md">
<img alt="SMS-Konfiguration" src="../../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="smpp-external-account.md"><strong>Konfigurieren des SMS-Kanals</strong></a>
</div>
<p>
</td>
</tr></table>
