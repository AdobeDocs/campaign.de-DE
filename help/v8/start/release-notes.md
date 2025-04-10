---
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: ff874a8e06303625b4c96f49fdf4f303b50fb908
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 17%

---

# Neueste Versionen {#latest-release}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der Campaign v8-Konsole (**Versionen)**. Weitere Informationen zu Campaign-Versionen, -Versionen und -Upgrades finden [ auf dieser Seite ](upgrades.md). Weitere Versionen sind im Abschnitt Vorherige Versionen dieser Dokumentation aufgeführt.

>[!BEGINSHADEBOX]

**Auf dieser Seite**

* [Version 8.7.4](#release-8-7-4)
* [Version 8.7.](#release-8-7-3)
* [Version 8.6.4](#release-8-6-4)

>[!ENDSHADEBOX]

## Version 8.7.4 {#release-8-7-4}

_Freitag, 10. April 2025_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. Sie ist Kundinnen und Kunden vorbehalten, die **von Adobe Campaign Standard zu Adobe Campaign v8** migrieren, und kann nicht in anderen Umgebungen bereitgestellt werden.
>
>Wenn Sie als Campaign Standard-Anwender zu Campaign v8 wechseln, erfahren Sie mehr über diesen Wechsel in der [Dokumentation zur Web-Benutzeroberfläche von Campaign v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration).

### Neue Funktionen {#features-8-7-4}

* **SMS-REST-API-**: Die REST-API für Transaktionsnachrichten ist jetzt für den SMS-Kanal verfügbar. Wenn sowohl E-Mail als auch Mobiltelefon in der Payload vorhanden sind, können Sie das Feld „wishChannel“ verwenden, um den Kanal anzugeben. Wenn keine E-Mail-Adresse angegeben wird, wird sie standardmäßig verwendet, es sei denn, WishedChannel fordert explizit SMS an.

* **Mehrsprachige Sendungen** - Mit der Veröffentlichung der Campaign Web-Benutzeroberfläche im April können Sie mehrere E-Mail-Sendungen in verschiedenen Sprachen senden und auf die zugehörigen dynamischen Berichte zugreifen. Diese Funktion ist nur Ende April in der Web-Benutzeroberfläche von Adobe Campaign verfügbar und erfordert ein Server-Update auf Campaign v8.7.4.

### Fehlerbehebungen {#fixes-8-7-4}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-80245, NEO-83559

## Version 8.6.4 {#release-8-6-4}

_15. Januar 2025_

### Allgemeine Verbesserungen {#improvements-8-6-4}

* Die Stabilität der Campaign-Anwendung wurde bei der Versandanalyse im Kontext einer [Enterprise (FFDA)-Bereitstellung) ](../../v8/architecture/enterprise-deployment.md).
* Diese Version enthält verbesserte und verstärkte FFDA-Architekturmechanismen, einschließlich Schlüsselverwaltung, Staging und Datenreplikation.
* Für die Implementierung von [Enterprise (FFDA) wurden neue technische Workflows ](../../v8/architecture/enterprise-deployment.md). Diese Workflows replizieren Bereitstellungs- und zugehörige Daten, indem sie parallele Replikationsanfragen für die entsprechenden Tabellen zentralisieren. Diese Workflows beginnen mit `Replicate nms`. [Weitere Informationen](../architecture/replication.md)
* Eine neue Option **Watchdog-Supervisor aktivieren, um den Workflow dauerhaft**, ist jetzt in den Workflow-Eigenschaften verfügbar. Wenn diese Option aktiviert ist, werden Workflows nach einem Fehler automatisch neu gestartet. Der Neustart erfolgt standardmäßig alle 30 Sekunden, wenn der Workflow noch immer einen Fehler aufweist. Um dieses Intervall anzupassen, können Sie eine neue `XtkWorkflow_WatchdogRestartTimerTimeout` erstellen und einen ganzzahligen Datentyp festlegen, um die neue Verzögerung anzugeben. Diese Option sollte nur in technischen Workflows aktiviert werden. [Weitere Informationen](../../automation/workflow/workflow-properties.md#execution)

### Verbesserungen bezüglich der Sicherheit {#security-8-6-4}

Die Verbindung mit Adobe-Lösungen und -Anwendungen über das externe **[!UICONTROL Adobe Experience Cloud]**-Konto wurde aktualisiert, um die Sicherheit zu erhöhen.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Kompatibilitätsaktualisierungen {#comp-8-6-4}

Die folgenden FDA-Connectoren wurden hinzugefügt. Mehr dazu erfahren Sie auf [dieser Seite](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks wird jetzt als externe Datenbank mit Adobe Campaign Federated Data Access (FDA) unterstützt.

* Ein neuer Amazon Redshift FDA ODBC-Connector ist jetzt verfügbar. Es bietet verbesserte Konnektivität, einfachere Wartung und verbesserte Kompatibilität. Diese neue Version bietet die folgenden Verbesserungen:

   * Der neue Connector basiert auf der ODBC-Schnittstelle, die mit unseren neuesten FDA-Connectoren übereinstimmt. Dies sichert eine langfristige Unterstützung.
   * Außerdem wird ein neuer Datenlademechanismus mit S3-Buckets eingeführt, wodurch die Leistung erheblich verbessert wird.

  Der alte Connector kann weiterhin verwendet werden. Wenn Sie die neue Version ausprobieren möchten, wenden Sie sich an den Adobe-Support.

### Fehlerbehebungen {#fixes-8-6-4}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77452, NEO-78946, NEO-80243, NEO-81127, NEO-81209, NEO-77162, NEO-81223, NEO-81287, NEO-79373, NEO-80314, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591 NEO-82592, NEO-82640, NEO-82665, NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137 83143.

