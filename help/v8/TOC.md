---
audience: end-user
user-guide-title: Campaign v8
description: Dokumentation zu Campaign v8
breadcrumb-title: Übersicht über Campaign
title: Dokumente zu Campaign v8
source-git-commit: 366cf800a81ea9ab10fe5e3063f44e5214bda927
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 100%

---


# Dokumentation zu Adobe Campaign v8 {#campaign-v8}

+ [Dokumentation zu Campaign v8](campaign-home.md)
+ Versionen und aktuelle Updates {#releases}
   + [Frühzeitige Versionshinweise](start/e-release-notes.md)
   + [Versionshinweise](start/release-notes.md)
   + Frühere Versionshinweise {#previous-rn}
      + [2022](start/release-notes-2022.md)
      + [2021](start/release-notes-2021.md)
   + [Schutzmechanismen](start/ac-guardrails.md)
   + [Bekannte Probleme](start/known-issues.md)
   + [Kompatibilitätsmatrix](start/compatibility-matrix.md)
+ Erste Schritte {#new}
   + [Erste Schritte mit Adobe Campaign](start/get-started.md)
   + [Wichtigste Funktionen](start/whats-new.md)
   + [Komponenten und Prozesse](start/ac-components.md)
   + [Herstellen einer Verbindung zu Campaign](start/connect.md)
   + Campaign-Benutzeroberfläche {#ac-ui}
      + [Erkunden der Benutzeroberfläche von Campaign](start/campaign-ui.md)
      + [Anpassen der Benutzeroberfläche von Campaign](start/customize-ui.md)
      + [Verwalten von Ordnern und Ansichten](audiences/folders-and-views.md)
   + [Wechsel von Classic v7 zu v8](start/v7-to-v8.md)
   + [Häufig gestellte Fragen](start/campaign-faq.md)
+ Kampagnen-Management {#campaigns}
   + [Erste Schritte mit Kampagnen](start/campaigns.md)
   + [Kampagnenorchestrierung >](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=de)
   + Senden von Nachrichten {#send}
      + [Erste Schritte mit Nachrichten](start/create-message.md)
      + [Arbeiten mit Versandvorlagen](send/create-templates.md)
      + E-Mails {#emails}
         + [Entwerfen und Validieren von E-Mails](send/email.md)
         + [Versenden und Überwachen von E-Mails](send/send.md)
      + [SMS](send/sms.md)
      + [Push-Benachrichtigungen ](send/push.md)
      + [LINE-Messaging](send/line.md)
      + [Briefpost](send/direct-mail.md)
      + [Twitter](send/twitter.md)
      + [Transaktionsnachrichten](send/transactional.md)
      + Fehler, Bounces und Quarantänen{#failures}
         + [Quarantänen](send/quarantines.md)
         + [Versandfehler](send/delivery-failures.md)
      + [Optimieren der Versandzeit](send/predictive.md)
      + [Verwalten von Abonnements](start/subscriptions.md)
+ Profil- und Zielgruppen-Management {#audience}
   + [Erste Schritte mit Profilen und Audiences](audiences/gs-audiences.md)
   + [Verwenden von Audiences](start/audiences.md)
   + [Zugriff auf Profile](audiences/view-profiles.md)
   + Hinzufügen von Profilen {#add-profiles}
      + [Manuelles Erstellen von Profilen](audiences/create-profiles.md)
      + [Importieren von Profilen aus einer Datei](audiences/import-profiles.md)
      + [Arbeiten mit externen Profilen](audiences/external-profiles.md)
      + [Erfassen von Profildaten in Web-Formularen](audiences/collect-profiles.md)
      + [Arbeiten mit Zielgruppen-Mappings](audiences/target-mappings.md)
   + Erstellen von Audiences {#create-audiences}
      + [Erstellen einer Liste von Kontakten](audiences/create-audiences.md)
      + [Erstellen und Verwalten von Filtern](audiences/create-filters.md)
   + [Audiences mit Adobe-Lösungen freigeben](start/shared-audiences.md)
   + [Best Practices](audiences/audiences-best-practices.md)
+ Content-Management {#content}
   + [Entwerfen von Web-Anwendungen und Formularen](dev/webapps.md)
+ Datenschutz- und Sicherheits-Management {#privacy}
   + [Verwalten von Datenschutzanfragen](start/privacy.md)
   + [Sicherheitsrichtlinien](config/security.md)
+ Entscheidungs-Management {#offers}
   + [Erste Schritte mit Echtzeit-Interaktionen](interaction/interaction.md)
   + [Umgebungen und Architektur](interaction/interaction-architecture.md)
   + [Best Practices](interaction/interaction-best-practices.md)
   + Definieren von Einstellungen {#interaction-settings}
      + [Erstellen von Benutzern](interaction/interaction-operators.md)
      + [Erstellen von Umgebungen](interaction/interaction-env.md)
      + [Erstellen vordefinierter Filter](interaction/interaction-predefined-filters.md)
      + [Erstellen von Platzierungen](interaction/interaction-offer-spaces.md)
   + [Erstellen eines Angebotskatalogs](interaction/interaction-offer-catalog.md)
   + [Erstellen eines Angebots](interaction/interaction-offer.md)
   + [Senden eines Angebots    (ausgehend)](interaction/interaction-send-offers.md)
   + Unterbreiten eines Angebots (eingehend){#inbound}
      + [Kontext](interaction/interaction-present-offers.md)
      + [Aufrufen eines Angebots auf einer Webseite](interaction/interaction-integration.md)
      + [Verwalten anonymer Interaktionen](interaction/anonymous-interactions.md)
   + [Berichte und Verlauf](interaction/interaction-tracking.md)
   + [Anwendungsfälle](interaction/interaction-use-cases.md)
+ Reporting und Analysen {#analytics}
   + [Verfolgen und Überwachen](start/tracking.md)
   + Arbeiten mit Berichten{#reports}
      + [Erste Schritte mit Berichten](reporting/gs-reporting.md)
      + Erstellen von Cubes{#cubes}
         + [Erste Schritte mit Cubes](reporting/gs-cubes.md)
         + [Erstellen von Cubes](reporting/cube-indicators.md)
         + [Erstellen von Berichten mit Cubes](reporting/cube-tables.md)
         + [Anpassen von Cubes](reporting/customize-cubes.md)
      + Integrierte Berichte{#ac-reports}
         + [Liste integrierter Berichte](reporting/built-in-reports.md)
         + [Allgemeine Berichte](reporting/global-reports.md)
         + [Versandberichte](reporting/delivery-reports.md)
         + [Berechnung integrierter Metriken](reporting/metrics-calculation.md)
      + [Benutzerdefinierte Berichte](reporting/custom-reports.md)
+ Daten-Management {#data}
   + [Erste Schritte mit Workflows](config/workflows.md)
   + [Datenimport](start/import.md)
   + [Workflow-Dokumentation](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=de)
+ Integrationen {#connect}
   + [Campaign mit anderen Lösungen verbinden](connect/integration.md)
   + [Campaign + Experience Platform](connect/ac-aep.md)
   + [Campaign + Journey Optimizer](connect/ac-ajo.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + Experience Cloud Triggers](connect/ac-triggers.md)
   + [Campaign + Twitter](connect/ac-tw.md)
   + [Campaign + externe Datenbank](connect/fda.md)
   + Campaign + Ihr CRM-System   {#ac-crm}
      + [Erste Schritte mit CRM-Connectoren](connect/crm.md)
      + [Arbeiten mit Campaign und SFDC](connect/ac-sfdc.md)
      + [Arbeiten mit Campaign und Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [Daten synchronisieren](connect/crm-data-sync.md)
+ Administration {#admin}
   + Benutzer und Berechtigungen {#permissions}
      + [Erste Schritte mit Berechtigungen](start/gs-permissions.md)
      + [Verwalten von Benutzerberechtigungen](start/manage-permissions.md)
      + [Berechtigungen für Ordner hinzufügen](start/folder-permissions.md)
   + [Control Panel](config/self-service.md)
+ Architektur und Konfiguration {#config}
   + Architektur {#architecture}
      + [Allgemeine Prinzipien](architecture/general-architecture.md)
      + [Architektur](architecture/architecture.md)
      + FDA-Snowflake-Implementierung {#fda}
         + [Was ist FDA-Snowflake?](architecture/fda-deployment.md)
      + FFDA-Implementierung in Unternehmen {#ffda}
         + [Was ist Campaign FFDA?](architecture/enterprise-deployment.md)
         + Merkmale {#ffda-characteristics}
            + [Schlüsselverwaltung und Eindeutigkeit](architecture/keys.md)
            + [Neue APIs](architecture/new-apis.md)
            + [API-Staging-Mechanismus](architecture/staging.md)
            + [Replikationsmechanismus](architecture/replication.md)
   + Implementierung {#implement}
      + [Implementierungsschritte](start/implement.md)
      + [Anpassen der Instanz](dev/customize.md)
      + [Best Practices für Datenmodelle](dev/datamodel-best-practices.md)
   + Konfiguration {#configuration}
      + [E-Mail-Einstellungen](config/email-settings.md)
      + [Einstellungen für Transaktionsnachrichten](config/transactional-msg-settings.md)
      + [Campaign SDKs mit Ihrer Mobile App integrieren](config/push-config.md)
      + [Externe Konten](config/external-accounts.md)
+ Ressourcen für Entwickler {#developer}
   + [Campaign-Datenmodell](dev/datamodel.md)
   + Schemata und Formulare {#shemas-forms}
      + [Arbeiten mit Schemata](dev/schemas.md)
      + [Erstellen von Schemata](dev/create-schema.md)
      + [Erweitern von Schemata](dev/extend-schema.md)
      + [Filtern von Schemata](dev/filter-schema.md)
      + [Schemastruktur](dev/schema-structure.md)
      + [Datenbank-Mapping](dev/database-mapping.md)
      + [Einschränken der Anzeige von personenbezogenen Daten](dev/restrict-pi-view.md)
      + [Verwenden einer benutzerdefinierten Empfängertabelle](dev/custom-recipient.md)
      + [Aktualisieren der Datenbank](dev/update-database-structure.md)
      + [Formulare](dev/forms.md)
   + [Campaign-APIs](dev/api.md)
+ [Campaign Control Panel >](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=de)
+ [Handbuch zur Kampagnenautomatisierung >](https://experienceleague.adobe.com/docs/campaign/automation/home.html?lang=de)
