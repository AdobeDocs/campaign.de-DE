---
solution: Campaign v8
product: Adobe Campaign
title: Erste Schritte mit Marketing-Kampagnen
description: Erste Schritte mit Marketing-Kampagnen
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: b5a6c845-13a7-4746-b856-a08a3cf80b66,c4798c8f-619e-4a60-80d7-29b9e4c61168
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 12%

---

# Erste Schritte mit Marketing-Kampagnen{#gs-ac-campaigns}

Adobe Campaign bietet eine Reihe von Lösungen, mit denen Sie Kampagnen personalisieren und über alle Ihre Online- und Offline-Kanäle hinweg bereitstellen können. Sie können Marketingkampagnen erstellen, konfigurieren, ausführen und analysieren. Alle Marketing-Kampagnen können von einem einheitlichen Kontrollzentrum aus verwaltet werden. In diesem Abschnitt erfahren Sie, wie Sie Marketing-Kampagnen durchsuchen und erstellen.

Kampagnen umfassen Aktionen (Sendungen) und Prozesse (Import oder Extraktion von Dateien) sowie Ressourcen (Marketing-Dokumente, Versandentwürfe). Sie werden in Marketing-Kampagnen verwendet. Kampagnen sind Teil eines Programms und Programme Teil eines Kampagnenplans.

## Kanalübergreifende Orchestrierung einer Kampagne

Mit Adobe Campaign können Sie zielgerichtete und personalisierte Kampagnen auf mehreren Kanälen entwerfen und organisieren: E-Mail, Briefpost, SMS, Push-Benachrichtigung. Über eine einzige Oberfläche erhalten Sie alle Funktionen, die zum Planen, Orchestrieren, Konfigurieren, Personalisieren, Automatisieren, Ausführen und Messen all Ihrer Kampagnen und Kommunikationen erforderlich sind.

### Grundbegriffe

Bevor Sie mit der Implementierung von Marketing-Kampagnen beginnen, sollten Sie sich mit folgenden Konzepten vertraut machen:

* **Marketing-Kampagne**: eine Kampagne, die alle Elemente einer Marketingkampagne zusammenfasst: Sendungen, Targeting-Regeln, Kosten, Exportdateien, zugehörige Dokumente usw. Jede Kampagne ist an ein Programm angehängt.

* **Programm**: Ein Programm ermöglicht die Definition von Marketing-Aktionen für einen Kalenderzeitraum: Launch, Kundenwerbung, Treueprogramm usw. Jedes Programm enthält Kampagnen, die mit einem Kalender verknüpft sind, der eine Gesamtübersicht bietet.

* **Plan**: der Marketingplan kann mehrere Programme enthalten. Er ist mit einem Kalenderzeitraum verknüpft, verfügt über ein zugewiesenes Budget und kann auch mit Dokumenten und Zielen verknüpft werden.

* **Kampagnen-Workflow**: Ein Kampagnen-Workflow enthält Aktivitäten zum Erstellen der Kampagnenlogik. Verwenden Sie Kampagnen-Workflows, um Zielgruppen zu definieren und Sendungen für alle verfügbaren Kanäle zu erstellen.

* **Wiederkehrende Kampagnen**: Wiederkehrende Kampagnen werden basierend auf einer spezifischen Vorlage erstellt, die die auszuführende Workflow-Vorlage und den Ausführungsplan definiert.

* **Regelmäßige Kampagnen**: Eine periodische Kampagne ist eine Kampagne, die automatisch entsprechend der Ausführungsplanung ihrer Vorlage erstellt wird.

## Arbeitsbereich für Marketing-Kampagnen

Mit Adobe Campaign können Sie alle Marketing-Kampagnen in einem einheitlichen Kontrollzentrum erstellen, konfigurieren, ausführen und analysieren.

[!DNL :arrow_upper_right:] Erfahren Sie, wie Sie in der Dokumentation zu  [Campaign Classic v7 auf Marketing-Kampagnen zugreifen und diese implementieren können.](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/about-marketing-campaigns/accessing-marketing-campaigns.html?lang=en#orchestrating-campaigns)


## Die wichtigsten Schritte zum Starten

Die wichtigsten Schritte zum Erstellen einer kanalübergreifenden Marketing-Kampagne sind:

1. **Planung und Konzeption von Marketing-Programmen und -Kampagnen**

   Definieren Sie Hierarchie und Zeitplan, legen Sie Budget fest, fügen Sie Ressourcen hinzu, wählen Sie Operatoren aus.

   [!DNL :arrow_upper_right:] Erfahren Sie, wie Sie einen Marketingplan erstellen und Kampagnen konfigurieren, in der Dokumentation zu  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#creating-plan-and-program-hierarchy)

   Alle Marketing-Kampagnen basieren auf einer Vorlage, die die wichtigsten Einstellungen und Funktionen speichert. Es wird eine native Vorlage bereitgestellt, mit der Sie eine Kampagne erstellen können, für die keine bestimmte Konfiguration definiert wurde. Sie können Ihre Kampagnenvorlagen erstellen und konfigurieren und dann Kampagnen aus diesen Vorlagen erstellen.

   [!DNL :arrow_upper_right:] Erfahren Sie in der Dokumentation zu  [Campaign Classic v7, wie Sie mit Kampagnenvorlagen arbeiten.](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)

   [!DNL :arrow_upper_right:] Erfahren Sie mehr über wiederkehrende Kampagnen und deren Konfiguration in der Dokumentation zu  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns)

1. **Zielgruppen definieren**

   Sie können die Audience in einem Workflow erstellen oder eine bestehende Gruppe auswählen, z. B. eine Empfängerliste, Abonnenten eines Newsletters, Empfänger eines früheren Versands oder eine beliebige Filterbedingung.

   [!DNL :arrow_upper_right:] Erfahren Sie, wie Sie die Audience Ihrer Nachrichten in der Dokumentation zu  [Campaign Classic v7 definieren.](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#orchestrating-campaigns)

1. **Sendungen erstellen**

   Wählen Sie Kanäle aus, definieren Sie den Nachrichteninhalt und starten Sie Sendungen.

   [!DNL :arrow_upper_right:] Erfahren Sie, wie Sie Marketingkampagnen-Sendungen erstellen und starten, in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=en#creating-deliveries)

   Sie können einer Kampagne verschiedene Dokumente zuordnen: Bericht, Foto, Webseite, Diagramm usw.

   [!DNL :arrow_upper_right:] Weitere Informationen zu verknüpften Dokumenten finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-assets.html?lang=en#adding-documents)

1. **Validierungsprozess einrichten**

   Mit Adobe Campaign können Sie kollaborative Validierungsprozesse für die wichtigsten Etappen der Marketingkampagne einrichten. Sie können für jede Kampagne Zielgruppe, Inhalt und Kosten des Versands validieren. Die für die Validierung zuständigen Adobe Campaign-Benutzer können per E-Mail benachrichtigt werden und die Validierung über die Konsole oder eine Webverbindung akzeptieren oder ablehnen.

   [!DNL :arrow_upper_right:] Informationen zum Einrichten und Verwalten von Genehmigungen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=en#orchestrating-campaigns)

