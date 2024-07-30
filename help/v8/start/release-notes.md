---
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 0c13ee22a7d40aaa9a8c27d3450ec3275a02748f
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 97%

---

# Neueste Versionen {#latest-release}

Adobe Campaign wird regelmäßig aktualisiert. Dieser regelmäßige Aktualisierungsrhythmus zielt darauf ab, Ihnen die neuesten und besten Funktionen bereitzustellen, Ihre Umgebung sicher zu halten und Ihr Produkterlebnis zu verbessern. Adobe empfiehlt allen Kundinnen und Kunden dringend, ein Upgrade auf die neueste Version durchzuführen. Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der neuesten Campaign v8-Versionen (Konsole) aufgelistet. Weitere Informationen zu Campaign-Versionen und -Aktualisierungen finden Sie auf [dieser Seite](upgrades.md).

Wenn Sie Managed Cloud Services nutzen, wird Ihre Instanz von Adobe mit jeder neuen Version aktualisiert. Adobe wird Sie jeweils kontaktieren und Ihre Umgebungen aktualisieren. Die Campaign-Client-Konsole **muss auf dieselbe Version aktualisiert werden** wie die Campaign-Server. Auf [dieser Seite](../start/connect.md#upgrade-ac-console) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.

Außerdem sollten Sie als Kundin bzw. Kunde sicherstellen, dass Sie die neuesten unterstützten Versionen der in der [Kompatibilitätsmatrix](compatibility-matrix.md) aufgeführten Systeme verwenden.


## Version 8.6.3 {#release-8-6-3}

_30. Juli 2024_

### Neue Funktionen {#new-8-6-3}

* **Rich-Push-Benachrichtigungen**: Sie können jetzt Rich-Push-Benachrichtigungen senden. Rich-Push-Benachrichtigungen sind eine erweiterte Form von Benachrichtigungen an Mobilgeräte, die über einfache Textnachrichten hinausgehen und Multimedia-Elemente wie Bilder, interaktive Schaltflächen oder andere Rich-Media-Inhalte enthalten. Mit dieser Version ist jetzt eine Reihe von Vorlagen für Rich-Push-Benachrichtigungen für Ihre iOS- und Android-Apps verfügbar. [Weitere Informationen](../send/rich-push-android.md)

* Ab dieser Version sind ausgehende Campaign-Integrationen in Adobe-Lösungen und -Apps auf OAuth-Server-zu-Server-Anmeldedaten angewiesen, weil die Anmeldedatenoption „Service-Konto (JWT)“ eingestellt wurde. [Weitere Informationen](release-notes.md#change-8-7-1)

### Allgemeine Verbesserungen {#improvements-8-6-3}

* Um die Sicherheit der gesamten Kommunikation zwischen Anwendungen zu erhöhen, wird mTLS jetzt für externe API-Aufrufe unterstützt.

### Fehlerbehebungen {#fixes-8-6-3}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-79328, NEO-78843, NEO-77795, NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-725 04, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->


## Version 8.5.3 {#release-8-5-3}

_28. Mai 2024_

### Migration zu OAuth-Server-zu-Server-Anmeldedaten {#change-8-5-3}

Ab dieser Version sind ausgehende Campaign-Integrationen in Adobe-Lösungen und -Apps auf OAuth-Server-zu-Server-Anmeldedaten angewiesen, weil die Anmeldedatenoption „Service-Konto (JWT)“ eingestellt wurde. [Weitere Informationen](#change-8-7-1)

### Fehlerbehebungen {#fixes-8-5-3}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-52542


## Mai-Updates {#may-updates}

Die folgende Änderung wurde im Mai veröffentlicht und steht jetzt Benutzenden von Campaign v8 zur Verfügung:

* **Neues Add-on für verbesserte Sicherheit**: Um die Netzwerkverbindung sicherer zu machen und die Sicherheit Ihrer Ressourcen zu verbessern, bietet Adobe Campaign ein neues Add-on für verbesserte Sicherheit an. Die darin enthaltenen Funktionen ermöglichen eine sichere CMK-Integration und sicheres VPN-Tunneling.  [Weitere Informationen](../config/enhanced-security.md)


## Version 8.7.1 {#release-8-7-1}

_2. Mai 2024_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. Sie ist Kundinnen und Kunden vorbehalten, die **von Adobe Campaign Standard zu Adobe Campaign v8** migrieren, und kann nicht in anderen Umgebungen bereitgestellt werden.
>
>Benutzende von Campaign Standard, die auf Campaign v8 umsteigen, können in der [Dokumentation zur Web-Benutzeroberfläche von Campaign v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"} mehr über diese Transition erfahren.

### Neue Funktionen {#new-8-7-1}

* **Vorlagen für Rich-Push-Benachrichtigungen**: Sie können jetzt Rich-Push-Benachrichtigungen über Android senden. Rich-Push-Benachrichtigungen sind eine erweiterte Form von Benachrichtigungen an Mobilgeräte, die über einfache Textnachrichten hinausgehen und Multimedia-Elemente wie Bilder, interaktive Schaltflächen oder andere Rich-Media-Inhalte enthalten. [Weitere Informationen](../send/rich-push-ios.md)

* **Branding**: Wenn Sie von Campaign Standard migriert sind, können Ihre technischen Admins nun eine oder mehrere Marken definieren, um die Parameter zu zentralisieren, die sich auf die Markenidentität auswirken, z. B. das Logo der Marke, die Domain der Zugangs-URL zu den Landingpages, Einstellungen zum Nachrichten-Tracking. Sie können diese Marken erstellen und mit verschiedenen Nachrichten oder Landingpages verknüpfen. Diese Konfiguration wird in Vorlagen verwaltet. [Mehr dazu](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=de){target="_blank"}

* **Rest-APIs**: Wenn Sie von Campaign Standard migriert sind, können Sie REST-APIs verwenden, um Integrationen für Adobe Campaign zu erstellen und Ihr eigenes Ökosystem aufzubauen, indem Sie Adobe Campaign mit den von Ihnen verwendeten Technologien verbinden. [Mehr dazu](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=de){target="_blank"}

* **Dynamisches Reporting**: Wenn Sie von Campaign Standard migriert sind, können Sie auf das dynamische Reporting zugreifen, das vollständig anpassbare und in Echtzeit aktualisierte Berichte zum Messen der Wirkung Ihrer Marketing-Aktivitäten bietet. Dadurch kann auf Profildaten zugegriffen werden, was die demografische Analyse nach Profildimensionen wie Geschlecht, Stadt und Alter sowie nach Daten von E-Mail-Kampagnen wie Öffnungen und Klicks ermöglicht. [Mehr dazu](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=de){target="_blank"}

### Aktualisierungen zur Kompatibilität {#comp-8-7-1}

* Databricks wird jetzt als externe Datenbank mit Adobe Campaign Federated Data Access (FDA) unterstützt. Weiterführende Informationen finden Sie auf [dieser Seite](compatibility-matrix.md#FederatedDataAccessFDA).

### Migration zu OAuth-Server-zu-Server-Anmeldedaten {#change-8-7-1}

Ab dieser Version sind ausgehende Campaign-Integrationen in Adobe-Lösungen und -Apps auf OAuth-Server-zu-Server-Anmeldedaten angewiesen, weil die Anmeldedatenoption „Service-Konto (JWT)“ eingestellt wurde. Adobe führt die Migration von JWT zu OAuth für Ihre ausgehenden Integrationen durch, z. B. die Integration von Campaign-Analytics oder die Integration von Experience Cloud Triggers.

Wenn Sie eingehende Integrationen in Campaign implementiert haben, müssen Sie Ihr technisches Konto migrieren, wie in [dieser Dokumentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"} beschrieben. Bereits vorhandene Service-Konto(JWT)-Anmeldedaten funktionieren noch bis zum **27. Januar 2025** weiterhin.

### Allgemeine Verbesserungen {#improvements-8-7-1}

* Mehrere Schemata wurden von 32 auf 64 Bit geändert. Dies betrifft nur Kundinnen und Kunden, die von Campaign Standard migrieren. [Mehr dazu](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=de){target="_blank"}

* In Campaign-Tabellen werden die folgenden Attribute jetzt standardmäßig nach Datum und Uhrzeit des Servers ausgefüllt: `lastModified` und `created`. Der `createdBy-id`-Attributwert wird nun standardmäßig mit der aktuellen Anmelde-ID ausgefüllt. Werte, die von Benutzenden in API-Aufrufen bereitgestellt werden, werden ignoriert. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* Um die Sicherheit der gesamten Kommunikation zwischen Anwendungen zu erhöhen, wird mTLS jetzt für externe API-Aufrufe unterstützt.

### Fehlerbehebungen {#fixes-8-7-1}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054
