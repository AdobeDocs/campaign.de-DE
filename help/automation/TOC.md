---
audience: user
user-guide-title: Handbuch zur Kampagnenautomatisierung
user-guide-description: Handbuch zur Kampagnenautomatisierung
source-git-commit: 7fe079c5473fa164405753c2be6cc8be16329f58
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 100%

---


# Handbücher zur Kampagnenautomatisierung {#automation}

+ [Handbuch zur Kampagnenautomatisierung](home.md)
+ Mit Workflows automatisieren {#workflows}
   + Erste Schritte mit Workflows {#introduction}
      + [Über Workflows](workflow/about-workflows.md)
      + Typen von Workflows {#wf-type}
         + [Zielgruppen-Workflows](workflow/targeting-workflows.md)
         + [Kampagnen-Workflows](workflow/campaign-workflows.md)
         + [Technische Workflows](workflow/technical-workflows.md)
      + [Erstellen eines Workflows](workflow/build-a-workflow.md)
      + [Best Practices](workflow/workflow-best-practices.md)
      + [Verwenden von Workflow-Daten](workflow/use-workflow-data.md)
   + Workflow ausführen {#executing-a-workflow}
      + [Workflow starten](workflow/start-a-workflow.md)
      + [Lebenszyklus eines Workflows](workflow/workflow-life-cycle.md)
      + [Einrichten von Validierungen](workflow/define-approvals.md)
   + Überwachen von Workflows {#monitoring-workflows}
      + [Überwachen der Workflow-Ausführung](workflow/monitor-workflow-execution.md)
      + [Überwachen technischer Workflows](workflow/monitor-technical-workflows.md)
      + [Workflow-Heatmap](workflow/heatmap.md)
   + Workflow-Aktivitäten {#wf-activities}
      + [Erste Schritte mit Aktivitäten](workflow/activities.md)
      + Zielgruppenaktivitäten {#targeting-activities}
         + [Liste der Zielgruppenaktivitäten](workflow/targeting-activities.md)
         + [Segmente](workflow/cells.md)
         + [Ändern der Datenquelle](workflow/change-data-source.md)
         + [Ändern der Dimension](workflow/change-dimension.md)
         + [CRM-Connector](workflow/crm-connector.md)
         + [Deduplizierung](workflow/deduplication.md)
         + [Versandentwurf](workflow/delivery-outline.md)
         + [Bearbeiten von Schemas](workflow/edit-schema.md)
         + [Anreicherung](workflow/enrichment.md)
         + [Ausschluss](workflow/exclusion.md)
         + [Inkrementelle Abfrage](workflow/incremental-query.md)
         + [Schnittmenge](workflow/intersection.md)
         + [Listen-Update](workflow/list-update.md)
         + [Angebote pro Segment](workflow/offers-by-cell.md)
         + [Angebotsmodul](workflow/offer-engine.md)
         + [Abfrage](workflow/query.md)
         + [Liste lesen](workflow/read-list.md)
         + [Aufspaltung](workflow/split.md)
         + [Abonnements](workflow/subscription-services.md)
         + [Vereinigung](workflow/union.md)
         + [Daten-Update](workflow/update-data.md)
      + Fluss-Steuerungsaktivitäten {#flow-control-activities}
         + [Liste der Fluss-Steuerungsaktivitäten](workflow/flow-control-activities.md)
         + [Warnhinweis](workflow/alert.md)
         + [Und-Verknüpfung](workflow/and-join.md)
         + [Validierung](workflow/approval.md)
         + [Externes Signal](workflow/external-signal.md)
         + [Verzweigung](workflow/fork.md)
         + [Sprung (Start und Ende)](workflow/jump--start-point-and-end-point-.md)
         + [Start und Ende](workflow/start-and-end.md)
         + [Planung](workflow/scheduler.md)
         + [Unter-Workflow](workflow/sub-workflow.md)
         + [Test](workflow/test.md)
         + [Zeitliche Beschränkung](workflow/time-constraint.md)
         + [Warten](workflow/wait.md)
      + Aktionsaktivitäten {#action-activities}
         + [Liste der Aktionsaktivitäten](workflow/action-activities.md)
         + [Content-Management](workflow/content-management.md)
         + [Versand (fortlaufend)](workflow/continuous-delivery.md)
         + [Kanalübergreifender Versand](workflow/cross-channel-deliveries.md)
         + [Datenextraktion (Datei)](workflow/extraction--file-.md)
         + [Laden (Datei)](workflow/data-loading--file-.md)
         + [Laden (DBMS)](workflow/data-loading--rdbms-.md)
         + [Versand](workflow/delivery.md)
         + [Versand bearbeiten](workflow/delivery-control.md)
         + [Lokale Validierung](workflow/local-approval.md)
         + [Laden (SOAP)](workflow/loading-soap.md)
         + [nlserver-Modul](workflow/nlserver-module.md)
         + [Wiederkehrender Versand](workflow/recurring-delivery.md)
         + [SQL-Code und JavaScript-Code](workflow/sql-code-and-javascript-code.md)
         + [SQL-Daten-Management](workflow/sql-data-management.md)
         + [Aggregat-Update](workflow/update-aggregate.md)
      + Ereignisaktivitäten {#event-activities}
         + [Liste der Ereignisaktivitäten](workflow/event-activities.md)
         + [Datei-Wächter](workflow/file-collector.md)
         + [Dateiübertragung](workflow/file-transfer.md)
         + [E-Mail-Empfang](workflow/inbound-emails.md)
         + [SMS-Empfang](workflow/inbound-sms.md)
         + [HTTP-Übertragung](workflow/web-download.md)
   + Anwendungsfälle {#use-cases}
      + [Über Workflow-Anwendungsfälle](workflow/workflow-use-cases.md)
      + Sendungen {#deliveries}
         + [Verwenden der lokalen Validierung](workflow/local-approval-activity.md)
         + [Senden einer Geburtstags-E-Mail](workflow/send-a-birthday-email.md)
         + [Laden des Versandinhalts](workflow/load-delivery-content.md)
         + [Workflow für einen kanalübergreifenden Versand](workflow/cross-channel-delivery-workflow.md)
         + [E-Mail-Anreicherung mit benutzerdefinierten Datumsfeldern](workflow/email-enrichment-with-custom-date-fields.md)
      + Monitoring      {#monitoring}
         + [Senden eines Berichts an eine Liste](workflow/send-a-report-to-a-list.md)
         + [Überwachen Ihrer Workflows](workflow/workflow-supervision.md)
         + [Senden personalisierter Warnungen an Benutzer](workflow/send-alerts-to-operators.md)
      + Daten-Management {#data-management}
         + [Koordinieren von Datenaktualisierungen](workflow/coordinate-data-updates.md)
         + [Erstellen einer zusammenfassenden Liste](workflow/create-a-summary-list.md)
         + [Anreichern von Daten](workflow/enrich-data.md)
         + [Verwenden von Aggregaten](workflow/using-aggregates.md)
         + [Verwenden der Zusammenführungsfunktion der Deduplizierungsaktivität](workflow/deduplication-merge.md)
         + [Einrichten eines Workflows für den wiederkehrenden Import](workflow/recurring-import-workflow.md)
      + Erstellen von Abfragen {#designing-queries}
         + [Vierteljährliches Listen-Update mithilfe einer inkrementellen Abfrage](workflow/quarterly-list-update.md)
      + Abfrage und Filter {#designing-queries}
         + [Abfrage zur Empfängertabelle](workflow/querying-recipient-table.md)
         + [Informationen zum Abfrageversand](workflow/query-delivery-info.md)
         + [Berechnen von Aggregaten](workflow/compute-aggregates.md)
         + [Abfrage mit Gruppierungsverwaltung](workflow/query-grouping-management.md)
         + [Abfrage mit einer n:n-Beziehung](workflow/query-many-to-many-relationship.md)
         + [Hinzufügen eines berechneten Auflistungsfelds](workflow/adding-enumeration-type-calculated-field.md)
         + [Erstellen von Filtern](workflow/create-a-filter.md)
         + [Filtern doppelter Empfänger](workflow/filter-duplicated-recipients.md)
   + Erweiterte Parameter {#advanced-management}
      + [Workflow-Eigenschaften](workflow/workflow-properties.md)
      + [Erweiterte Parameter](workflow/advanced-parameters.md)
      + [JavaScript-Scripte und -Vorlagen](workflow/javascript-scripts-and-templates.md)
      + [Beispiele für JavaScript-Code in Workflows](workflow/javascript-in-workflows.md)
      + [Auf eine externe Datenbank zugreifen](workflow/accessing-an-external-database--fda-.md)
      + [Verwalten von Berechtigungen](workflow/managing-rights.md)
      + [Ändern von Aktivitätsbildern](workflow/change-activity-images.md)
      + [Verwalten von Zeitzonen](workflow/managing-time-zones.md)
+ Kampagnenorchestrierung {#campaign-orchestration}
   + [Erste Schritte mit Marketing-Kampagnen](campaigns/set-up-campaigns.md)
   + [Erstellen von Programmen und Kampagnen](campaigns/marketing-campaign-create.md)
   + [Vorlagen erstellen und konfigurieren](campaigns/marketing-campaign-templates.md)
   + [Sendungen hinzufügen](campaigns/marketing-campaign-deliveries.md)
   + [Audience auswählen](campaigns/marketing-campaign-target.md)
   + [Dokumente und Assets verwalten](campaigns/marketing-campaign-assets.md)
   + [Genehmigungen einrichten und verwalten](campaigns/marketing-campaign-approval.md)
   + [Wiederkehrende und periodische Kampagnen](campaigns/recurring-periodic-campaigns.md)
   + [Kampagnen überwachen](campaigns/marketing-campaign-monitoring.md)
   + [Dienstleister, Lager und Budgets](campaigns/providers--stocks-and-budgets.md)
+ Kampagnenoptimierung (Add-on){#campaign-optimization}
   + [Erste Schritte mit Kampagnentypologien](campaign-opt/campaign-typologies.md)
   + [Filterregeln](campaign-opt/filtering-rules.md)
   + [Kontrollregeln](campaign-opt/control-rules.md)
   + [Druckregeln](campaign-opt/pressure-rules.md)
   + [Kohärenzregeln](campaign-opt/consistency-rules.md)
   + [Regeln anwenden](campaign-opt/apply-rules.md)
   + [Kampagnensimulation](campaign-opt/campaign-simulations.md)
+ Verteiltes Marketing (Add-on) {#distributed-marketing}
   + [Über dezentrales Marketing](distributed-marketing/about-distributed-marketing.md)
   + [Lokale Kampagnen erstellen](distributed-marketing/creating-a-local-campaign.md)
   + [Partizipative Kampagnen erstellen](distributed-marketing/creating-a-collaborative-campaign.md)
   + [Kampagnenkit veröffentlichen](distributed-marketing/publishing-the-campaign-package.md)
   + [Auf Kampagnen zugreifen](distributed-marketing/accessing-campaigns.md)
   + [Verfolgen einer Kampagne](distributed-marketing/tracking-a-campaign.md)
   + [Anwendungsfälle](distributed-marketing/examples.md)
+ [Dokumentation zu Campaign v8](https://experienceleague.adobe.com/docs/campaign/campaign-v8/campaign-home.html?lang=de)