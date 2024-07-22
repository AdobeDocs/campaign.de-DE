---
title: Frühzeitige Versionshinweise zu Campain v8
description: Frühzeitige Veröffentlichung von Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: dfc86ebaa2acc0b7777843b2d1d370939b6bfcc2
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 49%

---

# Frühere Versionshinweise {#e-new-release}

Auf dieser Seite werden Verbesserungen und Fehlerbehebungen beschrieben, die in der nächsten Version von Campaign v8 enthalten sein werden. **Die nachfolgenden frühzeitigen Versionshinweise können ohne vorherige Ankündigung bis zum Verfügbarkeitsdatum der Version geändert werden**. Links, Bildschirme und die aktualisierte Dokumentation werden am Veröffentlichungsdatum in den [Versionshinweisen](release-notes.md) veröffentlicht.

## Version 8.7.2 {#release-8-7-2}

_Mittwoch, 30. Juli 2024_


>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. Sie ist Kundinnen und Kunden vorbehalten, die **von Adobe Campaign Standard zu Adobe Campaign v8** migrieren, und kann nicht in anderen Umgebungen bereitgestellt werden.
>
>Benutzende von Campaign Standard, die auf Campaign v8 umsteigen, können in der [Dokumentation zur Web-Benutzeroberfläche von Campaign v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"} mehr über diese Transition erfahren.

### Neue Funktionen {#new-8-7-2}

* **Neuer SMS-Versand-Connector** - Der SMS-Versand-Connector wurde modernisiert und verbessert, um SMPP-Verbindungen im Transceiver-Modus zu aktivieren, persistente SMPP-Verbindungen zu ermöglichen und eine bessere Kompatibilität für Umgebungen sicherzustellen, die von Adobe Campaign Standard aus umgestellt werden. Für alle neuen SMS-Implementierungen ist jetzt ein neues externes SMS-Konto verfügbar. Die vorhandene Implementierung wird weiterhin unterstützt. Es wird jedoch empfohlen, zu diesem neuen modernen und erweiterten Connector zu wechseln.

* **Rich-Push-Benachrichtigung (GA)** - Sie können jetzt Rich-Push-Benachrichtigungen senden. Rich-Push-Benachrichtigungen sind eine erweiterte Form von Benachrichtigungen an Mobilgeräte, die über einfache Textnachrichten hinausgehen und Multimedia-Elemente wie Bilder, interaktive Schaltflächen oder andere Rich-Media-Inhalte enthalten. Mit dieser Version sind jetzt eine Reihe von Vorlagen für Rich-Push-Benachrichtigungen für Ihre iOS- und Android-Apps verfügbar. [Weitere Informationen](../send/rich-push.md)

* **Branding** - Branding-Optionen sind jetzt für alle Kanäle verfügbar, einschließlich SMS und Briefpost. [Mehr dazu](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=de){target="_blank"}


### Fehlerbehebungen {#fixes-8-7-2}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-76592, NEO-75400, NEO-77406, NEO-77674, NEO-77899, NEO-73989, NEO-76064, NEO-760 39, NEO-76040, NEO-76845, NEO-76664, NEO-76682, NEO-7663, NEO-73602, NEO-72915, NEO-7 8134, NEO-77000, NEO-77002, NEO-76955, NEO-76864, NEO-76926, NEO-76495, NEO-77168 O-41058, NEO-75581, NEO-74647, NEO-74585, NEO-74586, NEO-74831, NEO-77319, NEO-786 7.

## Version 8.6.3 {#release-8-6-3}

_Mittwoch, 30. Juli 2024_


### Neue Funktionen {#new-8-6-3}

* **Rich-Push-Benachrichtigung** - Sie können jetzt Rich-Push-Benachrichtigungen senden. Rich-Push-Benachrichtigungen sind eine erweiterte Form von Benachrichtigungen an Mobilgeräte, die über einfache Textnachrichten hinausgehen und Multimedia-Elemente wie Bilder, interaktive Schaltflächen oder andere Rich-Media-Inhalte enthalten. Mit dieser Version sind jetzt eine Reihe von Vorlagen für Rich-Push-Benachrichtigungen für Ihre iOS- und Android-Apps verfügbar. [Weitere Informationen](../send/rich-push.md)

* Ab dieser Version sind ausgehende Campaign-Integrationen in Adobe-Lösungen und -Apps auf OAuth-Server-zu-Server-Anmeldedaten angewiesen, weil die Anmeldedatenoption „Service-Konto (JWT)“ eingestellt wurde. [Weitere Informationen](release-notes.md#change-8-7-1)


### Allgemeine Verbesserungen {#improvements-8-6-3}

* Um die Sicherheit der gesamten Kommunikation zwischen Anwendungen zu erhöhen, wird mTLS jetzt für externe API-Aufrufe unterstützt.

### Fehlerbehebungen {#fixes-8-6-3}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-72504, NEO-70263, NEO-67620, NEO-63 97, NEO-58596, NEO-56832

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->