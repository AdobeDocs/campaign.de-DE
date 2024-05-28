---
title: Versionshinweise 2023 zu Campaign v8 (Konsole)
description: Liste der Funktionen und Verbesserungen in Campaign v8-Versionen 2023
feature: Release Notes
source-git-commit: 4fecae16b2db0f174de6d77acf5b846906073aeb
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 81%

---

# Versionshinweise 2024 {#2024-rn}

Auf dieser Seite werden neue Funktionen, Verbesserungen und Fehlerbehebungen der **Campaign v8-Versionen von 2024** aufgelistet.


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

Die folgenden Probleme wurden in dieser Version behoben:

NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64 80, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-6 3174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199 O-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-5048 8, NEO-47789