---
title: Erste Schritte mit Kampagnen
description: Erste Schritte mit Kampagnen
feature: Cross Channel Orchestration
role: User
level: Beginner
exl-id: b5a6c845-13a7-4746-b856-a08a3cf80b66
source-git-commit: 8d6c3e03f9b7533f7f325b755e3b6d4f74b63a8d
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 93%

---

# Erste Schritte mit Kampagnen {#gs-ac-campaigns}

Adobe Campaign umfasst mehrere Lösungen, mit denen Sie Kampagnen personalisieren und auf allen Online- und Offline-Kanälen versenden können. Sie können Marketing-Kampagnen erstellen, konfigurieren, ausführen und analysieren. Alle Marketing-Kampagnen können von einem einheitlichen Kontrollzentrum aus verwaltet werden. In diesem Abschnitt erfahren Sie, wie Sie Marketing-Kampagnen durchsuchen und erstellen können.

Kampagnen umfassen Aktionen (Sendungen) und Prozesse (Import oder Extraktion von Dateien) sowie Ressourcen (Marketing-Dokumente, Versandentwürfe). Sie werden in Marketing-Kampagnen verwendet. Kampagnen sind Teil eines Programms und Programme Teil eines Kampagnenplans.

## Kanalübergreifende Orchestrierung einer Kampagne{#cross-channel-orchestration}

Adobe Campaign unterstützt Sie bei der Konzeption und Orchestrierung von zielgerichteten und personalisierten Kampagnen auf verschiedenen Kanälen: E-Mail, Briefpost, SMS und Push-Benachrichtigung. Über nur eine Oberfläche können Sie all Ihre Kampagnen und Kommunikationen planen, orchestrieren, konfigurieren, personalisieren, automatisieren, ausführen und messen.

![](assets/campaign-tab.png)

### Grundbegriffe{#ac-core-concepts}

Bevor Sie mit der Implementierung von Marketing-Kampagnen beginnen, müssen Sie mit den folgenden Begriffen vertraut sein:

* **Marketing-Kampagne**: Eine Kampagne zentralisiert alle Elemente im Zusammenhang mit einer Marketing-Kampagne: Versand, Zielgruppenbestimmungs-Regeln, Kosten, Exportdateien, zugehörige Dokumente usw. Jede Kampagne ist an ein Programm angehängt.

* **Programm**: Mit einem Programm können Sie Marketing-Aktionen für einen Zeitraum im Kalender definieren: Start, Canvassing, Treue usw. Jedes Programm enthält Kampagnen, die mit einem Kalender verknüpft sind, der eine Gesamtübersicht bietet.

* **Plan**: der Marketing-Plan kann mehrere Programm enthalten. Er ist an einen Zeitraum im Kalender gebunden, verfügt über zugewiesene Haushaltsmittel und kann auch mit Dokumenten und Zielen verknüpft werden.

* **Kampagnen-Workflow** ein Kampagnen-Workflow enthält Aktivitäten zum Aufbau der Kampagnen-Logik. Verwenden Sie Kampagnen-Workflows, um Zielgruppen zu definieren und Sendungen für alle verfügbaren Kanäle zu erstellen.

* **Wiederkehrende Kampagnen**: wiederkehrende Kampagnen werden anhand einer bestimmten Vorlage erstellt, die die auszuführende Workflow-Vorlage definiert, und anhand der Ausführungsplanung.

* **Periodische Kampagnen**: eine periodische Kampagne ist eine Kampagne, die automatisch nach der Ausführungsplanung ihrer Vorlage erstellt wird.

## Marketing-Kampagnen-Arbeitsbereich{#ac-workspace}

Adobe Campaign ermöglicht die Erstellung, Konfiguration, Ausführung und Analyse von Marketing-Kampagnen über ein einheitliches Kontrollzentrum.

![](assets/calendar.png)

In diesem Abschnitt erfahren Sie, wie Sie auf Marketing[Kampagnen zugreifen und diese implementieren ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=de){target="_blank"}.

## Wichtige Schritte zum Beginn{#gs-ac-start}

Die wichtigsten Schritte zur Erstellung einer Cross-Channel-Marketing-Kampagne sind:

1. **Planen und Entwerfen von Marketing-Programmen und -Kampagnen**

   Definieren Sie Hierarchie und Zeitplan, stellen Sie Budget ein, fügen Sie Ressourcen hinzu, wählen Sie Benutzer aus.

   Auf [ Seite erfahren Sie, wie Sie einen Marketing-Plan erstellen und Kampagnen konfigurieren ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-create.html?lang=de){target="_blank"}.

   Alle Marketing-Kampagnen basieren auf einer Vorlage, in der die Haupteinstellungen und -funktionen gespeichert sind. Es wird eine native Vorlage bereitgestellt, mit der Sie eine Kampagne erstellen können, für die keine bestimmte Konfiguration definiert wurde. Sie können Ihre Kampagnenvorlagen erstellen und konfigurieren und dann Kampagnen aus diesen Vorlagen erstellen.

   Auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-templates.html?lang=de){target="_blank"} erfahren Sie, wie Sie mit Kampagnenvorlagen arbeiten.

   Auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=de){target="_blank"} erfahren Sie mehr über wiederkehrende Kampagnen und darüber, wie Sie diese konfigurieren können.

1. **Zielgruppen definieren**

   Sie können die Zielgruppe in einem Workflow erstellen oder eine bestehende Gruppe auswählen, z. B. eine Empfänger-Liste, Abonnenten eines Newsletters, Empfänger eines vorherigen Versands oder eine beliebige Filterbedingung.

   ![](assets/campaign-wf.png)

   Auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=de){target="_blank"} erfahren Sie, wie Sie die Zielgruppe für Ihre Nachrichten definieren.

1. **Sendungen erstellen**

   Wählen Sie einen oder mehrere Kanäle aus, definieren Sie den Nachrichteninhalt und starten Sie Sendungen.

   ![](assets/campaign-dashboard.png)

   Auf [dieser Seite](../../automation/campaigns/marketing-campaign-deliveries.md) erfahren Sie, wie Sie Sendungen für Marketing-Kampagnen erstellen und starten.

   Sie können einer Kampagne verschiedene Dokumente zuordnen: Bericht, Foto, Web-Seite, Diagramm usw. Auf [dieser Seite](../../automation/campaigns/marketing-campaign-assets.md) erfahren Sie mehr über zugehörige Dokumente.

1. **Einrichten des Validierungsprozesses**

   Adobe Campaign ermöglicht den Einsatz von partizipativen Validierungsprozessen für die wichtigsten Etappen einer Marketing-Kampagne. Für jede Kampagne können Sie die Versandzielgruppe, den Inhalt und die Kosten validieren. Die für die Validierung zuständigen Adobe Campaign-Benutzer können per E-Mail benachrichtigt werden und eine Validierung über die Konsole oder eine Internet-Verbindung annehmen oder ablehnen.

   Auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=de#campaign-orchestration){target="_blank"} erfahren Sie, wie Sie Validierungen einrichten und verwalten können.


## Add-on für verteiltes Marketing{#distributed-marketing-add-on}

Adobe Campaign bietet ein Add-on für **verteiltes Marketing** zur Implementierung von Kooperationskampagnen zwischen zentralen Entitäten (Hauptsitz, Marketing-Abteilungen) und lokalen Entitäten (Filialen und regionale Agenturen). Diese Zusammenarbeit basiert auf einem gemeinsamen Arbeitsbereich, auch **[!UICONTROL Kampagnenkit-Liste]** genannt, wobei von zentralen Entitäten entworfene Kampagnenvorlagen den lokalen Entitäten angeboten werden.

>[!NOTE]
>
>Diese Funktion ist ab Campaign v8.3 verfügbar. Informationen zur Überprüfung Ihrer Version finden Sie in [diesem Abschnitt](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).

Auf [ Seite erfahren Sie, wie Sie die Funktionen von Campaign für dezentrales Marketing konfigurieren und ](https://experienceleague.adobe.com/docs/campaign/automation/distributed-marketing/about-distributed-marketing.html?lang=de){target="_blank"}.

## Add-on &quot;Reaktionsverwaltung&quot;{#response-manager-add-on}

Adobe Campaign bietet ein Add-on zur **Reaktionsverwaltung** (Response Manager), mit dem Sie den Erfolg und die Rentabilität von Marketing-Kampagnen oder Angebotsvorschlägen über alle Kommunikationskanäle hinweg messen können: E-Mail, Mobilgeräte, Briefpost usw.

>[!NOTE]
>
>Diese Funktion ist ab Campaign v8.3 verfügbar. Informationen zur Überprüfung Ihrer Version finden Sie in [diesem Abschnitt](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).

[&#128279;](../assets/do-not-localize/book.png) Erfahren Sie in der [Dokumentation zu Campaign Classic v7, wie Sie den Campaign Response Manager konfigurieren und ](https://experienceleague.adobe.com/docs/campaign-classic/using/response-manager/about-response-manager.html?lang=de){target="_blank"}.
