---
solution: Campaign v8
product: Adobe Campaign
title: E-Mail-Kanal-Einstellungen für Campaign
description: E-Mail-Kanal-Einstellungen für Campaign
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 47%

---

# E-Mail-Kanal-Einstellungen für Campaign

## E-Mail-BCC

Sie können Adobe Campaign so konfigurieren, dass von den von der Plattform gesendeten E-Mails eine Kopie beibehalten wird.

>[!NOTE]
>Die E-Mail-BCC-Funktion ist optional. Prüfen Sie diesbezüglich Ihren Lizenzvertrag.

Adobe Campaign selbst ermöglicht keine Verwaltung von archivierten Dateien. Sie können aber die gewünschten Nachrichten an eine bestimmte Adresse senden, wo sie mithilfe eines externen Systems verarbeitet und archiviert werden.

Dazu werden E-Mail-Dateien, die den gesendeten E-Mails entsprechen, auf einen Remote-Server, z. B. einen SMTP-E-Mail-Server, übertragen. Das Archivierungsziel ist eine BCC-E-Mail-Adresse (für die Versand-Empfänger unsichtbar), die Sie angeben müssen.

Bitte beachten Sie Folgendes:

* Sie können nur **eine** BCC-E-Mail-Adresse verwenden.

* Nur erfolgreich gesendete E-Mails werden berücksichtigt, Absprünge nicht.

:Sprache_Ballon: Als Benutzer von Managed Cloud Services kontaktieren Sie [Adobe](../start/campaign-faq.md#support), um E-Mail-BCC in Campaign zu aktivieren. Die von Ihnen ausgewählte BCC-E-Mail-Adresse muss dem Adobe-Team zur Verfügung gestellt werden, das sie für Sie konfigurieren wird.

Nachdem E-Mail-BCC konfiguriert wurde, stellen Sie sicher, dass die Funktion in der Versandvorlage oder im Versand über die Option **E-Mail-BCC** aktiviert ist.

![](assets/email-bcc.png)


**Verwandte** Themen in der Campaign Classic v7-Dokumentation:

* [Verwenden von E-Mail-Versandvorlagen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)
* [E-Mail-Parameter kennenlernen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html)
* [Ursachen für das Fehlschlagen von Sendungen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html)
