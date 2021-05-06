---
solution: Campaign Classic
product: campaign
title: Erste Schritte mit Marketing-Kampagnen
description: Erste Schritte mit Marketing-Kampagnen
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: b5a6c845-13a7-4746-b856-a08a3cf80b66,c4798c8f-619e-4a60-80d7-29b9e4c61168
translation-type: tm+mt
source-git-commit: d7d026422d43e8baef43b114936366071f7086e5
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 13%

---

# Erste Schritte mit Marketing-Kampagnen{#gs-ac-campaigns}

Adobe Campaign Angebots bietet eine Reihe von Lösungen, mit deren Hilfe Sie Kampagnen für alle Ihre Online- und Offline-Kanal personalisieren und bereitstellen können. Sie können Marketing-Kampagnen erstellen, konfigurieren, ausführen und analysieren. Alle Marketing-Kampagnen können von einem einheitlichen Kontrollzentrum verwaltet werden. Hier erfahren Sie, wie Sie Marketing-Kampagnen durchsuchen und erstellen.

Kampagnen umfassen Aktionen (Sendungen) und Prozesse (Import oder Extraktion von Dateien) sowie Ressourcen (Marketing-Dokumente, Versandentwürfe). Sie werden in Marketing-Kampagnen verwendet. Kampagnen sind Teil eines Programms und Programme Teil eines Kampagnenplans.

## Kanalübergreifende Orchestrierung einer Kampagne

Mit Adobe Campaign können Sie zielgerichtete und personalisierte Kampagnen auf mehreren Kanälen entwerfen und orchestrieren: E-Mail, Direktnachricht, SMS, Push-Benachrichtigung. Eine einzige Oberfläche bietet Ihnen alle erforderlichen Funktionen, um alle Ihre Kampagnen und Mitteilungen zu planen, zu orchestrieren, zu konfigurieren, zu personalisieren, zu automatisieren, auszuführen und zu messen.

### Grundbegriffe

Bevor Sie mit der Implementierung von Marketing-Kampagnen beginnen, müssen Sie mit den folgenden Begriffen vertraut sein:

* **Marketing-Kampagne**: Eine Kampagne zentralisiert alle Elemente im Zusammenhang mit einer Marketing-Kampagne: Versand, Targeting-Regeln, Kosten, Exportdateien, zugehörige Dokumente usw. Jede Kampagne ist an ein Programm angehängt.

* **Programm**: Mit einem Programm können Sie Marketingaktionen für einen Kalenderzeitraum definieren: Start, Arbeitsfläche, Loyalität usw. Jedes Programm enthält Kampagnen, die mit einem Kalender verknüpft sind und eine allgemeine Ansicht bieten.

* **Plan**: der Marketingplan kann mehrere Programm enthalten. Es ist an einen Kalenderzeitraum gebunden, verfügt über zugewiesene Haushaltsmittel und kann auch mit Dokumenten und Zielen verknüpft werden.

* **Arbeitsablauf** der Kampagne: ein Arbeitsablauf für Kampagnen enthält Aktivitäten zum Aufbau der Kampagne-Logik. Mit Kampagnen-Workflows können Sie Audiencen definieren und Versand für alle verfügbaren Kanal erstellen.

* **Wiederkehrende Kampagnen**: wiederkehrende Kampagnen werden aus einer bestimmten Vorlage erstellt, die die auszuführende Workflow-Vorlage und den Ausführungsplan definiert.

* **Regelmäßige Kampagnen**: eine periodische Kampagne ist eine Kampagne, die automatisch gemäß dem Ausführungsplan ihrer Vorlage erstellt wird.

## Arbeitsbereich Marketing-Kampagne

Mit Adobe Campaign können Sie alle Marketing-Kampagnen aus einem einheitlichen Kontrollzentrum erstellen, konfigurieren, ausführen und analysieren.

:arrow_upper_right: Erfahren Sie, wie Sie auf Marketing-Kampagnen zugreifen und diese implementieren können.[](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/about-marketing-campaigns/accessing-marketing-campaigns.html?lang=en#orchestrating-campaigns)


## Wichtige Schritte zum Beginn

Die wichtigsten Schritte zur Erstellung einer Kanal-übergreifenden Marketing-Kampagne sind:

1. **Planen und Entwerfen von Marketing-Programmen und -Kampagnen**

   Definieren Sie Hierarchie und Zeitplan, stellen Sie Budget ein, fügen Sie Ressourcen hinzu, wählen Sie Operatoren aus.

   :arrow_upper_right: Erfahren Sie, wie Sie einen Marketingplan erstellen und Kampagnen auf [dieser Seite konfigurieren](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#creating-plan-and-program-hierarchy)

   Alle Marketing-Kampagnen basieren auf einer Vorlage, in der die Haupteinstellungen und -funktionen gespeichert werden. Es wird eine native Vorlage bereitgestellt, mit der Sie eine Kampagne erstellen können, für die keine bestimmte Konfiguration definiert wurde. Sie können Ihre Kampagnenvorlagen erstellen und konfigurieren und dann Kampagnen aus diesen Vorlagen erstellen.

   :arrow_upper_right: Erfahren Sie, wie Sie mit Kampagnenvorlagen auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns) arbeiten.

   :arrow_upper_right: Entdecken Sie wiederkehrende Kampagnen und konfigurieren Sie sie auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns)

1. **Audiencen definieren**

   Sie können die Audience in einem Workflow erstellen oder eine bestehende Gruppe auswählen, z. B. eine Empfänger-Liste, Abonnenten eines Newsletters, Empfänger eines vorherigen Versands oder eine beliebige Filterbedingung.

   :arrow_upper_right: Erfahren Sie, wie Sie die Audience Ihrer Nachrichten auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#orchestrating-campaigns) definieren.

1. **Sendungen erstellen**

   Wählen Sie Kanal aus, definieren Sie den Nachrichteninhalt und Beginn-Versand.

   :arrow_upper_right: Erfahren Sie, wie Sie Versand für Marketing-Kampagnen in [dieser  erstellen und Beginn darauf verwenden](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=en#creating-deliveries)

   Sie können einer Kampagne verschiedene Dokumente zuordnen: Bericht, Foto, Webseite, Diagramm usw.

   :arrow_upper_right: Weitere Informationen zu verknüpften Dokumenten finden Sie in [diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-assets.html?lang=en#adding-documents)

1. **Einrichten des Genehmigungsprozesses**

   Mit Adobe Campaign können Sie gemeinsame Genehmigungsprozesse für die Hauptphasen der Marketing-Kampagne einrichten. Für jede Kampagne können Sie die Zielgruppe, den Inhalt und die Kosten des Versands genehmigen. Die für die Genehmigung zuständigen Adobe Campaign-Betreiber können per E-Mail benachrichtigt werden und die Genehmigung von der Konsole oder über eine Webverbindung annehmen oder ablehnen.

   :arrow_upper_right: Erfahren Sie, wie Sie Genehmigungen in [dieser Seite einrichten und verwalten](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=en#orchestrating-campaigns)


1. Meldungen überwachen: Versand steuern und ausführen. Mehr dazu.

1. Planen von Kampagnen und der damit verbundenen Kosten. Mehr dazu.

## Genehmigungen und Validierung


## Dienste und Abonnements

Erstellen von Diensten und Verwalten von Abonnements/Abmeldungen

## Reporting

Kampagnenberichte

:bulb:
