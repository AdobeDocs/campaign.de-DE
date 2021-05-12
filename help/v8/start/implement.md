---
solution: Campaign
product: Adobe Campaign
title: Leitlinien für die Umsetzung
description: Erfahren Sie, wie Sie Kampagne v8 implementieren
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: 51efce79e4195c9d53db167be80c7adcda811e21
workflow-type: tm+mt
source-wordcount: '1220'
ht-degree: 3%

---

# Leitlinien zur Umsetzung der Kampagne

In diesem Abschnitt erfahren Sie, wie Sie das Adobe Campaign an die Anforderungen Ihrer Firma anpassen. Verwenden Sie die folgenden Richtlinien, um Ihre Implementierung zu strukturieren und zu organisieren.

1. **Einstellungen** definieren: Zugriff gewähren, Client-Konsole freigeben, Kanal konfigurieren (E-Mail, Push, sms)
1. **Bereiten Sie Ihre Umgebung** vor: Profile importieren, Audiencen erstellen, Arbeitsablauf und Kampagnenvorlagen entwerfen, Typologieregeln erstellen
1. **Instanz** anpassen: neue Datenfelder erstellen, Tabellen/Schemas hinzufügen
1. **Erweitern der Bereitstellung**: Verbindungen zu Adoben, anderen Produkten und Systemen - Steckern, Einstellungen für mehrere Lösungen

>[!CAUTION]
>
>Mit **Kampagne Managed Cloud Services** wurden Ihre Umgebung und Ihre Erstkonfiguration gemäß den Bedingungen Ihrer Lizenzvereinbarung durch die Adobe festgelegt. Es ist nicht zulässig, installierte integrierte Pakete, integrierte Schema oder Berichte zu ändern.
>
>Wenn Sie ein Kampagne-Add-on oder eine spezielle Funktion verwenden müssen, die nicht für Sie bereitgestellt wurde, müssen Sie sich an den **Adobe-Kundendienst** wenden.

## Vor Beginn

Dieser Abschnitt enthält wichtige Informationen zum Datenschutz und zur Sicherheit, die vor der eigentlichen Implementierung überprüft und berücksichtigt werden müssen.

### Datenschutz

Adobe Campaign verfügt über Prozesse und Einstellungen, mit denen Sie Kampagnen gemäß den geltenden Datenschutzgesetzen und den Voreinstellungen Ihres Empfängers verwenden können. Sie können Folgendes verwalten:

* **Datenerfassung**: Mit Adobe Campaign können Sie Daten, einschließlich persönlicher und sensibler Daten, erfassen. Daher ist es wichtig, dass Sie die Zustimmung Ihrer Empfänger erhalten und verwalten. Weitere Informationen finden Sie in der [Campaign Classic-Dokumentation](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition)

* **Benutzereinwilligung und Datenspeicherung**: Erfahren Sie, wie Sie die Benutzereinwilligung einholen, Mechanismen für die Teilnahme an Dubletten einrichten, die Abmeldung erleichtern und die Datenspeicherung in der Dokumentation zum Datenschutz in  [Campaign Classic konfigurieren können.](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent)

* **Datenschutzbestimmungen**: Informationen zur Datenschutzverordnung der Europäischen Vereinigung (GDPR), zum kalifornischen Verbraucherschutzgesetz (CCPA) und anderen internationalen Datenschutzvorschriften sowie zu den Auswirkungen dieser Vorschriften auf Ihr Unternehmen und Ihr Adobe Campaign finden Sie in der  [Campaign Classic-](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html) Dokumentation.

### Sicherheit

Erfahren Sie mehr über Sicherheitsrichtlinien und -prinzipien mit Adobe Campaign in der [Kampagne Security Checkliste](../config/security.md).

## Kampagnen definieren

### hinzufügen von Benutzern und Berechtigungen

Sie können Benutzer manuell zu Kampagne hinzufügen und sie Gruppen zuordnen, die an Ihrer Rollenhierarchie ausgerichtet sind. Die Benutzer können sich dann anmelden und auf die für sie geeigneten Daten und Berechtigungen zugreifen.

:arrow_upper_right: In [diesem Abschnitt ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=en#getting-started) erfahren Sie, wie Sie Adobe Campaign Benutzer hinzufügen.

### Kampagne Client Console installieren

Die Hauptbenutzeroberfläche der Applikation ist ein Rich-Client, d. h. eine native Applikation (Windows), die ausschließlich mit Standard-Internetprotokollen (SOAP, HTTP usw.) mit dem Adobe Campaign-Anwendungsserver kommuniziert. Die Adobe Campaign Client Console bietet hohe Benutzerfreundlichkeit für Produktivität, nutzt sehr wenig Bandbreite (über einen lokalen Cache) und ist für eine einfache Bereitstellung ausgelegt. Diese Konsole kann über einen Internetbrowser bereitgestellt werden, kann automatisch aktualisiert werden und erfordert keine spezielle Netzwerkkonfiguration, da nur HTTP(S)-Traffic generiert wird.

:bulb: [Erfahren Sie mehr über Kampagne Client Console](connect.md).

## Vorbereitung Ihrer Umgebung

Bevor Sie Nachrichten senden und Marketing-Kampagnen erstellen, müssen Sie:

1. Profile importieren und Audiencen erstellen

   Mit Kampagne können Sie der Cloud-Datenbank Kontakte hinzufügen. Sie können eine Datei laden, mehrere Kontaktaktualisierungen planen und automatisieren, Daten im Web erfassen oder Profil-Informationen direkt in die Empfänger-Tabelle eingeben.

   :bulb: [Erfahren Sie, wie Sie Profil](import.md) importieren.

   Audiencen werden in Listen gruppiert und können über Worflows erstellt werden. Sie können dann in Versänden mit mehreren Kanälen gezielt eingesetzt werden.

   :bulb: [Erfahren Sie, wie Sie Audiencen](audiences.md) definieren.

1. Vorlagen erstellen

   Kampagnen, Versand, Aufträge oder Workflows basieren auf einer Vorlage, die wichtige Einstellungen und Funktionen speichert. Für jede Komponente wird eine integrierte Vorlage bereitgestellt, für die keine spezifische Konfiguration definiert wurde. Sie müssen Vorlagen konfigurieren und an Ihre Anforderungen anpassen und für Endbenutzer verfügbar machen.

   :arrow_upper_right: [Weitere Informationen zu E-Mail-Vorlagen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)

   :arrow_upper_right: Erfahren Sie, wie Sie mit Kampagnenvorlagen auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns) arbeiten.

   :arrow_upper_right: Erfahren Sie, wie Sie eine Workflow-Vorlage auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=en#workflow-templates) konfigurieren

1. Typologieregeln konfigurieren

   Nutzen Sie Kampagnentypologien-Regeln, um das Senden von Versänden zu filtern, zu steuern und zu überwachen. So steuern Ermüdungsregeln zum Beispiel die Häufigkeit und Quantität von Nachrichten, um zu vermeiden, dass Empfänger übermäßig aufgesucht werden. Nach der Implementierung werden Typologieregeln in Versänden referenziert.

   :arrow_upper_right: [Erfahren Sie mehr über Typologien und Ermüdungsmanagement](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=en#orchestrating-campaigns)

1. Machen Sie sich mit dem integrierten Datenmodell der Kampagne vertraut

   Adobe Campaign enthält ein vordefiniertes Datenmodell. Um Ihre Umgebung zu implementieren und anzupassen, müssen Sie mit den integrierten Tabellen des Adobe Campaign-Datenmodells und deren Beziehung zueinander vertraut sein.

   :bulb: [Erfahren Sie mehr über die Kampagne datamodel](../dev/datamodel.md).

## Instanz anpassen

Sie können viele verschiedene Bereiche und Funktionen der Kampagne anpassen. Die meisten unserer Kunden passen drei Dinge an:

1. **Tabellen und Schemas**

   Adobe Campaign verfügt über häufige Schemas zur Identifizierung von Daten wie: Empfänger, Versandlogs, Abonnements und mehr.

   :bulb: In diesem Abschnitt erfahren Sie mehr über [integrierte Datamodel-Kampagne](../dev/datamodel.md).

   :bulb: Sie können bestehende Schema erweitern oder neue Schema von Grund auf neu erstellen. Weiterführende Informationen finden Sie auf [dieser Seite](../dev/customize.md).

1. **Dashboards und Listen**

   Sie können auf einfache Weise Listen konfigurieren, Felder hinzufügen und entfernen und Spalten anpassen.

   :bulb: Erfahren Sie, wie Sie Filter und Listen in der Kampagne auf [dieser Seite](../dev/customize.md#gs-lists-and-filters) verwalten.

   Sie können auch neue Dashboard erstellen, um die Kampagnen je nach Bedarf anzuzeigen.

   :bulb: Weitere Informationen finden Sie auf [dieser Seite](../dev/customize.md#gs-custom-dashboards).

1. **Berichte**

   Kampagne bietet eine Reihe integrierter Berichte zu Versand-Überwachung, URLs und Klickstreams, Verfolgung, Bereitstellbarkeitsindikatoren und mehr.

   Abgesehen von den integrierten Berichten können Sie in Adobe Campaign auch benutzerdefinierte Berichte entsprechend dem jeweiligen Kontext und Ihren Anforderungen erstellen. In diesem Dokument werden die Grundsätze der Nutzung und der Durchführungsmodalitäten erläutert.

   :bulb: Erfahren Sie mehr über die Funktionen von Berichten in der Kampagne auf [dieser Seite](reporting.md).


## Einrichten der Automatisierung der Kampagne

Um komplexe Marketing-Kampagnen über mehrere Kanal hinweg zu unterschiedlichen Audiencen zu orchestrieren, nutzen Sie die Automatisierungsfunktionen der Kampagne.

* Workflows: Prozesse und Daten verwalten

* Abonnements und Landingpages

* Typologieregeln: Ermüdung und Steuerung

## Bereitstellung erweitern

### Implementierung mehrerer Lösungen

Wenn Sie andere Adoben verwenden, können Sie diese mit Ihrer Kampagne-Umgebung verbinden und Funktionen kombinieren.

* Kampagne - Journey Orchestration
* Kampagne - CDP in Echtzeit
* Kampagne - Experience Cloud Trigger
* Kampagne - Experience Manager
* Kampagne - Zielgruppe
* Kampagne - Hauptdienst Audience Manager/Personen
* Kampagne - Asset
* Kampagne - Analytics Data Connectors


Sie können auch Single-Sign-On (SSO) verwenden, um eine Verbindung zur Kampagne herzustellen. Weiterführende Informationen finden Sie auf [dieser Seite](connect.md).

:bulb: Entdecken Sie die vollständige Liste der Adobe-Lösung, die in Adobe Campaign [auf dieser Seite ](../connect/integration.md) integriert werden kann.

### Connectoren

Verbinden Sie Kampagnen mit Drittanbietersystemen, um eine große Bandbreite an Funktionen zu kombinieren und Prozesse zu automatisieren.

:bulb: Weitere Informationen zu verfügbaren Connectors finden Sie in [diesem Abschnitt](../connect/integration.md).

**CRM mit Kampagne verbinden**

Sie können Ihre Adobe Campaign-Plattform mit Ihren CRM-Drittanbietersystemen verbinden und Daten synchronisieren: Kontakte, Konten, Käufe usw.

:bulb: In [diesem Abschnitt ](../connect/integration.md#gs-crm-connectors) erfahren Sie, wie Sie Ihr CRM-System mit der Kampagne verbinden.

**Herstellen einer Verbindung zu einer externen Datenbank**

Sie können die Kampagne Cloud-Datenbank über das Modul Federated Data Access (FDA) mit externen Systemen verbinden.

:bulb: Erfahren Sie, wie Sie das Modul &quot;Kampagne FDA&quot;konfigurieren, um Zugriffsparameter in [diesem Abschnitt zu definieren](../connect/integration.md#gs-fda)
