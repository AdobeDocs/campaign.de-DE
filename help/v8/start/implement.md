---
title: Leitlinien für die Implementierung
description: Erfahren Sie, wie Sie Campaign v8 implementieren
feature: Overview
role: User
level: Intermediate
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 98%

---

# Leitlinien für die Implementierung von Campaign{#gs-implementation}

In diesem Abschnitt erfahren Sie, wie Sie Adobe Campaign an die Anforderungen Ihrer Firma anpassen. Verwenden Sie die folgenden Richtlinien, um Ihre Implementierung zu strukturieren und zu organisieren.

1. **Einstellungen definieren**: Zugriff gewähren, Client-Konsole freigeben, Kanäle konfigurieren (E-Mail, Push, SMS) [Weitere Informationen](#implementation-ac-settings)
1. **Ihre Umgebung vorbereiten**: Profile importieren, Zielgruppen erstellen, Workflow- und Kampagnenvorlagen entwerfen, Typologieregeln erstellen. [Weitere Informationen](#implementation-prepare-your-env)
1. **Ihre Instanz anpassen**: neue Datenfelder erstellen, Tabellen/Schemata hinzufügen. [Weitere Informationen](#implementation-custom-your-instance)
1. **Prozesse automatisieren**: Automatisierungsfunktionen von Adobe Campaign konfigurieren. [Weitere Informationen](#implementation-automation)
1. **Ihre Bereitstellung erweitern**: mit Adobe-Lösungen, anderen Produkten und Systemen verbinden – Connectoren, Einstellungen für mehrere Lösungen. [Weitere Informationen](#implementation-extend)

>[!CAUTION]
>
>Mit **Campaign Managed Cloud Services** wird Ihre Umgebung und die anfängliche Konfiguration von Adobe gemäß den Bedingungen Ihrer Lizenzvereinbarung festgelegt. Sie dürfen keine installierten integrierten Packages, integrierten Schemata oder Berichte ändern.
>
>Wenn Sie ein Campaign-Add-on oder eine spezifische Funktion verwenden müssen, das bzw. die Ihnen nicht zur Verfügung gestellt wurde, wenden Sie sich an Ihren **Adobe Transition Manager**.

## Vor Beginn{#before-starting}

Dieser Abschnitt enthält wichtige Informationen zum Datenschutz und zur Sicherheit, die bereits vor der eigentlichen Implementierung geprüft und berücksichtigt werden müssen.

### Datenschutz{#implementation-privacy}

Adobe Campaign verfügt über Prozesse und Einstellungen, die es Ihnen ermöglichen, Campaign in Übereinstimmung mit den geltenden Datenschutzgesetzen und den Präferenzen Ihrer Empfänger zu verwenden. Sie können Folgendes verwalten:

* **Datenakquise**: Mit Adobe Campaign können Sie Daten, einschließlich persönlicher und vertraulicher Daten, erfassen. Es ist daher unerlässlich, dass Sie das Einverständnis Ihrer Empfängerinnen und Empfängern erhalten und managen.

  Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=de#data-acquisition){target="_blank"}

* **Benutzerzustimmung und Datenspeicherung**: Sie müssen die Einwilligungen der jeweiligen Benutzenden einholen, Anmeldemechanismen mit Double-Opt-in einrichten, den Opt-out erleichtern und die Datenspeicherung konfigurieren.

  Weitere Informationen finden Sie in der [Dokumentation zum Datenschutz in Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=de#consent){target="_blank"}

* **Datenschutzbestimmungen**: In [diesem Abschnitt](privacy.md) finden Sie Informationen über Datenschutzanforderungen und darüber, wie sich diese Bestimmungen auf Ihre Organisation und Adobe Campaign auswirken.

### Sicherheit

Informationen zu Sicherheitsrichtlinien und -prinzipien für Adobe Campaign finden Sie in der [Sicherheits-Checkliste von Campaign](../config/security.md).

## Einstellungen für Campaign definieren{#implementation-ac-settings}

### Benutzer hinzufügen und Berechtigungen erteilen{#implementation-add-users}

Sie können Benutzer entsprechend Ihrer Rollenhierarchie manuell zu Campaign hinzufügen und sie Gruppen zuordnen. Die Benutzer können sich dann anmelden und auf die für sie geeigneten Daten und Berechtigungen zugreifen.

In [diesem Abschnitt](../start/gs-permissions.md) erfahren Sie, wie Sie Benutzende zu Adobe Campaign hinzufügen.

### Installieren der Campaign-Client-Konsole{#implementation-install-console}

Die Hauptbenutzeroberfläche des Programms ist ein Rich-Client, d. h. ein natives Programm (Windows), das ausschließlich mit Standard-Internet-Protokollen (SOAP, HTTP usw.) mit dem Adobe Campaign-Anwendungs-Server kommuniziert. Die Adobe Campaign-Client-Konsole bietet eine hohe Benutzerfreundlichkeit für hohe Produktivität, verbraucht sehr wenig Bandbreite (durch die Verwendung eines lokalen Cache) und wurde für eine einfache Bereitstellung entwickelt. Diese Konsole kann über einen Internet-Browser bereitgestellt werden, kann automatisch aktualisiert werden und erfordert keine spezielle Netzwerkkonfiguration, da sie nur HTTP(S)-Traffic erzeugt.

[Erfahren Sie mehr über die Campaign-Client-Konsole](connect.md).

## Ihre Umgebung vorbereiten{#implementation-prepare-your-env}

Bevor Sie Nachrichten senden und Marketing-Kampagnen erstellen, müssen Sie Folgendes tun:

1. **Importieren von Profilen und Erstellen von Zielgruppen**

   Mit Campaign können Sie der Cloud-Datenbank Kontakte hinzufügen. Sie können eine Datei laden, mehrere Kontaktaktualisierungen planen und automatisieren, Daten im Internet sammeln oder Profilinformationen direkt in die Empfängertabelle eingeben.

   [Erfahren Sie, wie Sie Profile importieren](import.md).

   Zielgruppen werden in Listen gruppiert und können über Workflows erstellt werden. Sie können dann in kanalübergreifenden Sendungen gezielt angesprochen werden.

   [Erfahren Sie, wie Sie Zielgruppen definieren](audiences.md).

1. **Verwenden von Vorlagen**

   Kampagnen, Sendungen, Vorgänge oder Workflows basieren auf einer Vorlage, in der wichtige Einstellungen und Funktionen gespeichert sind. Für jede Komponente, für die keine spezifische Konfiguration definiert wurde, wird eine integrierte Vorlage bereitgestellt. Sie müssen die Vorlagen konfigurieren, an Ihre Anforderungen anpassen und für Endbenutzer verfügbar machen.


   Auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-templates.html?lang=de){target="_blank"} erfahren Sie, wie Sie mit Kampagnenvorlagen arbeiten.

   Auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=de){target="_blank"} erfahren Sie, wie Sie eine Workflow-Vorlage konfigurieren.

   Weitere Informationen zu E-Mail-Vorlagen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=de){target="_blank"}.


1. **Konfigurieren von Typologieregeln**

   Nutzen Sie die Campaign-Typologieregeln, um den Versand zu filtern, zu steuern und zu überwachen. Zum Beispiel steuern Ermüdungsregeln die Häufigkeit und Menge der Nachrichten, um eine Übersättigung der Empfänger zu vermeiden. Einmal implementiert, werden Typologieregeln in den Sendungen referenziert.

   Weitere Informationen zu Typologien und zur Ermüdungsverwaltung finden Sie in [diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=de){target="_blank"}.

1. **Einführung in das integrierte Datenmodell in Campaign**

   Adobe Campaign enthält ein vordefiniertes Datenmodell. Um Ihre Umgebung zu implementieren und anzupassen, müssen Sie mit den integrierten Tabellen des Adobe Campaign-Datenmodells vertraut sein und wissen, wie sie sich zueinander verhalten.

   [Erfahren Sie mehr über das Campaign-Datenmodell](../dev/datamodel.md).

## Anpassen der Instanz{#implementation-custom-your-instance}

Sie können viele verschiedene Bereiche und Funktionen in Campaign anpassen. Die meisten unserer Kunden passen drei Dinge an:

1. **Tabellen und Schemata**

   Adobe Campaign verfügt über gemeinsame Schemata zur Identifizierung von Daten wie: Empfänger, Versandprotokolle, Abonnements und mehr.

   In diesem Abschnitt erfahren Sie mehr über das integrierte Datenmodell von [Campaign](../dev/datamodel.md).

   Sie können bestehende Schemata erweitern oder Schemata von Grund auf neu erstellen. Weiterführende Informationen finden Sie auf [dieser Seite](../dev/customize.md).

1. **Dashboards und Listen**

   Sie können auf einfache Weise Listen konfigurieren, Felder hinzufügen und entfernen und Spalten anpassen.

   Auf [dieser Seite](../dev/customize.md#gs-lists-and-filters) erfahren Sie, wie Sie in Campaign Filter und Listen verwalten.

   Sie können auch neue Dashboards erstellen, um Campaign-Daten je nach Bedarf anzuzeigen.

   Weitere Informationen finden Sie auf [dieser Seite](../dev/customize.md#gs-custom-dashboards).

1. **Berichte**

   Campaign bietet eine Reihe von integrierten Berichten zur Überwachung des Versands, zu URLs und Clickstreams, zur Nachverfolgung, zu Zustellbarkeitsindikatoren und mehr.

   Abgesehen von den integrierten Berichten können Sie in Adobe Campaign auch benutzerdefinierte Berichte entsprechend dem jeweiligen Kontext und Ihren Anforderungen erstellen. In diesem Dokument werden die Grundsätze der Nutzung und die Implementierungsmodi erläutert.

   Auf [dieser Seite](../reporting/gs-reporting.md) erfahren Sie mehr über die Reporting-Funktionen in Campaign.


## Einrichten der Automatisierung in Campaign{#implementation-automation}

Nutzen Sie die Funktionen zur Kampagnenautomatisierung, um komplexe Marketing-Kampagnen an verschiedene Zielgruppen über mehrere Kanäle zu orchestrieren.

* Verwenden Sie **Workflows** zur Verwaltung von Prozessen und Daten. Weitere Informationen finden Sie in [dieser Dokumentation](../../automation/workflow/about-workflows.md).

* Richten Sie **Abonnement**-Prozesse und **Landingpages** ein.  Weitere Informationen auf [dieser Seite](../start/subscriptions.md)

* Konfigurieren Sie **Typologieregeln** zur Definition von Ermüdungs- und Kontrollverwaltung.  Weitere Informationen finden Sie in [dieser Dokumentation](../../automation/campaign-opt/campaign-typologies.md).


## Ihre Bereitstellung erweitern{#implementation-extend}

### Implementierung mehrerer Lösungen{#implementation-multi-solutions}

Wenn Sie andere Adobe-Lösungen einsetzen, können Sie diese mit Ihrer Campaign-Umgebung verbinden und Funktionen kombinieren.

* Campaign – Journey Orchestration
* Campaign – Real-Time CDP
* Campaign – Experience Cloud Triggers
* Campaign – Experience Manager
* Campaign – Target
* Campaign – Audience Manager/People Core Service
* Campaign – Assets
* Campaign – Analytics Data Connectors


Sie können nur Single Sign-on (SSO) verwenden, um eine Verbindung zu Campaign herzustellen. Weitere Informationen finden Sie auf [dieser Seite](connect.md).

Auf [dieser Seite](../connect/integration.md) finden Sie die vollständige Liste der Adobe-Lösungen, die mit Adobe Campaign integriert werden können.

### Connectoren{#implementation-connectors}

Verbinden Sie Campaign mit Systemen von Drittanbietern, um eine große Bandbreite an Funktionen zu kombinieren und Prozesse zu automatisieren.

Weitere Informationen zu verfügbaren Connectoren finden Sie in [diesem Abschnitt](../connect/integration.md).

**Ihr CRM mit Campaign verbinden**

Sie können Ihre Adobe Campaign-Plattform mit Ihren CRM-Systemen von Drittanbietern verbinden und Daten synchronisieren: Kontakte, Konten, Käufe usw.

In [diesem Abschnitt](../connect/integration.md#gs-crm-connectors) erfahren Sie, wie Sie Ihr CRM-System mit Campaign verbinden.

**Verbindung zu einer externen Datenbank herstellen**

Sie können die Campaign Cloud-Datenbank über das Federated Data Access-Modul (FDA) mit externen Systemen verbinden.

In [diesem Abschnitt](../connect/integration.md#gs-fda) erfahren Sie, wie Sie das FDA-Modul von Campaign konfigurieren, um Zugriffsparameter zu definieren.
