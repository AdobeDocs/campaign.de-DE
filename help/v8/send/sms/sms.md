---
title: SMS mit Adobe Campaign versenden
description: Erste Schritte mit dem SMS-Versand in Campaign
feature: SMS
role: User, Developer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
TQID: 'https://experienceleague.adobe.com/7ChOYJmYScxaAoqnruyMv-8n0AkXgYAIlt1783hTjvY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 92%
---
# Erste Schritte mit SMS {#gs-sms-channel}

Verwenden Sie Adobe Campaign, um Textnachrichten an die Mobilgeräte Ihrer Kundinnen und Kunden zu senden. Im SMS-Editor können Sie Nachrichten im Textformat erstellen, personalisieren und in der Vorschau anzeigen.

Um SMS mit Adobe Campaign an Mobilgeräte zu senden, benötigen Sie Folgendes:

* Ein externes Konto, das für den Kanal **[!UICONTROL Mobiltelefon (SMS)]** konfiguriert wurde. Erfahren Sie, wie Sie den SMS-Kanal in Ihrer [Mid-Sourcing-Infrastruktur](sms-mid-sourcing.md) konfigurieren. Für diese Konfiguration müssen Sie die [Parameter des externen SMPP-Kontos](smpp-external-account.md) und die [Merkmale des SMS-Kanals](sms-channel.md) kennen.
Überprüfen Sie nach dieser Einrichtung Ihre SMPP-Verbindung und informieren Sie sich, wie Sie bei Bedarf Fehler beheben können. [Weitere Informationen](smpp-connection.md).

* Eine SMS-Versandvorlage, die korrekt mit diesem externen Konto verknüpft ist.

Adobe Campaign unterstützt zwei SMS-Connectoren, die zum Senden von SMS-Nachrichten an Ihre Kunden verwendet werden. [Weitere Informationen](sms-connectors.md).

>[!NOTE]
>
>Sie können mit Adobe Campaign auch [Push-Benachrichtigungen](../push.md) und [LINE](../line/line.md)-Nachrichten an Mobilgeräte versenden.

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
