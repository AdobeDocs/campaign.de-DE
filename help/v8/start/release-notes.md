---
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 4a4bcb0b540d6e8a426839e77bf81ad30eb93653
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 51%

---

# Neueste Versionen {#latest-release}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der Campaign v8-Konsole (**Versionen)**. Weitere Informationen zu Campaign-Versionen, -Versionen und -Upgrades finden [ auf dieser Seite ](upgrades.md). Weitere Versionen sind im Abschnitt Vorherige Versionen dieser Dokumentation aufgeführt.

## Version 8.6.4 {#release-8-6-4}

_15. Januar 2025_

### Allgemeine Verbesserungen {#improvements-8-6-4}

* Die Stabilität der Campaign-Anwendung wurde bei der Versandanalyse im Kontext einer [Enterprise (FFDA)-Bereitstellung) ](../../v8/architecture/enterprise-deployment.md).
* Diese Version enthält verbesserte und verstärkte FFDA-Architekturmechanismen, einschließlich Schlüsselverwaltung, Staging und Datenreplikation.
* Für die Implementierung von [Enterprise (FFDA) wurden neue technische Workflows ](../../v8/architecture/enterprise-deployment.md). Diese Workflows replizieren Bereitstellungs- und zugehörige Daten, indem sie parallele Replikationsanfragen für die entsprechenden Tabellen zentralisieren. Diese Workflows beginnen mit `Replicate nms`. [Weitere Informationen](../architecture/replication.md)
* Eine neue Option **Watchdog-Supervisor aktivieren, um den Workflow dauerhaft**, ist jetzt in den Workflow-Eigenschaften verfügbar. Wenn diese Option aktiviert ist, werden Workflows nach einem Fehler automatisch neu gestartet. Der Neustart erfolgt standardmäßig alle 30 Sekunden, wenn der Workflow noch immer einen Fehler aufweist. Um dieses Intervall anzupassen, können Sie eine neue `XtkWorkflow_WatchdogTimerTimeout` erstellen und einen ganzzahligen Datentyp festlegen, um die neue Verzögerung anzugeben. Diese Option sollte nur in technischen Workflows aktiviert werden. [Weitere Informationen](../../automation/workflow/workflow-properties.md#execution)

### Verbesserungen bezüglich der Sicherheit {#security-8-6-4}

Die Verbindung mit Adobe-Lösungen und Apps über das externe Konto **[!UICONTROL Adobe Experience Cloud]** wurde aktualisiert, um die Sicherheit zu erhöhen.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Aktualisierungen zur Kompatibilität {#comp-8-6-4}

Databricks wird jetzt als externe Datenbank mit Adobe Campaign Federated Data Access (FDA) unterstützt. Weiterführende Informationen finden Sie auf [dieser Seite](compatibility-matrix.md#FederatedDataAccessFDA).

### Fehlerbehebungen {#fixes-8-6-4}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77452, NEO-78946, NEO-80243, NEO-81127, NEO-81209, NEO-77162, NEO-81223, NEO-81287, NEO-79373, NEO-80314, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591 NEO-82592, NEO-82640, NEO-82665, NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137 83143.

## Version 8.7.2 {#release-8-7-2}

_3. September 2024_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. Sie ist Kundinnen und Kunden vorbehalten, die **von Adobe Campaign Standard zu Adobe Campaign v8** migrieren, und kann nicht in anderen Umgebungen bereitgestellt werden.
>
>Benutzende von Campaign Standard, die auf Campaign v8 umsteigen, können in der [Dokumentation zur Web-Benutzeroberfläche von Campaign v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration){target="_blank"} mehr über diese Transition erfahren.

### Neue Funktionen {#new-8-7-2}

* **Neuer SMS-Versand-Connector**: Der SMS-Versand-Connector wurde modernisiert und verbessert, um SMPP-Verbindungen im Transceiver-Modus zu aktivieren, persistente SMPP-Verbindungen zu ermöglichen und eine bessere Kompatibilität für Umgebungen sicherzustellen, die von Adobe Campaign Standard aus umgestellt werden. Für alle neuen SMS-Implementierungen ist jetzt ein neues externes SMS-Konto verfügbar. Die vorhandene Implementierung wird weiterhin unterstützt. Es wird jedoch empfohlen, zu diesem neuen, modernen und erweiterten Connector zu wechseln. [Weitere Informationen](../send/sms/sms.md)

* **Rich-Push-Benachrichtigungen (GA)**: Sie können jetzt Rich-Push-Benachrichtigungen senden. Rich-Push-Benachrichtigungen sind eine erweiterte Form von Benachrichtigungen an Mobilgeräte, die über einfache Textnachrichten hinausgehen und Multimedia-Elemente wie Bilder, interaktive Schaltflächen oder andere Rich-Media-Inhalte enthalten. Mit dieser Version ist jetzt eine Reihe von Vorlagen für Rich-Push-Benachrichtigungen für Ihre iOS- und Android-Apps verfügbar. [Weitere Informationen](../send/rich-push-android.md)

* **Branding**: Branding-Optionen sind jetzt für alle Kanäle verfügbar, einschließlich SMS und Direkt-Mail. [Weitere Informationen](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=de){target="_blank"}

### Fehlerbehebungen {#fixes-8-7-2}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328