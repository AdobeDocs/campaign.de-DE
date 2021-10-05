---
title: Leitlinien für die Implementierung
description: Erfahren Sie, wie Sie Campaign v8 implementieren
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: ht
source-wordcount: '1213'
ht-degree: 100%

---

# Leitlinien für die Implementierung von Campaign

In diesem Abschnitt erfahren Sie, wie Sie Adobe Campaign an die Anforderungen Ihres Unternehmens anpassen. Verwenden Sie die folgenden Richtlinien, um Ihre Implementierung zu strukturieren und zu organisieren.

1. **Einstellungen definieren**: Zugriff gewähren, Client-Konsole freigeben, Kanäle konfigurieren (E-Mail, Push, SMS)
1. **Ihre Umgebung vorbereiten**: Profile importieren, Audiences erstellen, Workflow und Kampagnenvorlagen entwerfen, Typologieregeln erstellen
1. **Ihre Instanz anpassen**: neue Datenfelder erstellen, Tabellen/Schemata hinzufügen
1. **Ihre Implementierung erweitern**: mit Adobe-Lösungen, anderen Produkten und Systemen verbinden – Connectoren, Einstellungen für mehrere Lösungen

>[!CAUTION]
>
>Mit **Campaign Managed Cloud Services** wurden Ihre Umgebung und die Erstkonfiguration gemäß Ihren Lizenzbestimmungen von Adobe eingerichtet. Sie dürfen keine installierten integrierten Packages, integrierten Schemata oder Berichte ändern.
>
>Wenn Sie ein Campaign-Add-on oder eine spezifische Funktion verwenden müssen, das/die Ihnen nicht zur Verfügung gestellt wurde, wenden Sie sich an die **Adobe-Kundenunterstützung**.

## Vor Beginn

Dieser Abschnitt enthält wichtige Informationen zum Datenschutz und zur Sicherheit, die bereits vor der eigentlichen Implementierung geprüft und berücksichtigt werden müssen.

### Datenschutz

Adobe Campaign verfügt über Prozesse und Einstellungen, die es Ihnen ermöglichen, Campaign in Übereinstimmung mit den geltenden Datenschutzgesetzen und den Präferenzen Ihrer Empfänger zu verwenden. Sie können Folgendes verwalten:

* **Datenakquise**: Mit Adobe Campaign können Sie Daten, einschließlich persönlicher und vertraulicher Daten, erfassen. Es ist daher unerlässlich, dass Sie das Einverständnis Ihrer Empfänger erhalten und managen. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=de#data-acquisition)

* **Benutzereinwilligung und Datenspeicherung**: Erfahren Sie in der [Dokumentation zum Datenschutz in Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=de#consent), wie Sie das Einverständnis der Benutzer einholen, Double-Opt-in-Mechanismen für Abonnements einrichten, das Opt-out erleichtern und die Datenspeicherung konfigurieren.

* **Datenschutzbestimmungen**: In der [Dokumentation zum Datenschutz in Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=de){target=&quot;_blank&quot;} finden Sie Informationen über die Datenschutz-Grundverordnung (DSGVO) der Europäischen Union, den California Consumer Privacy Act (CCPA) und andere internationale Datenschutzanforderungen sowie zu der Frage, wie sich diese Vorschriften auf Ihre Organisation und Adobe Campaign auswirken.

### Sicherheit

Informationen zu Sicherheitsrichtlinien und -prinzipien für Adobe Campaign finden Sie in der [Sicherheits-Checkliste von Campaign](../config/security.md).

## Einstellungen für Campaign definieren

### Benutzer hinzufügen und Berechtigungen erteilen

Sie können Benutzer manuell zu Campaign hinzufügen und sie mit Gruppen verknüpfen, die an Ihrer Rollenhierarchie ausgerichtet sind. Die Benutzer können sich dann anmelden und auf die für sie passenden Daten und Berechtigungen zugreifen.

↗️ Wie Sie Benutzer zu Adobe Campaign hinzufügen, erfahren Sie [in diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=de#getting-started){target=&quot;_blank&quot;}.

### Campaign-Client-Konsole installieren

Die Hauptbenutzeroberfläche des Programms ist ein Rich-Client, d. h. ein natives Programm (Windows), das ausschließlich mit Standard-Internet-Protokollen (SOAP, HTTP usw.) mit dem Adobe Campaign-Anwendungs-Server kommuniziert. Die Adobe Campaign-Client-Konsole bietet hohe Benutzerfreundlichkeit für hohe Produktivität, verbraucht sehr wenig Bandbreite (durch die Verwendung eines lokalen Cache) und wurde für eine einfache Implementierung entwickelt. Diese Konsole kann über einen Internet-Browser implementiert werden, kann automatisch aktualisiert werden und erfordert keine spezielle Netzwerkkonfiguration, da sie nur HTTP(S)-Traffic erzeugt.

?? [Erfahren Sie mehr über die Campaign-Client-Konsole](connect.md).

## Ihre Umgebung vorbereiten

Bevor Sie Nachrichten senden und Marketing-Kampagnen erstellen, müssen Sie Folgendes tun:

1. Profile importieren und Audiences erstellen

   Mit Campaign können Sie der Cloud-Datenbank Kontakte hinzufügen. Sie können eine Datei laden, mehrere Kontaktaktualisierungen planen und automatisieren, Daten im Internet sammeln oder Profilinformationen direkt in die Empfängertabelle eingeben.

   ?? [Erfahren Sie, wie Sie Profile importieren](import.md).

   Audiences werden in Listen gruppiert und können über Workflows erstellt werden. Sie können dann in kanalübergreifenden Sendungen gezielt angesprochen werden.

   ?? [Erfahren Sie, wie Sie Audiences definieren](audiences.md).

1. Vorlagen erstellen

   Kampagnen, Sendungen, Aufträge oder Workflows basieren auf einer Vorlage, in der wichtige Einstellungen und Funktionen gespeichert sind. Für jede Komponente, für die keine spezifische Konfiguration definiert wurde, wird eine integrierte Vorlage bereitgestellt. Sie müssen die Vorlagen konfigurieren, an Ihre Anforderungen anpassen und für Endbenutzer verfügbar machen.

   ↗️ [Weitere Informationen zu E-Mail-Vorlagen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=de){target=&quot;_blank&quot;}.

   ↗️ Wie Sie mit Kampagnenvorlagen arbeiten, erfahren Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=de#orchestrating-campaigns).{target=&quot;_blank&quot;}

   ↗️ Wie Sie eine Workflow-Vorlage konfigurieren, erfahren Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=de#workflow-templates).{target=&quot;_blank&quot;}

1. Typologieregeln konfigurieren

   Nutzen Sie die Campaign-Typologieregeln zum Filtern, Steuern und Überwachen der Sendungen. Zum Beispiel steuern Ermüdungsregeln die Häufigkeit und Menge der Nachrichten, um eine Übersättigung der Empfänger zu vermeiden. Einmal implementiert, werden Typologieregeln in den Sendungen referenziert.

   ↗️ Weitere Informationen zu Typologien und zur Ermüdungsverwaltung finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=de#orchestrating-campaigns).{target=&quot;_blank&quot;}

1. Einführung in das integrierte Datenmodell in Campaign

   Adobe Campaign enthält ein vordefiniertes Datenmodell. Um Ihre Umgebung zu implementieren und anzupassen, müssen Sie mit den integrierten Tabellen des Adobe Campaign-Datenmodells vertraut sein und wissen, wie sie sich zueinander verhalten.

   ?? [Erfahren Sie mehr über das Campaign-Datenmodell](../dev/datamodel.md).

## Anpassen der Instanz

Sie können viele verschiedene Bereiche und Funktionen in Campaign anpassen. Die meisten unserer Kunden passen drei Dinge an:

1. **Tabellen und Schemata**

   Adobe Campaign verfügt über gemeinsame Schemata zur Identifizierung von Daten wie: Empfänger, Versandprotokolle, Abonnements und mehr.

   ?? In diesem Abschnitt erfahren Sie mehr über das [integrierte Datenmodell von Campaign](../dev/datamodel.md).

   ?? Sie können bestehende Schemata erweitern oder Schemata von Grund auf neu erstellen. Weiterführende Informationen finden Sie auf [dieser Seite](../dev/customize.md).

1. **Dashboards und Listen**

   Sie können auf einfache Weise Listen konfigurieren, Felder hinzufügen und entfernen und Spalten anpassen.

   ?? Erfahren Sie auf [dieser Seite](../dev/customize.md#gs-lists-and-filters), wie Sie in Campaign Filter und Listen verwalten.

   Sie können auch neue Dashboards erstellen, um Campaign-Daten je nach Bedarf anzuzeigen.

   ?? Weiterführende Informationen finden Sie auf [dieser Seite](../dev/customize.md#gs-custom-dashboards).

1. **Berichte**

   Campaign bietet eine Reihe von integrierten Berichten zur Überwachung von Sendungen, zu URLs und Clickstreams, zur Nachverfolgung, zu Zustellbarkeitsindikatoren und mehr.

   Abgesehen von den integrierten Berichten können Sie in Adobe Campaign auch benutzerdefinierte Berichte entsprechend dem jeweiligen Kontext und Ihren Anforderungen erstellen. In diesem Dokument werden die Grundsätze der Nutzung und die Implementierungsmodi erläutert.

   ?? Erfahren Sie auf [dieser Seite](reporting.md) mehr über die Reporting-Funktionen in Campaign.


## Einrichten der Automatisierung in Campaign

Nutzen Sie die Funktionen zur Kampagnenautomatisierung, um komplexe Marketing-Kampagnen an verschiedene Audiences über mehrere Kanäle zu orchestrieren.

* Workflows: Prozesse und Daten verwalten

* Abonnements und Landingpages

* Typologieregeln: Ermüdung und Verwaltung von Steuerelementen

## Ihre Implementierung erweitern

### Implementierung mehrerer Lösungen

Wenn Sie andere Adobe-Lösungen einsetzen, können Sie diese mit Ihrer Campaign-Umgebung verbinden und Funktionen kombinieren.

* Campaign – Journey Orchestration
* Campaign – Real-Time CDP
* Campaign – Experience Cloud Triggers
* Campaign – Experience Manager
* Campaign – Target
* Campaign – Audience Manager/People Core Service
* Campaign – Assets
* Campaign – Analytics Data Connectors


Sie können auch Single-Sign-on (SSO) verwenden, um eine Verbindung zu Campaign herzustellen. Weiterführende Informationen finden Sie auf [dieser Seite](connect.md).

?? Sehen Sie [auf dieser Seite](../connect/integration.md) die vollständige Liste der Adobe-Lösungen, die mit Adobe Campaign integriert werden können.

### Connectoren

Verbinden Sie Campaign mit Systemen von Drittanbietern, um eine große Bandbreite an Funktionen zu kombinieren und Prozesse zu automatisieren.

?? In [diesem Abschnitt](../connect/integration.md) finden Sie weitere Informationen zu verfügbaren Connectoren.

**Ihr CRM mit Campaign verbinden**

Sie können Ihre Adobe Campaign-Plattform mit Ihren CRM-Systemen von Drittanbietern verbinden und Daten synchronisieren: Kontakte, Konten, Käufe usw.

?? In [diesem Abschnitt](../connect/integration.md#gs-crm-connectors) erfahren Sie, wie Sie Ihr CRM-System mit Campaign verbinden.

**Verbindung zu einer externen Datenbank herstellen**

Sie können die Campaign Cloud-Datenbank über das Federated Data Access-Modul (FDA) mit externen Systemen verbinden.

?? In [diesem Abschnitt](../connect/integration.md#gs-fda) erfahren Sie, wie Sie das FDA-Modul von Campaign konfigurieren, um Zugriffsparameter zu definieren.
