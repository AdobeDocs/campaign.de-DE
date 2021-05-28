---
solution: Campaign v8
product: Adobe Campaign
title: Einstellungen für den E-Mail-Kanal in Campaign
description: Einstellungen für den E-Mail-Kanal in Campaign
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: 3fd91879485a33961769c684acba8ca3c48bbbed
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 63%

---

# Einstellungen für den E-Mail-Kanal in Campaign

## E-Mail-BCC

Sie können Adobe Campaign so konfigurieren, dass von den von der Plattform gesendeten E-Mails eine Kopie beibehalten wird.

>[!NOTE]
>Die E-Mail-BCC-Funktion ist optional. Prüfen Sie diesbezüglich Ihren Lizenzvertrag.

Adobe Campaign selbst ermöglicht keine Verwaltung von archivierten Dateien. Sie können aber die gewünschten Nachrichten an eine bestimmte Adresse senden, wo sie mithilfe eines externen Systems verarbeitet und archiviert werden.

Dazu werden E-Mail-Dateien, die den gesendeten E-Mails entsprechen, auf einen Remote-Server, z. B. einen SMTP-E-Mail-Server, übertragen. Das Archivierungsziel ist eine BCC-E-Mail-Adresse (für die Versand-Empfänger unsichtbar), die Sie angeben müssen.

Bitte beachten Sie Folgendes:

* Sie können nur **eine** BCC-E-Mail-Adresse verwenden.

* Nur erfolgreich gesendete E-Mails werden berücksichtigt, Absprünge nicht.

[!DNL :speech_balloon:] Als Benutzer von Managed Cloud Services  [kontaktieren Sie ](../start/campaign-faq.md#support) Adobe, um E-Mail-BCC in Campaign zu aktivieren. Die gewünschte BCC-E-Mail-Adresse muss dem Adobe-Team, das die Adresse für Sie konfigurieren wird, mitgeteilt werden.

Nachdem E-Mail-BCC konfiguriert wurde, stellen Sie sicher, dass die Funktion in der Versandvorlage oder im Versand über die Option **E-Mail-BCC** aktiviert ist.

![](assets/email-bcc.png)


**Verwandte** Themen in der Campaign Classic v7-Dokumentation:


[!DNL :arrow_upper_right:] [Mirrorseite erzeugen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page)

[!DNL :arrow_upper_right:] [E-Mail-Format auswählen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats)

[!DNL :arrow_upper_right:] [Zeichenkodierung auswählen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding)

[!DNL :arrow_upper_right:] [Bounce-E-Mail-Adresse festlegen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails)

[!DNL :arrow_upper_right:] [Verwenden von E-Mail-Versandvorlagen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=de)

[!DNL :arrow_upper_right:] [Ursachen für das Fehlschlagen von Sendungen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html)
