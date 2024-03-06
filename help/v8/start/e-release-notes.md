---
title: Frühzeitige Versionshinweise zu Campain v8
description: Frühzeitige Veröffentlichung von Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: eae364fb3d082c91022fee6bf29802c9eb6dfcf5
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 100%

---

# Frühere Versionshinweise {#e-new-release}

Auf dieser Seite werden Verbesserungen und Fehlerbehebungen beschrieben, die in der nächsten Version von Campaign v8 enthalten sein werden. Dieser Inhalt kann ohne vorherige Ankündigung bis zum Veröffentlichungsdatum geändert werden. Die offiziellen Versionshinweise finden Sie auf dieser [Seite](../start/release-notes.md).

## Version 8.6.1 {#release-8-6-1}

_14. Februar 2024_


### Neue Funktionen {#new-8-6-1}

* Ab dieser Version haben Sie Zugriff auf die neue **Campaign Web-Benutzeroberfläche**, die in der zentralen Adobe Experience Cloud-Umgebung verfügbar ist. Experience Cloud ist die integrierte Familie von Anwendungen, Produkten und Diensten von Adobe für das digitale Marketing. Über die intuitive Benutzeroberfläche können Sie schnell auf Ihre Cloud-Anwendungen, Produktfunktionen und Dienste zugreifen. [Auf dieser Seite](campaign-ui.md#ac-web-ui) erfahren Sie, wie Sie eine Verbindung mit Adobe Experience Cloud herstellen und auf die Benutzeroberfläche von Adobe Campaign Web zugreifen.

* Die 32-Bit-Version der Client-Konsole wird jetzt nicht mehr unterstützt. Ab 8.6. ist die Client-Konsole nur noch in 64 Bit verfügbar. Das Upgrade auf die 64-Bit-Version der Client-Konsole ist nahtlos. Weitere Informationen zum Upgrade Ihres Betriebssystems finden Sie in dieser [Technote](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=de).


### Allgemeine Verbesserungen {#improvements-8-6-1}

* Campaign v8.6 verbessert den Durchsatz für **Tracking-Indikatoren des E-Mail-Versands**. Mit unseren optimierten Prozessen wird die Tracking-Erfassung und Rechenzeit verkürzt, und Sie können Ihre Versandschlüsselindikatoren viel schneller überprüfen.

* Sie können nun Ihre Campaign v8-Instanz mit Ihrer externen Azure Synapse-Datenbank verbinden. Diese Verbindung wird über ein neues externes Konto verwaltet.

* Adobe Campaign v8 kann jetzt in **Adobe Experience Manager as a Cloud Service** integriert werden, wobei das Authoring ausschließlich über die Adobe Campaign Web-Benutzeroberfläche verfügbar ist.

* Sie können jetzt Ihre **Adobe Experience Manager Assets-Bibliothek** neben Ihren Experience Cloud-Assets nutzen, auch wenn das Paket **Integration in Adobe Experience Cloud** auf Ihrer Adobe Campaign-Instanz installiert ist.

* Sie können keine Benutzenden mehr über die Client-Konsole erstellen. Sie müssen jetzt die Admin Console verwenden. [Weitere Informationen](../start/gs-permissions.md).

* Mehrere Drittanbieter-Tools wurden aktualisiert, um die Sicherheit zu optimieren.

### Aktualisierungen bei der Zustellbarkeit {#deliverability-8-6-1}

* Bis Februar 2024 muss jedes Unternehmen, das mehr als 5.000 E-Mails über Google oder Yahoo! sendet, eine sogenannte DMARC-Authentifizierungstechnologie (Domain-based Message Authentication Reporting and Conformance) verwenden. Stellen Sie sicher, dass für alle Subdomains, die Sie mit Adobe Campaign verwenden, DMARC-Einträge eingerichtet sind. [Weitere Informationen](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=de){target="_blank"}

* Ab dem 1. Juni 2024, verlangen Google und Yahoo! von Absenderinnen und Absendern die Einhaltung der Vorschrift, eine Ein-Klick-Abmeldung anzubieten. Adobe Campaign unterstützt nun diese Option. [Weitere Informationen](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=de#one-click-list-unsubscribe){target="_blank"}


### Fehlerbehebungen {#fixes-8-6-1}

Folgende Probleme wurden in dieser Version behoben:
NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789