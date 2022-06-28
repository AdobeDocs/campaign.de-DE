---
audience: end-user
user-guide-title: Campaign v8
description: Dokumentation zu Campaign v8
breadcrumb-title: Campaign v8
title: Dokumente zu Campaign v8
source-git-commit: 099d14ace04df1b98e03be283a6436f49f535958
workflow-type: ht
source-wordcount: '353'
ht-degree: 100%

---


# Dokumentation zu Adobe Campaign v8 {#campaign-v8}

+ [Dokumentation zu Campaign v8](campaign-home.md)
+ Neue Funktionen {#new}
   + [Wichtigste Funktionen](start/whats-new.md)
   + [Versionshinweise](start/release-notes.md)
   + [Bekannte Einschränkungen](start/known-limitations.md)
   + [Bekannte Probleme](start/known-issues.md)
   + [Wechsel von Classic v7 zu v8](start/capability-matrix.md)
+ Starten {#start}
   + [Erste Schritte](start/get-started.md)
   + [Komponenten und Prozesse](start/ac-components.md)
   + Campaign-Benutzeroberfläche {#ac-ui}
      + [Erkunden der Benutzeroberfläche von Campaign](start/campaign-ui.md)
      + [Anpassen der Benutzeroberfläche von Campaign](start/customize-ui.md)
   + [Verwenden von Audiences](start/audiences.md)
   + [Verwalten von Datenschutzanfragen](start/privacy.md)
   + [Datenimport](start/import.md)
   + [Erstellen von Kampagnen](start/campaigns.md)
   + [Senden von Nachrichten](start/create-message.md)
   + [Verwalten von Abonnements](start/subscriptions.md)
   + [Verfolgen und Überwachen](start/tracking.md)
   + [Metriken und Berichte](start/reporting.md)
   + [Häufig gestellte Fragen](start/campaign-faq.md)
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
+ Implementieren {#implement}
   + [Implementierungsschritte](start/implement.md)
   + [Anpassen der Instanz](dev/customize.md)
   + [Sicherheitsrichtlinien](config/security.md)
   + [Entwerfen von Web-Anwendungen und Formularen](dev/webapps.md)
   + [Best Practices für Datenmodelle](dev/datamodel-best-practices.md)
+ Freigeben {#deploy}
   + [Kompatibilitätsmatrix](start/compatibility-matrix.md)
   + [Herstellen einer Verbindung zu Campaign](start/connect.md)
   + [Berechtigungen](start/permissions.md)
   + [Control Panel](config/self-service.md)
+ Profile und Audiences {#profiles-and-audiences}
   + [Erste Schritte](audiences/gs-audiences.md)
   + [Zugriff auf Profile](audiences/view-profiles.md)
   + Hinzufügen von Profilen {#add-profiles}
      + [Manuelles Erstellen von Profilen](audiences/create-profiles.md)
      + [Importieren von Profilen aus einer Datei](audiences/import-profiles.md)
      + [Arbeiten mit externen Profilen](audiences/external-profiles.md)
      + [Erfassen von Profildaten in Web-Formularen](audiences/collect-profiles.md)
   + Erstellen von Audiences {#create-audiences}
      + [Erstellen einer Liste von Kontakten](audiences/create-audiences.md)
      + [Erstellen und Verwalten von Filtern](audiences/create-filters.md)
   + [Verwalten von Ordnern und Ansichten](audiences/folders-and-views.md)
   + [Best Practices](audiences/audiences-best-practices.md)
+ Senden von Nachrichten {#send}
   + E-Mails {#emails}
      + [Entwerfen und Validieren von E-Mails](send/email.md)
      + [Versenden und Überwachen von E-Mails](send/send.md)
   + [SMS](send/sms.md)
   + [Push-Benachrichtigungen ](send/push.md)
   + [LINE-Messaging](send/line.md)
   + [Briefpost](send/direct-mail.md)
   + [Social-Media-Marketing](send/twitter.md)
   + [Transaktionsnachrichten](send/transactional.md)
   + Fehler, Bounces und Quarantänen{#failures}
      + [Quarantänen](send/quarantines.md)
      + [Versandfehler](send/delivery-failures.md)
+ Echtzeit-Interaktion{#interaction}
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
+ Konfigurieren {#config}
   + [Automatisieren mit Workflows](config/workflows.md)
   + [E-Mail-Einstellungen](config/email-settings.md)
   + [Einstellungen für Transaktionsnachrichten](config/transactional-msg-settings.md)
   + [Campaign SDKs mit Ihrer Mobile App integrieren](config/push-config.md)
   + [Externe Konten](config/external-accounts.md)
+ Verbinden {#connect}
   + [Herstellen von Verbindungen zu anderen Lösungen](connect/integration.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + Experience Cloud Triggers](connect/ac-triggers.md)
   + [Campaign + Real-Time CDP](connect/ac-rtcdp.md)
   + [Campaign + Twitter](connect/ac-tw.md)
   + [Campaign + externe Datenbank](connect/fda.md)
   + Campaign + Ihr CRM-System   {#ac-crm}
      + [Erste Schritte mit CRM-Connectoren](connect/crm.md)
      + [Arbeiten mit Campaign und SFDC](connect/ac-sfdc.md)
      + [Arbeiten mit Campaign und Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [Daten synchronisieren](connect/crm-data-sync.md)
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
+ [Campaign Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=de)

