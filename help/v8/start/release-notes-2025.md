---
title: Versionshinweise 2025 zu Campaign v8 (Konsole)
description: Liste der Funktionen und Verbesserungen in Campaign v8-Versionen 2025
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: b52308bcbe68a7c382918fe28f8166e3bfcb6cde
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 96%

---

# Versionshinweise 2025 {#2025-rn}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der **Campaign v8-Versionen 2025** aufgelistet. Die neueste Version finden Sie auf [dieser Seite](release-notes.md).

Installieren Sie für jede neue Implementierung oder jedes Upgrade auf eine vorhandene Umgebung [die neueste Version](release-notes.md).

>[!BEGINSHADEBOX]

**Auf dieser Seite**

* [Version 8.6.5](#release-8-6-5)
* [Version 8.6.4](#release-8-6-4)
* [Version 8.7.4](#release-8-7-4)
* [Version 8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]

## Version 8.6.5 {#release-8-6-5}

_25. April 2025_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. 

### Neue Funktionen {#features-8-6-5}

**Neuer SMS-Versand-Connector**: Der SMS-Versand-Connector wurde modernisiert und verbessert, um SMPP-Verbindungen im Transceiver-Modus zu aktivieren, persistente SMPP-Verbindungen zu ermöglichen und eine bessere Kompatibilität für Umgebungen sicherzustellen, die von Adobe Campaign Standard aus umgestellt werden. Für alle neuen SMS-Implementierungen ist jetzt ein neues externes SMS-Konto verfügbar. Die vorhandene Implementierung wird weiterhin unterstützt. Es wird jedoch empfohlen, zu diesem neuen, modernen und erweiterten Connector zu wechseln. [Weitere Informationen](../send/sms/sms.md)

### Allgemeine Verbesserungen {#improvements-8-6-5}

* Die globale Leistung der Anwendung wurde im Kontext einer Enterprise-Bereitstellung (FFDA) verbessert, einschließlich der Durchführung des Testversands und der Datenbankbereinigung.

* Um die Sicherheit der gesamten Kommunikation zwischen Anwendungen zu erhöhen, wird mTLS jetzt für externe API-Aufrufe unterstützt.

* Mail Transfer Agent (MTA): Behebung eines Problems, bei dem ein verwaistes untergeordnetes MTA-Element im Status **[!UICONTROL Start ausstehend]** hängen blieb.

### Fehlerbehebungen {#fixes-8-6-5}

Die folgenden Probleme wurden ebenfalls in dieser Version behoben:

NEO-67620, NEO-71534, NEO-80245, NEO-81105, NEO-81758, NEO-81908, NEO-82351, NEO-82742, NEO-83044, NEO-83138, NEO-83350, NEO-83729, NEO-83793, NEO-83809, NEO-84038, NEO-84108, NEO-85269, NEO-86121, NEO-86556, NEO-86739

## Version 8.7.4 {#release-8-7-4}

_10. April 2025_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. Sie ist Kundinnen und Kunden vorbehalten, die **von Adobe Campaign Standard zu Adobe Campaign v8** migrieren, und kann nicht in anderen Umgebungen bereitgestellt werden.
>
>Benutzende von Campaign Standard, die auf Campaign v8 umsteigen, können in der [Dokumentation zur Web-Benutzeroberfläche von Campaign v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration){target="_blank"} mehr über diese Transition erfahren.

### Neue Funktionen {#features-8-7-4}

* **SMS REST API-Unterstützung**: Das REST-API für Transaktionsnachrichten ist nun für den SMS-Kanal verfügbar. Wenn sowohl „email“ als auch „mobilePhone“ in der Payload vorhanden sind, können Sie den Kanal über das Feld „wishedChannel“ angeben. Ohne Angabe wird standardmäßig „email“ verwendet, es sei denn, „wishedChannel“ fordert explizit SMS. 

* **Mehrsprachige Sendungen**: Seit der Version der Campaign Web-Benutzeroberfläche vom April können Sie mehrere E-Mail-Sendungen in verschiedenen Sprachen senden und auf die zugehörigen dynamischen Berichte zugreifen. Diese Funktion wird erst ab Ende April in der Adobe Campaign Web-Benutzeroberfläche verfügbar sein und erfordert ein Server-Update auf Campaign v8.7.4.

### Fehlerbehebungen {#fixes-8-7-4}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-80245, NEO-83559

## Version 8.7.3 {#release-8-7-3}

_14. Februar 2025_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. Sie ist Kundinnen und Kunden vorbehalten, die **von Adobe Campaign Standard zu Adobe Campaign v8** migrieren, und kann nicht in anderen Umgebungen bereitgestellt werden.
>
>Benutzende von Campaign Standard, die auf Campaign v8 umsteigen, können in der [Dokumentation zur Web-Benutzeroberfläche von Campaign v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration){target="_blank"} mehr über diese Transition erfahren.

### Neue Funktionen {#features-8-7-3}

* **Dynamische Berichte für Transaktionsnachrichten**: Sie können jetzt Ihre Transaktionsnachrichten in der Benutzeroberfläche der dynamischen Berichte überwachen. Diese Berichte ermöglichen es Marketing-Fachleuten, alle Berichtsmetriken und Dimensionen von Transaktionsnachrichten sowie die Aufschlüsselung der über eine Vorlage gesendeten Sendungen in Echtzeit anzuzeigen. [Weitere Informationen](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"}

* **REST-APIs für Transaktionsnachrichten**: Ereignisbasierte Transaktions-APIs sind jetzt für E-Mails verfügbar. [Weitere Informationen](../dev/api/get-started-apis.md)

### Fehlerbehebungen {#fixes-8-7-3}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-79373, NEO-81908, NEO-83081

## Version 8.6.4 {#release-8-6-4}

_15. Januar 2025_

### Allgemeine Verbesserungen {#improvements-8-6-4}

* Die Stabilität der Campaign-Anwendung wurde bei der Versandanalyse im Kontext einer [Enterprise-Bereitstellung (FFDA)](../../v8/architecture/enterprise-deployment.md) optimiert.
* Diese Version enthält verbesserte und verstärkte FFDA-Architekturmechanismen, einschließlich Schlüsselverwaltung, Staging und Datenreplikation.
* Für die [Enterprise-Bereitstellung (FFDA)](../../v8/architecture/enterprise-deployment.md) wurden neue technische Workflows eingeführt. Diese Workflows replizieren den Versand und zugehörige Daten, indem sie parallele Replikationsanfragen für die entsprechenden Tabellen zentralisieren. Diese Workflows beginnen mit `Replicate nms`. [Weitere Informationen](../architecture/replication.md)
* Eine neue Option **Watchdog-Supervisor darf den Workflow dauerhaft laufen lassen** ist jetzt in den Workflow-Eigenschaften verfügbar. Wenn diese Option aktiviert ist, werden Workflows nach einem Fehler automatisch neu gestartet. Der Neustart erfolgt standardmäßig alle 30 Sekunden, wenn der Workflow noch immer einen Fehler aufweist. Um dieses Intervall anzupassen, können Sie eine neue Option `XtkWorkflow_WatchdogRestartTimerTimeout` erstellen und einen Datentyp als Ganzzahl festlegen, um die neue Verzögerung anzugeben. Diese Option sollte nur in technischen Workflows aktiviert werden. [Weitere Informationen](../../automation/workflow/workflow-properties.md#execution)

### Verbesserungen bezüglich der Sicherheit {#security-8-6-4}

Die Verbindung mit Adobe-Lösungen und -Anwendungen über das externe **[!UICONTROL Adobe Experience Cloud]**-Konto wurde aktualisiert, um die Sicherheit zu erhöhen.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Kompatibilitätsaktualisierungen {#comp-8-6-4}

Die folgenden FDA-Connectoren wurden hinzugefügt: Mehr dazu erfahren Sie auf [dieser Seite](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks wird jetzt als externe Datenbank mit Adobe Campaign Federated Data Access (FDA) unterstützt. 

* Ein neuer Amazon Redshift FDA ODBC-Connector ist jetzt verfügbar. Er bietet verbesserte Konnektivität, einfachere Wartung und optimierte Kompatibilität. Diese neue Version bietet die folgenden Verbesserungen:

   * Der neue Connector basiert auf der ODBC-Schnittstelle, die auf unsere neuesten FDA-Connectoren ausgerichtet ist. Dies sichert eine langfristige Unterstützung.
   * Außerdem wird ein neuer Mechanismus zum Laden von Daten mit S3-Buckets eingeführt, wodurch die Leistung erheblich verbessert wird.

  Der alte Connector kann weiterhin verwendet werden. Wenn Sie den neuen ausprobieren möchten, wenden Sie sich an den Adobe-Support.

### Fehlerbehebungen {#fixes-8-6-4}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-82665, NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137, NEO-83143.

