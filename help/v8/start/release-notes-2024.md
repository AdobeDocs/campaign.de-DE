---
title: Versionshinweise 2024 zu Campaign v8 (Konsole)
description: Liste der Funktionen und Verbesserungen in Campaign v8-Versionen 2024
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: 041df8d2d6128d72a04008affbc9680ba5b640a1
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 87%

---

# Versionshinweise 2024 {#2024-rn}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der **Campaign v8-Versionen 2024** aufgelistet.

>[!BEGINSHADEBOX]

**Auf dieser Seite**

* Campaign v8.7 - [Version 8.7.1](#release-8-7-1)
* Campaign v8.6 - [Version 8.6.1](#release-8-6-1) | [Version 8.6.2](#release-8-6-2) | [Version 8.6.3 ](#release-8-6-3)
* Campaign v8.5 - [Version 8.5.3](#release-8-5-3)

>[!ENDSHADEBOX]



## Version 8.7.1 {#release-8-7-1}

_2. Mai 2024_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. Sie ist Kundinnen und Kunden vorbehalten, die **von Adobe Campaign Standard zu Adobe Campaign v8** migrieren, und kann nicht in anderen Umgebungen bereitgestellt werden.
>
>Benutzende von Campaign Standard, die auf Campaign v8 umsteigen, können in der [Dokumentation zur Web-Benutzeroberfläche von Campaign v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/acs-migration){target="_blank"} mehr über diese Transition erfahren.

### Neue Funktionen {#new-8-7-1}

* **Vorlagen für Rich-Push-Benachrichtigungen**: Sie können jetzt Rich-Push-Benachrichtigungen über Android senden. Rich-Push-Benachrichtigungen sind eine erweiterte Form von Benachrichtigungen an Mobilgeräte, die über einfache Textnachrichten hinausgehen und Multimedia-Elemente wie Bilder, interaktive Schaltflächen oder andere Rich-Media-Inhalte enthalten. [Weitere Informationen](../send/rich-push-ios.md)

* **Branding**: Wenn Sie von Campaign Standard migriert sind, können Ihre technischen Admins nun eine oder mehrere Marken definieren, um die Parameter zu zentralisieren, die sich auf die Markenidentität auswirken, z. B. das Logo der Marke, die Domain der Zugangs-URL zu den Landingpages, Einstellungen zum Nachrichten-Tracking. Sie können diese Marken erstellen und mit verschiedenen Nachrichten oder Landingpages verknüpfen. Diese Konfiguration wird in Vorlagen verwaltet. [Mehr dazu](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=de){target="_blank"}

* **Rest-APIs**: Wenn Sie von Campaign Standard migriert sind, können Sie REST-APIs verwenden, um Integrationen für Adobe Campaign zu erstellen und Ihr eigenes Ökosystem aufzubauen, indem Sie Adobe Campaign mit den von Ihnen verwendeten Technologien verbinden. [Mehr dazu](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=de){target="_blank"}

* **Dynamisches Reporting**: Wenn Sie von Campaign Standard migriert sind, können Sie auf das dynamische Reporting zugreifen, das vollständig anpassbare und in Echtzeit aktualisierte Berichte zum Messen der Wirkung Ihrer Marketing-Aktivitäten bietet. Dadurch kann auf Profildaten zugegriffen werden, was die demografische Analyse nach Profildimensionen wie Geschlecht, Stadt und Alter sowie nach Daten von E-Mail-Kampagnen wie Öffnungen und Klicks ermöglicht. [Mehr dazu](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=de){target="_blank"}

### Kompatibilitätsaktualisierungen {#comp-8-7-1}

Die folgenden FDA-Connectoren wurden hinzugefügt. Mehr dazu erfahren Sie auf [dieser Seite](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks wird jetzt als externe Datenbank mit Adobe Campaign Federated Data Access (FDA) unterstützt.

* Ein neuer Amazon Redshift FDA ODBC-Connector ist jetzt verfügbar. Es bietet verbesserte Konnektivität, einfachere Wartung und verbesserte Kompatibilität. Diese neue Version bietet die folgenden Verbesserungen:

   * Der neue Connector basiert auf der ODBC-Schnittstelle, die mit unseren neuesten FDA-Connectoren übereinstimmt. Dies sichert eine langfristige Unterstützung.
   * Außerdem wird ein neuer Datenlademechanismus mit S3-Buckets eingeführt, wodurch die Leistung erheblich verbessert wird.

  Der alte Connector kann weiterhin verwendet werden. Wenn Sie die neue Version ausprobieren möchten, wenden Sie sich an den Adobe-Support.

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



## Version 8.6.3 {#release-8-6-3}

_30. Juli 2024_

### Neue Funktionen {#new-8-6-3}

* **Rich-Push-Benachrichtigungen**: Sie können jetzt Rich-Push-Benachrichtigungen senden. Rich-Push-Benachrichtigungen sind eine erweiterte Form von Benachrichtigungen an Mobilgeräte, die über einfache Textnachrichten hinausgehen und Multimedia-Elemente wie Bilder, interaktive Schaltflächen oder andere Rich-Media-Inhalte enthalten. Mit dieser Version ist jetzt eine Reihe von Vorlagen für Rich-Push-Benachrichtigungen für Ihre iOS- und Android-Apps verfügbar. [Weitere Informationen](../send/rich-push-android.md)

* Ab dieser Version sind ausgehende Campaign-Integrationen in Adobe-Lösungen und -Apps auf OAuth-Server-zu-Server-Anmeldedaten angewiesen, weil die Anmeldedatenoption „Service-Konto (JWT)“ eingestellt wurde. [Weitere Informationen](release-notes-2024.md#change-8-7-1)

### Allgemeine Verbesserungen {#improvements-8-6-3}

* Um die Sicherheit der gesamten Kommunikation zwischen Anwendungen zu erhöhen, wird mTLS jetzt für externe API-Aufrufe unterstützt.

### Fehlerbehebungen {#fixes-8-6-3}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-79328, NEO-78843, NEO-77795, NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-72504, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->


## Updates vom Mai 2024 {#may-updates}

Die folgende Änderung wurde im Mai veröffentlicht und steht jetzt Benutzenden von Campaign v8 zur Verfügung:

* **Neues Add-on für verbesserte Sicherheit**: Um die Netzwerkverbindung sicherer zu machen und die Sicherheit Ihrer Ressourcen zu verbessern, bietet Adobe Campaign ein neues Add-on für verbesserte Sicherheit an. Die darin enthaltenen Funktionen ermöglichen eine sichere CMK-Integration und sicheres VPN-Tunneling.  [Weitere Informationen](../config/enhanced-security.md)

## Version 8.6.2 {#release-8-6-2}

_23. Februar 2024_

### Fehlerbehebungen {#fixes-8-6-2}

Mit dieser Version wird das folgende Problem behoben:

* Es wurde ein Leistungsproblem behoben, dass in der Mid-Sourcing-Instanz auftrat (NEO-72595).

## Version 8.6.1 {#release-8-6-1}

_14. Februar 2024_

### Neue Funktionen {#new-8-6-1}

* Ab dieser Version haben Sie Zugriff auf die neue **Campaign Web-Benutzeroberfläche**, die in der zentralen Adobe Experience Cloud-Umgebung verfügbar ist. Experience Cloud ist die integrierte Familie von Anwendungen, Produkten und Diensten von Adobe für das digitale Marketing. Über die intuitive Benutzeroberfläche können Sie schnell auf Ihre Cloud-Anwendungen, Produktfunktionen und Dienste zugreifen. [Auf dieser Seite](campaign-ui.md#ac-web-ui) erfahren Sie, wie Sie eine Verbindung mit Adobe Experience Cloud herstellen und auf die Benutzeroberfläche von Adobe Campaign Web zugreifen.

  >[!AVAILABILITY]
  >
  >Die Web-Benutzeroberfläche von Campaign steht nur Benutzenden zur Verfügung, die über ihre Adobe ID eine Verbindung zu Adobe Campaign herstellen. Weitere Informationen zu [Adobe Identity Management System (IMS)](https://helpx.adobe.com/de/enterprise/using/identity.html){target="_blank"}.
  >

* Adobe Campaign v8 kann jetzt in **Adobe Experience Manager as a Cloud Service** integriert werden, wobei das Authoring ausschließlich über die Adobe Campaign Web-Benutzeroberfläche verfügbar ist. [Weitere Informationen](../connect/ac-aem.md)

* Sie können jetzt Ihre **Adobe Experience Manager Assets-Bibliothek** neben Ihren Experience Cloud-Assets nutzen, auch wenn das Paket „Integration in Adobe Experience Cloud“ auf Ihrer Adobe Campaign-Instanz installiert ist. [Weitere Informationen](../connect/ac-aem.md#assets-library)

### Allgemeine Verbesserungen {#improvements-8-6-1}

* Campaign v8.6 verbessert den Durchsatz für **Tracking-Indikatoren des E-Mail-Versands**. Mit unseren optimierten Prozessen wird die Tracking-Erfassung und Rechenzeit verkürzt, und Sie können Ihre Versandschlüsselindikatoren viel schneller überprüfen.


### Aktualisierungen bei der Zustellbarkeit {#deliverability-8-6-1}

* Bis Februar 2024 muss jedes Unternehmen, das mehr als 5.000 E-Mails über Google oder Yahoo! sendet, eine sogenannte DMARC-Authentifizierungstechnologie (Domain-based Message Authentication Reporting and Conformance) verwenden. Stellen Sie sicher, dass für alle Subdomains, die Sie mit Adobe Campaign verwenden, DMARC-Einträge eingerichtet sind. [Weitere Informationen](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=de){target="_blank"}

* Ab dem 1. Juni 2024, verlangen Google und Yahoo! von Absenderinnen und Absendern die Einhaltung der Vorschrift, eine Ein-Klick-Abmeldung anzubieten. Adobe Campaign unterstützt nun diese Option. [Weitere Informationen](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#list-unsubscribe){target="_blank"}


### Fehlerbehebungen {#fixes-8-6-1}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789



## Version 8.5.3 {#release-8-5-3}

_28. Mai 2024_

### Migration zu OAuth-Server-zu-Server-Anmeldedaten {#change-8-5-3}

Ab dieser Version sind ausgehende Campaign-Integrationen in Adobe-Lösungen und -Apps auf OAuth-Server-zu-Server-Anmeldedaten angewiesen, weil die Anmeldedatenoption „Service-Konto (JWT)“ eingestellt wurde. [Weitere Informationen](#change-8-7-1)

### Fehlerbehebungen {#fixes-8-5-3}

Die folgenden Probleme wurden in dieser Version behoben:

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-52542