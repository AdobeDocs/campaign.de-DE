---
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Release Notes
role: User
level: Beginner
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 3b790305984436f1168f9c73aa09df509b2217f0
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 24%

---

# Aktuelle Version{#latest-release}

Adobe Campaign wird regelmäßig aktualisiert. Dieser regelmäßige Aktualisierungsrhythmus zielt darauf ab, Ihnen die neuesten und besten Funktionen bereitzustellen, Ihre Umgebung sicher zu halten und Ihr Produkterlebnis zu verbessern. Adobe empfiehlt allen Kunden dringend ein Upgrade auf die neueste Version. Erfahren Sie mehr über Campaign-Versionen und Empfehlungen [auf dieser Seite](upgrades.md).

Als Benutzer von Managed Cloud Service wird Ihre Instanz durch Adobe mit jeder neuen Version aktualisiert. Adobe wird Sie kontaktieren und Ihre Umgebungen aktualisieren. Campaign-Clientkonsole **muss auf dieselbe Version aktualisiert werden** als Campaign-Server. Informationen zum Aktualisieren der Clientkonsole finden Sie in diesem Abschnitt [page](../start/connect.md#upgrade-ac-console).

Außerdem sollten Sie als Kunde bzw. Kundin sicherstellen, dass Sie die neuesten unterstützten Versionen der in der [Kompatibilitätsmatrix](compatibility-matrix.md) aufgeführten Systeme verwenden. 


## Version 8.6.2 {#release-8-6-2}

_23.02.2024_

### Fehlerbehebungen {#fixes-8-6-2}

Dieses Release behebt das folgende Problem:

* Fehlerkorrektur - In der Mid-Sourcing-Instanz tritt jetzt kein Leistungsproblem mehr auf (NEO-72595).

## Version 8.6.1 {#release-8-6-1}

_14. Februar 2024_

### Neuheiten {#new-8-6-1}

* Ab dieser Version haben Sie Zugriff auf die neue **Campaign-Webbenutzeroberfläche**, verfügbar in der zentralen Adobe Experience Cloud-Umgebung. Experience Cloud ist die integrierte Familie von Anwendungen, Produkten und Diensten von Adobe für das digitale Marketing. Über die intuitive Benutzeroberfläche können Sie schnell auf Ihre Cloud-Anwendungen, Produktfunktionen und Dienste zugreifen. Erfahren Sie, wie Sie eine Verbindung zu Adobe Experience Cloud herstellen und auf die Adobe Campaign-Web-Oberfläche zugreifen. [auf dieser Seite](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8 ist jetzt mit **Adobe Experience Manager as a Cloud Service**, wobei das Authoring ausschließlich über die Adobe Campaign-Web-Benutzeroberfläche verfügbar ist. [Weitere Informationen](../connect/ac-aem.md)

* Sie können jetzt Ihre **Adobe Experience Manager Assets-Bibliothek** neben Ihren Experience Cloud Assets auch dann, wenn das Package Integration mit Adobe Experience Cloud auf Ihrer Adobe Campaign-Instanz installiert ist. [Weitere Informationen](../connect/ac-aem.md#assets-library)

### Allgemeine Verbesserungen {#improvements-8-6-1}

* Campaign v8.6 verbessert den Durchsatz für **Trackingindikatoren von E-Mail-Sendungen**. Mit unseren optimierten Prozessen wird die Tracking-Erfassung und Rechenzeit verkürzt, und Sie können Ihre Versandschlüsselindikatoren viel schneller überprüfen.


### Aktualisierungen der Zustellbarkeit {#deliverability-8-6-1}

* Bis Februar 2024 sendet jedes Unternehmen mehr als 5.000 E-Mail-Nachrichten über Google oder Yahoo! muss zunächst eine Authentifizierungstechnologie verwenden, die als Domain-based Message Authentication Reporting and Conformance (DMARC) bezeichnet wird. Stellen Sie sicher, dass für alle Subdomains, die Sie mit Adobe Campaign verwenden, DMARC-Datensätze eingerichtet sind. [Weitere Informationen](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=de){target="_blank"}

* Ab dem 1. Juni 2024, Google und Yahoo! verlangt von den Absendern die Einhaltung von One-Click List-Unsubscribe. Adobe Campaign unterstützt diese Option jetzt. [Weitere Informationen](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#one-click-list-unsubscribe){target="_blank"}


### Fehlerbehebungen {#fixes-8-6-1}

Folgende Probleme wurden in dieser Version behoben: NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984 NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-632 94, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-6 1199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542 O-50488, NEO-47789