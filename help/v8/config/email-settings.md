---
solution: Campaign Classic
product: campaign
title: Einstellungen für Kampagne-E-Mail-Kanal
description: Einstellungen für Kampagne-E-Mail-Kanal
feature: Übersicht
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: c2d066ca2f935455861c3d6747c9805c847f2e0d
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 53%

---

# Einstellungen für Kampagne-E-Mail-Kanal

## E-Mail-BCC

Sie können Adobe Campaign so konfigurieren, dass von den von der Plattform gesendeten E-Mails eine Kopie beibehalten wird.

Adobe Campaign selbst ermöglicht zwar nicht die Verwaltung von archivierten Dateien, Sie können aber die gewünschten Nachrichten an eine bestimmte Adresse senden, wo sie mithilfe eines externen Systems verarbeitet und archiviert werden.

Dazu werden E-Mail-Dateien, die den gesendeten E-Mails entsprechen, auf einen Remote-Server, z. B. einen SMTP-E-Mail-Server, übertragen. Das Archivierungsziel ist eine BCC-E-Mail-Adresse (für die Versand-Empfänger unsichtbar), die Sie angeben müssen.

Bitte beachten Sie Folgendes:

* Sie können nur eine einzige BCC-E-Mail-Adresse verwenden.

* Nur erfolgreich gesendete E-Mails werden berücksichtigt, Absprünge nicht.

Nachdem E-Mail-BCC konfiguriert wurde, stellen Sie sicher, dass die Funktion in der Versandvorlage oder im Versand über die Option **E-Mail-BCC** aktiviert ist.

:arrow_upper_right: Weitere Informationen finden Sie in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=en#email-bcc)

**Hinweis**: Die BCC-Funktion für E-Mail ist optional. Prüfen Sie diesbezüglich Ihren Lizenzvertrag.

:language_ballon: Als Managed Cloud Services-Benutzer können Sie [Kontakt-Adobe](../start/support.md#support) kontaktieren, um E-Mail-BCC in Kampagne zu aktivieren. Die BCC-E-Mail-Adresse Ihrer Wahl muss dem Adobe-Team zur Verfügung gestellt werden, das sie für Sie konfiguriert.