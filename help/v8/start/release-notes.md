---
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 607ef2ab8f1f1c7400451019e188c70f8c7d6091
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 74%

---

# Aktuelle Version{#latest-release}

Adobe Campaign wird regelmäßig aktualisiert. Dieser regelmäßige Aktualisierungsrhythmus zielt darauf ab, Ihnen die neuesten und besten Funktionen bereitzustellen, Ihre Umgebung sicher zu halten und Ihr Produkterlebnis zu verbessern. Adobe empfiehlt allen Kundinnen und Kunden dringend, ein Upgrade auf die neueste Version durchzuführen.

Wenn Sie Managed Cloud Services nutzen, wird Ihre Instanz von Adobe mit jeder neuen Version aktualisiert. Adobe wird Sie jeweils kontaktieren und Ihre Umgebungen aktualisieren. Die Campaign-Client-Konsole **muss auf dieselbe Version aktualisiert werden** wie die Campaign-Server. Auf [dieser Seite](../start/connect.md#upgrade-ac-console) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.

Außerdem sollten Sie als Kunde bzw. Kundin sicherstellen, dass Sie die neuesten unterstützten Versionen der in der [Kompatibilitätsmatrix](compatibility-matrix.md) aufgeführten Systeme verwenden. 

## Version 8.5.3 {#release-8-5-3}

_Mittwoch, 28. Mai 2024_

### Migration zu OAuth-Server-zu-Server-Anmeldedaten {#change-8-5-3}

* Ab dieser Version sind ausgehende Campaign-Integrationen mit Adobe-Lösungen und -Apps bei veralteten JWT-Anmeldedaten von Adobe auf OAuth Server-zu-Server-Anmeldedaten angewiesen. Adobe führt die Migration von JWT zu OAuth für Ihre ausgehenden Integrationen durch, z. B. die Integration von Campaign mit Analytics oder die Integration von Experience Cloud-Triggern.

  Wenn Sie eingehende Integrationen mit Campaign implementiert haben, müssen Sie Ihr technisches Konto migrieren, wie im Abschnitt [diese Dokumentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Vorhandene Service-Konto-Anmeldedaten (JWT) funktionieren weiterhin, bis **27. Januar 2025**. Darüber hinaus unterstützt die Developer Console die Erstellung neuer Service Account (JWT)-Anmeldedaten auch weiterhin, bis **3. Juni 2024**. Eine neue JWT-Berechtigung (Service Account) kann nach diesem Datum nicht mehr erstellt oder einem Projekt hinzugefügt werden.


### Fehlerbehebungen {#fixes-8-5-3}

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59 44, NEO-52542

## Version 8.7.1 {#release-8-7-1}

_2. Mai 2024_

>[!AVAILABILITY]
>
>Diese Version ist nur **eingeschränkt verfügbar**. Sie ist Kundinnen und Kunden vorbehalten, die **von Adobe Campaign Standard zu Adobe Campaign v8** migrieren, und kann nicht in anderen Umgebungen bereitgestellt werden.
>
>Benutzende von Campaign Standard, die auf Campaign v8 umsteigen, können in der [Dokumentation zur Web-Benutzeroberfläche von Campaign v8](https://experienceleague.adobe.com/de/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"} mehr über diese Transition erfahren.

### Neue Funktionen {#new-8-7-1}

* **Vorlagen für Rich-Push-Benachrichtigungen**: Sie können jetzt Rich-Push-Benachrichtigungen über Android senden. Rich-Push-Benachrichtigungen sind eine erweiterte Form von Benachrichtigungen an Mobilgeräte, die über einfache Textnachrichten hinausgehen und Multimedia-Elemente wie Bilder, interaktive Schaltflächen oder andere Rich-Media-Inhalte enthalten. [Weitere Informationen](../send/rich-push.md)

* **Branding**: Wenn Sie von Campaign Standard migriert sind, können Ihre technischen Admins nun eine oder mehrere Marken definieren, um die Parameter zu zentralisieren, die sich auf die Markenidentität auswirken, z. B. das Logo der Marke, die Domain der Zugangs-URL zu den Landingpages, Einstellungen zum Nachrichten-Tracking. Sie können diese Marken erstellen und mit verschiedenen Nachrichten oder Landingpages verknüpfen. Diese Konfiguration wird in Vorlagen verwaltet. [Mehr dazu](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=de){target="_blank"}

* **Rest-APIs**: Wenn Sie von Campaign Standard migriert sind, können Sie REST-APIs verwenden, um Integrationen für Adobe Campaign zu erstellen und Ihr eigenes Ökosystem aufzubauen, indem Sie Adobe Campaign mit den von Ihnen verwendeten Technologien verbinden. [Mehr dazu](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=de){target="_blank"}

* **Dynamisches Reporting**: Wenn Sie von Campaign Standard migriert sind, können Sie auf das dynamische Reporting zugreifen, das vollständig anpassbare und in Echtzeit aktualisierte Berichte zum Messen der Wirkung Ihrer Marketing-Aktivitäten bietet. Dadurch kann auf Profildaten zugegriffen werden, was die demografische Analyse nach Profildimensionen wie Geschlecht, Stadt und Alter sowie nach Daten von E-Mail-Kampagnen wie Öffnungen und Klicks ermöglicht. [Mehr dazu](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=de){target="_blank"}

* **Neues Add-on für erweiterte Sicherheit**: Um Ihre Netzwerkverbindung sicherer zu machen und die Sicherheit Ihrer Ressourcen zu verbessern, bietet Adobe Campaign ein neues Enhanced Security-Add-on mit zwei Funktionen: Sichere CMK-Integration und Secure VPN-Tunnelung. [Weitere Informationen](../config/enhanced-security.md)


### Aktualisierungen zur Kompatibilität {#comp-8-7-1}

* Databricks wird jetzt als externe Datenbank mit Adobe Campaign Federated Data Access (FDA) unterstützt. Weiterführende Informationen finden Sie auf [dieser Seite](compatibility-matrix.md#FederatedDataAccessFDA).

* Ab dieser Version sind ausgehende Campaign-Integrationen mit Adobe-Lösungen und -Apps bei veralteten JWT-Anmeldedaten von Adobe auf OAuth Server-zu-Server-Anmeldedaten angewiesen. Adobe führt die Migration von JWT zu OAuth für Ihre ausgehenden Integrationen durch, z. B. die Integration von Campaign mit Analytics oder die Integration von Experience Cloud-Triggern.

  Wenn Sie eingehende Integrationen mit Campaign implementiert haben, müssen Sie Ihr technisches Konto migrieren, wie im Abschnitt [diese Dokumentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Vorhandene Service-Konto-Anmeldedaten (JWT) funktionieren weiterhin, bis **27. Januar 2025**. Darüber hinaus unterstützt die Developer Console die Erstellung neuer Service Account (JWT)-Anmeldedaten auch weiterhin, bis **3. Juni 2024**. Eine neue JWT-Berechtigung (Service Account) kann nach diesem Datum nicht mehr erstellt oder einem Projekt hinzugefügt werden.


### Allgemeine Verbesserungen {#improvements-8-7-1}

* Mehrere Schemata wurden von 32 auf 64 Bit geändert. Dies betrifft nur Kundinnen und Kunden, die von Campaign Standard migrieren. [Mehr dazu](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=de){target="_blank"}

* In Campaign-Tabellen werden die folgenden Attribute jetzt standardmäßig nach Datum und Uhrzeit des Servers ausgefüllt: `lastModified` und `created`. Die `createdBy-id` -Attributwert nun standardmäßig mit der aktuellen Anmelde-ID ausgefüllt. Werte, die von Benutzenden in API-Aufrufen bereitgestellt werden, werden ignoriert. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

### Fehlerbehebungen {#fixes-8-7-1}

Folgende Probleme wurden in dieser Version behoben:
NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054

## Version 8.6.2 {#release-8-6-2}

_23. Februar 2024_

### Fehlerbehebungen {#fixes-8-6-2}

Mit dieser Version wird das folgende Problem behoben:

* Es wurde ein Leistungsproblem behoben, dass in der Mid-Sourcing-Instanz auftrat (NEO-72595).

## Version 8.6.1 {#release-8-6-1}

_14. Februar 2024_

### Neue Funktionen {#new-8-6-1}

* Ab dieser Version haben Sie Zugriff auf die neue **Campaign Web-Benutzeroberfläche**, die in der zentralen Adobe Experience Cloud-Umgebung verfügbar ist. Experience Cloud ist die integrierte Familie von Anwendungen, Produkten und Diensten von Adobe für das digitale Marketing. Über die intuitive Benutzeroberfläche können Sie schnell auf Ihre Cloud-Anwendungen, Produktfunktionen und Dienste zugreifen. [Auf dieser Seite](campaign-ui.md#ac-web-ui) erfahren Sie, wie Sie eine Verbindung mit Adobe Experience Cloud herstellen und auf die Benutzeroberfläche von Adobe Campaign Web zugreifen.


* Adobe Campaign v8 kann jetzt in **Adobe Experience Manager as a Cloud Service** integriert werden, wobei das Authoring ausschließlich über die Adobe Campaign Web-Benutzeroberfläche verfügbar ist. [Weitere Informationen](../connect/ac-aem.md)

* Sie können jetzt Ihre **Adobe Experience Manager Assets-Bibliothek** neben Ihren Experience Cloud-Assets nutzen, auch wenn das Paket „Integration in Adobe Experience Cloud“ auf Ihrer Adobe Campaign-Instanz installiert ist. [Weitere Informationen](../connect/ac-aem.md#assets-library)

### Allgemeine Verbesserungen {#improvements-8-6-1}

* Campaign v8.6 verbessert den Durchsatz für **Tracking-Indikatoren des E-Mail-Versands**. Mit unseren optimierten Prozessen wird die Tracking-Erfassung und Rechenzeit verkürzt, und Sie können Ihre Versandschlüsselindikatoren viel schneller überprüfen.


### Aktualisierungen bei der Zustellbarkeit {#deliverability-8-6-1}

* Bis Februar 2024 muss jedes Unternehmen, das mehr als 5.000 E-Mails über Google oder Yahoo! sendet, eine sogenannte DMARC-Authentifizierungstechnologie (Domain-based Message Authentication Reporting and Conformance) verwenden. Stellen Sie sicher, dass für alle Subdomains, die Sie mit Adobe Campaign verwenden, DMARC-Einträge eingerichtet sind. [Weitere Informationen](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=de){target="_blank"}

* Ab dem 1. Juni 2024, verlangen Google und Yahoo! von Absenderinnen und Absendern die Einhaltung der Vorschrift, eine Ein-Klick-Abmeldung anzubieten. Adobe Campaign unterstützt nun diese Option. [Weitere Informationen](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=de#one-click-list-unsubscribe){target="_blank"}


### Fehlerbehebungen {#fixes-8-6-1}

Folgende Probleme wurden in dieser Version behoben:
NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789