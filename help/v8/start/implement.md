---
solution: Campaign v8
product: Adobe Campaign
title: Implementierungsrichtlinien
description: Erfahren Sie, wie Sie Campaign v8 implementieren
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: 167730cc3e81ee47f02bcdbc2c39fe793a99c534
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 4%

---

# Implementierungsrichtlinien für Campaign

In diesem Abschnitt erfahren Sie, wie Sie Adobe Campaign an die Anforderungen Ihres Unternehmens anpassen können. Verwenden Sie die folgenden Richtlinien, um Ihre Implementierung zu strukturieren und zu organisieren.

1. **Definieren Sie Einstellungen**: Zugriff gewähren, Client Console freigeben, Kanäle konfigurieren (E-Mail, Push, SMS)
1. **Bereiten Sie Ihre Umgebung** vor: Profile importieren, Audiences erstellen, Workflow und Kampagnenvorlagen entwerfen, Typologieregeln erstellen
1. **Instanz anpassen**: neue Datenfelder erstellen, Tabellen/Schemata hinzufügen
1. **Erweitern Sie Ihre Bereitstellung**: Verbindung zu Adobe-Lösungen, anderen Produkten und Systemen - Connectoren, Einstellungen für mehrere Lösungen

>[!CAUTION]
>
>Mit **Campaign Managed Cloud Services** wurden Ihre Umgebung und die Erstkonfiguration gemäß Ihren Lizenzbestimmungen von Adobe festgelegt. Sie dürfen keine installierten integrierten Packages, integrierten Schemata oder Berichte ändern.
>
>Wenn Sie ein Campaign-Add-on oder eine spezifische Funktion verwenden müssen, die Ihnen nicht zur Verfügung gestellt wurde, wenden Sie sich an die **Adobe-Kundenunterstützung**.

## Vor Beginn

Dieser Abschnitt enthält wichtige Informationen zum Datenschutz und zur Sicherheit, die überprüft und berücksichtigt werden müssen, bevor die eigentliche Implementierung gestartet wird.

### Datenschutz

Adobe Campaign verfügt über Prozesse und Einstellungen, mit denen Sie Campaign unter Einhaltung der geltenden Datenschutzgesetze und der Voreinstellungen Ihres Empfängers verwenden können. Sie können Folgendes verwalten:

* **Datenerfassung**: Mit Adobe Campaign können Sie Daten, einschließlich persönlicher und sensibler Daten, erfassen. Daher ist es wichtig, dass Sie die Zustimmung Ihrer Empfänger erhalten und verwalten. Weitere Informationen finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition)

* **Benutzerzustimmung und Datenspeicherung**: Erfahren Sie, wie Sie die Benutzerzustimmung einholen, Anmeldemechanismen für die Anmeldung mit zweifacher Bestätigung einrichten, Opt-out erleichtern und die Datenbeibehaltung in der Datenschutzdokumentation von  [Campaign Classic konfigurieren.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent)

* **Datenschutzbestimmungen**: Weitere Informationen zur Datenschutz-Grundverordnung (DSGVO) der Europäischen Union, zum California Consumer Privacy Act (CCPA) und anderen internationalen Datenschutzanforderungen sowie dazu, wie sich diese Vorschriften auf Ihr Unternehmen und Adobe Campaign auswirken, finden Sie in der  [Campaign Classic-](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html) Dokumentation.

### Sicherheit

Erfahren Sie mehr über Sicherheitsrichtlinien und -prinzipien mit Adobe Campaign in [Checkliste für die Kampagnensicherheit](../config/security.md).

## Campaign-Einstellungen definieren

### Hinzufügen von Benutzern und Gewähren von Berechtigungen

Sie können Benutzer manuell zu Campaign hinzufügen und sie Gruppen zuordnen, die an Ihrer Rollenhierarchie ausgerichtet sind. Benutzer können sich dann anmelden und auf die für sie geeigneten Daten und Berechtigungen zugreifen.

:[!DNL :arrow_upper_right:]: In [diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=en#getting-started) erfahren Sie, wie Sie Benutzer zu Adobe Campaign hinzufügen.

### Installieren der Campaign Client Console

Die Hauptbenutzeroberfläche des Programms ist ein Rich-Client, d. h. eine native Anwendung (Windows), die ausschließlich mit Standardinternetprotokollen (SOAP, HTTP usw.) mit dem Adobe Campaign-Anwendungsserver kommuniziert. Die Adobe Campaign Client Console bietet eine hervorragende Benutzerfreundlichkeit für die Produktivität, verwendet sehr wenig Bandbreite (durch Verwendung eines lokalen Caches) und ist für eine einfache Implementierung ausgelegt. Diese Konsole kann über einen Internetbrowser bereitgestellt werden, kann automatisch aktualisiert werden und erfordert keine spezifische Netzwerkkonfiguration, da sie nur HTTP(S)-Traffic generiert.

[!DNL :bulb:] [Erfahren Sie mehr über die Campaign Client Console](connect.md).

## Vorbereiten der Umgebung

Bevor Sie Nachrichten senden und Marketingkampagnen erstellen, müssen Sie Folgendes tun:

1. Profile importieren und Audiences erstellen

   Campaign unterstützt Sie beim Hinzufügen von Kontakten zur Cloud-Datenbank. Sie können eine Datei laden, mehrere Kontaktaktualisierungen planen und automatisieren, Daten im Web erfassen oder Profilinformationen direkt in die Empfängertabelle eingeben.

   [!DNL :bulb:] [Erfahren Sie, wie Sie Profile](import.md) importieren.

   Zielgruppen werden in Listen gruppiert und können über Workflows erstellt werden. Diese können dann in kanalübergreifenden Sendungen verwendet werden.

   [!DNL :bulb:] [Erfahren Sie, wie Sie Zielgruppen definieren](audiences.md).

1. Vorlagen erstellen

   Kampagnen, Sendungen, Aufträge oder Workflows basieren alle auf einer Vorlage, die wichtige Einstellungen und Funktionen speichert. Für jede Komponente, für die keine spezifische Konfiguration definiert wurde, wird eine integrierte Vorlage bereitgestellt. Sie müssen Vorlagen konfigurieren und an Ihre Anforderungen anpassen und sie Endbenutzern zur Verfügung stellen.

   [!DNL :arrow_upper_right:] [Weitere Informationen zu E-Mail-Vorlagen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)

   [!DNL :arrow_upper_right:] Auf  [dieser Seite erfahren Sie, wie Sie mit Kampagnenvorlagen arbeiten.](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)

   [!DNL :arrow_upper_right:] Auf  [dieser Seite erfahren Sie, wie Sie eine Workflow-Vorlage konfigurieren.](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=en#workflow-templates)

1. Typologieregeln konfigurieren

   Nutzen Sie die Typologieregeln von Campaign, um den Versand zu filtern, zu kontrollieren und zu überwachen. Beispielsweise steuern Ermüdungsregeln die Häufigkeit und Menge der Nachrichten, um eine Überforderung von Empfängern zu vermeiden. Nach der Implementierung werden die Typologieregeln in Sendungen referenziert.

   [!DNL :arrow_upper_right:] [Erfahren Sie mehr über Typologien und Ermüdungsverwaltung](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=en#orchestrating-campaigns)

1. Eingehendes Datenmodell von Campaign

   Adobe Campaign enthält ein vordefiniertes Datenmodell. Um Ihre Umgebung zu implementieren und anzupassen, müssen Sie mit den integrierten Tabellen des Adobe Campaign-Datenmodells und deren Beziehung zueinander vertraut sein.

   [!DNL :bulb:] [Erfahren Sie mehr über das Datenmodell von Campaign](../dev/datamodel.md).

## Instanz anpassen

Sie können viele verschiedene Campaign-Bereiche und -Funktionen anpassen. Die meisten unserer Kunden passen drei Dinge an:

1. **Tabellen und Schemata**

   Adobe Campaign enthält allgemeine Schemata zur Identifizierung von Daten wie: Empfänger, Versandlogs, Abonnements und mehr.

   [!DNL :bulb:] In diesem Abschnitt erfahren Sie mehr über das integrierte Datenmodell von  [Campaign](../dev/datamodel.md).

   [!DNL :bulb:] Sie können vorhandene Schemata erweitern oder neue Schemas von Grund auf neu erstellen. Weiterführende Informationen finden Sie auf [dieser Seite](../dev/customize.md).

1. **Dashboards und Listen**

   Sie können einfach Listen konfigurieren, Felder hinzufügen und entfernen und Spalten anpassen.

   [!DNL :bulb:] Auf  [dieser Seite](../dev/customize.md#gs-lists-and-filters) erfahren Sie, wie Sie in Campaign Filter und Listen verwalten.

   Sie können auch neue Dashboards erstellen, um Campaign-Daten entsprechend Ihren Anforderungen anzuzeigen.

   [!DNL :bulb:][ Weiterführende Informationen finden Sie auf dieser Seite](../dev/customize.md#gs-custom-dashboards).

1. **Berichte**

   Campaign bietet eine Reihe integrierter Berichte zu Versandüberwachung, URLs und Clickstreams, Tracking, Zustellbarkeitsindikatoren und mehr.

   Abgesehen von den integrierten Berichten können Sie in Adobe Campaign auch benutzerdefinierte Berichte entsprechend dem jeweiligen Kontext und Ihren Anforderungen erstellen. Die Grundsätze der Anwendungs- und Durchführungsmodi werden in diesem Dokument beschrieben.

   [!DNL :bulb:] Weiterführende Informationen zu Berichtsfunktionen in Campaign finden Sie auf  [dieser Seite](reporting.md).


## Einrichten der Kampagnenautomatisierung

Um komplexe Marketing-Kampagnen kanalübergreifend für verschiedene Zielgruppen zu organisieren, nutzen Sie die Automatisierungsfunktionen von Campaign.

* Workflows: Prozesse und Daten verwalten

* Abonnements und Landingpages

* Typologieregeln: Ermüdungs- und Kontrollmanagement

## Implementierung erweitern

### Implementierung mehrerer Lösungen

Wenn Sie andere Adobe-Lösungen verwenden, können Sie diese mit Ihrer Campaign-Umgebung verbinden und Funktionen kombinieren.

* Campaign - Journey Orchestration
* Campaign - Echtzeit-Kundendatenplattform
* Campaign - Experience Cloud Trigger
* Campaign - Experience Manager
* Campaign - Target
* Campaign - Audience Manager/People Core Service
* Campaign - Asset
* Campaign - Analytics Data Connectors


Sie können auch Single Sign-On (SSO) verwenden, um eine Verbindung zu Campaign herzustellen. Weiterführende Informationen finden Sie auf [dieser Seite](connect.md).

[!DNL :bulb:] Eine vollständige Liste der Adobe-Lösungen, die mit Adobe Campaign integriert werden können, finden Sie  [auf dieser Seite](../connect/integration.md).

### Connectoren

Verbinden Sie Campaign mit Drittanbietersystemen, um eine Vielzahl von Funktionen zu kombinieren und Prozesse zu automatisieren.

[!DNL :bulb:] Weitere Informationen zu verfügbaren Connectoren finden Sie in  [diesem Abschnitt](../connect/integration.md).

**CRM mit Campaign verbinden**

Sie können Ihre Adobe Campaign-Plattform mit Ihren CRM-Drittanbietersystemen verbinden und Daten synchronisieren: Kontakte, Konten, Käufe usw.

[!DNL :bulb:] In  [diesem Abschnitt erfahren Sie, wie Sie Ihr CRM-System mit Campaign verbinden.](../connect/integration.md#gs-crm-connectors)

**Herstellen einer Verbindung zu einer externen Datenbank**

Sie können die Campaign Cloud-Datenbank über das Modul Federated Data Access (FDA) mit externen Systemen verbinden.

[!DNL :bulb:] In  [diesem Abschnitt erfahren Sie, wie Sie das FDA-Modul von Campaign konfigurieren, um Zugriffsparameter zu definieren.](../connect/integration.md#gs-fda)
