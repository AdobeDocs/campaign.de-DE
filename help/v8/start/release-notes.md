---
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: d4b172bc6b874d542dc9f2725e3bc35679fc7635
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 28%

---

# Neueste Versionen {#latest-release}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der neuesten Campaign v8-Versionen (Konsole) aufgelistet. Weitere Informationen zu Campaign-Versionen und -Upgrades finden Sie auf [dieser Seite](upgrades.md).

## Version 8.6.4 {#release-8-6-4}

_15. Januar 2025_


### Allgemeine Verbesserungen {#improvements-8-6-4}

* Die Stabilität der Campaign-Anwendung wurde bei der Versandanalyse im Kontext einer [Enterprise (FFDA)-Bereitstellung) ](../../v8/architecture/enterprise-deployment.md).
* Diese Version enthält verbesserte und verstärkte FFDA-Architekturmechanismen, einschließlich Schlüsselverwaltung, Staging und Datenreplikation.
* Für die Implementierung von [Enterprise (FFDA) wurden neue technische Workflows ](../../v8/architecture/enterprise-deployment.md). Diese Workflows replizieren Bereitstellungs- und zugehörige Daten, indem sie parallele Replikationsanfragen für die entsprechenden Tabellen zentralisieren. Diese Workflows beginnen mit `Replicate nms`.
* Eine neue Option **Watchdog-Supervisor aktivieren, um den Workflow dauerhaft**, ist jetzt in den Workflow-Eigenschaften verfügbar. Wenn diese Option aktiviert ist, werden Workflows nach einem Fehler automatisch neu gestartet. Der Neustart erfolgt standardmäßig alle 30 Sekunden. Um dieses Intervall anzupassen, können Sie eine neue `XtkWorkflow_WatchdogTimerTimeout` erstellen und einen ganzzahligen Datentyp festlegen, um die neue Verzögerung anzugeben. Diese Option sollte nur in technischen Workflows aktiviert werden.

### Verbesserungen bezüglich der Sicherheit {#security-8-6-4}

Die Verbindung mit Adobe-Lösungen und Apps über das externe Konto **[!UICONTROL Adobe Experience Cloud]** wurde aktualisiert, um die Sicherheit zu erhöhen.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Aktualisierungen zur Kompatibilität {#comp-8-6-4}

Databricks wird jetzt als externe Datenbank mit Adobe Campaign Federated Data Access (FDA) unterstützt. Weiterführende Informationen finden Sie auf [dieser Seite](compatibility-matrix.md#FederatedDataAccessFDA).

### Fehlerbehebungen {#fixes-8-6-4}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-77452, NEO-81127, NEO-81209, NEO-80243, NEO-80314, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-83096, NEO-83081.