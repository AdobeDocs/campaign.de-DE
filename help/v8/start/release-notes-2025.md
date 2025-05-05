---
title: Versionshinweise 2025 zu Campaign v8 (Konsole)
description: Liste der Funktionen und Verbesserungen in Campaign v8-Versionen 2025
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: 66e4b59915eae595b28076622f7bcfb5b5a0ffa4
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 66%

---

# Versionshinweise 2025 {#2025-rn}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der Campaign **2025 v8-Versionen**. Die neuesten Versionen sind auf [dieser Seite](release-notes.md) aufgeführt.

>[!BEGINSHADEBOX]

**Auf dieser Seite**

* Campaign v8.7 - [Version 8.7.2](#release-8-7-2) | [Version 8.7.](#release-8-7-3)


>[!ENDSHADEBOX]


## Version 8.7.3 {#release-8-7-3}

_14. Februar 2025_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. Sie ist Kundinnen und Kunden vorbehalten, die **von Adobe Campaign Standard zu Adobe Campaign v8** migrieren, und kann nicht in anderen Umgebungen bereitgestellt werden.
>
>Wenn Sie als Campaign Standard-Anwender zu Campaign v8 wechseln, erfahren Sie mehr über diesen Wechsel in der [Dokumentation zur Web-Benutzeroberfläche von Campaign v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Neue Funktionen {#features-8-7-3}

* **Dynamisches Reporting für Transaktionsnachrichten** - Sie können jetzt Ihre Transaktionsnachrichten in der Benutzeroberfläche des dynamischen Reportings überwachen. Diese Berichte ermöglichen es dem Marketing-Experten, alle Berichtsmetriken und Dimensionen von Transaktionsnachrichten sowie die Aufschlüsselung der über eine Vorlage gesendeten Sendungen in Echtzeit anzuzeigen. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}

* **REST-APIs für Transaktionsnachrichten** - Ereignisbasierte Transaktions-APIs sind jetzt für E-Mails verfügbar. [Weitere Informationen](https://experienceleague.adobe.com/de/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}

### Fehlerbehebungen {#fixes-8-7-3}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-79373, NEO-81908, NEO-83081

## Version 8.7.2 {#release-8-7-2}

_3. September 2024_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. Sie ist Kundinnen und Kunden vorbehalten, die **von Adobe Campaign Standard zu Adobe Campaign v8** migrieren, und kann nicht in anderen Umgebungen bereitgestellt werden.
>
>Wenn Sie als Campaign Standard-Anwender zu Campaign v8 wechseln, erfahren Sie mehr über diesen Wechsel in der [Dokumentation zur Web-Benutzeroberfläche von Campaign v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Neue Funktionen {#new-8-7-2}

* **Neuer SMS-Versand-Connector**: Der SMS-Versand-Connector wurde modernisiert und verbessert, um SMPP-Verbindungen im Transceiver-Modus zu aktivieren, persistente SMPP-Verbindungen zu ermöglichen und eine bessere Kompatibilität für Umgebungen sicherzustellen, die von Adobe Campaign Standard aus umgestellt werden. Für alle neuen SMS-Implementierungen ist jetzt ein neues externes SMS-Konto verfügbar. Die vorhandene Implementierung wird weiterhin unterstützt. Es wird jedoch empfohlen, zu diesem neuen, modernen und erweiterten Connector zu wechseln. [Weitere Informationen](../send/sms/sms.md)

* **Rich-Push-Benachrichtigungen (GA)**: Sie können jetzt Rich-Push-Benachrichtigungen senden. Rich-Push-Benachrichtigungen sind eine erweiterte Form von Benachrichtigungen an Mobilgeräte, die über einfache Textnachrichten hinausgehen und Multimedia-Elemente wie Bilder, interaktive Schaltflächen oder andere Rich-Media-Inhalte enthalten. Mit dieser Version ist jetzt eine Reihe von Vorlagen für Rich-Push-Benachrichtigungen für Ihre iOS- und Android-Apps verfügbar. [Weitere Informationen](../send/rich-push-android.md)

* **Branding**: Branding-Optionen sind jetzt für alle Kanäle verfügbar, einschließlich SMS und Direkt-Mail. [Weitere Informationen](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=de){target="_blank"}

### Fehlerbehebungen {#fixes-8-7-2}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328
