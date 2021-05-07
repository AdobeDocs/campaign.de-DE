---
solution: Campaign
product: Adobe Campaign
title: Erste Schritte mit Kampagne v8
description: Entdecken Sie wichtige Funktionen, die Benutzeroberfläche und globale Richtlinien
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
translation-type: tm+mt
source-git-commit: cebe3fedb97a5570aa404bf97709e6b26bf90d7c
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 40%

---

# Erste Schritte mit Adobe Campaign{#gs-ac-v8}

Adobe Campaign bietet eine Plattform für das Entwerfen von Kundenerlebnissen über Kanal hinweg und eine Umgebung für visuelle Kampagne-Orchestrierung, Interaktionsmanagement in Echtzeit und die Ausführung über Kanal hinweg.

Kampagne verwenden, um:

* Personalisierung und Interaktion durch eine einzige, zugängliche Ansicht des Kunden fördern
* Integrieren von E-Mail-, Mobil-, Online- und Offline-Kanälen in die Journey
* Automatisieren des Versands aussagekräftiger und zeitnaher Nachrichten und Angebot

![](assets/ac-capabilities.png)

## Integriertes Kundenprofil {#integrated-customer-profile}

Profil werden in einer leistungsstarken Cloud-Datenbank zentralisiert. Die Akquise von Profilen und die Datenbankerstellung können auf verschiedenste Weisen erfolgen: Online-Akquise über Web-Formulare, manueller oder automatisierter Import von Textdateien, Replikation von bereits existierenden Datenbanken oder Informationssystemen des Unternehmens. Mit Adobe Campaign können Sie Marketingverlauf, Kaufinformationen, Voreinstellungen, CRM-Daten und alle relevanten PII-Daten in eine konsolidierte Ansicht integrieren, um sie zu analysieren und Maßnahmen zu ergreifen.

In Adobe Campaign sind Empfänger die Standardprofile, an die Sendungen übermittelt werden (E-Mails, SMS etc.). Dank der in der Datenbank gespeicherten Empfängerdaten können Sie das Ziel filtern, das eine bestimmte Sendung erhält, und Personalisierungsdaten in Ihren Versandinhalten hinzufügen. In der Datenbank sind weitere Profiltypen vorhanden. Sie sind für andere Verwendungszwecke gedacht. Beispielsweise dienen Testprofile zum Testen von Sendungen, bevor sie tatsächlich an das endgültige Ziel übermittelt werden.

:bulb: Die Grundlagen der Profil-Verwaltung werden in [diesem Abschnitt](audiences.md) erläutert.

:bulb: In [diesem Abschnitt ](import.md) erfahren Sie, wie Sie Profil zur Kampagne hinzufügen.

## Zielgruppensegmentierung {#targeted-segmentation}

Adobe Campaign enthält leistungsstarke Analyse- und Zielgruppenbestimmungsfunktionen, die es Ihnen ermöglichen, sehr spezifische, dem Kundenprofil entsprechende Angebote zu erstellen. Dank der deskriptiven Analysefunktionen können Sie Informationen vor und nach Ihren Marketing-Kampagnen detailliert betrachten. Außerdem ermöglichen Filter und ein benutzerfreundliches Abfragetool, registrierte Kontakte mithilfe unzähliger Kriterien zu kategorisieren und extrem genaue Zielgruppen zu definieren.

Die erweiterte Data Management-Funktionalität erweitert die Datenverarbeitungsfunktionen. Es vereinfacht und optimiert den Targeting-Prozess durch die Einbeziehung von Daten, die nicht im Datamart modelliert wurden.

:bulb: Weitere Informationen zu Segmentierung, Erstellung und Personalisierung von Audiencen finden Sie in [diesem Abschnitt](audiences.md).

## Kanalübergreifende Orchestrierung einer Kampagne {#cross-channel-campaign-orchestration}

Mit Adobe Campaign können Sie zielgerichtete und personalisierte Kampagnen auf mehreren Kanälen entwerfen und orchestrieren: E-Mail, Direktnachricht, SMS, Push-Benachrichtigung. Eine einzige Oberfläche bietet Ihnen alle erforderlichen Funktionen, um alle Ihre Kampagnen und Mitteilungen zu planen, zu orchestrieren, zu konfigurieren, zu personalisieren, zu automatisieren, auszuführen und zu messen.

:bulb: Hier erfahren Sie, wie Sie eine Kampagne entwerfen, planen und ausführen.[](campaigns.md)

## Workflows

Adobe Campaign bietet eine umfassende grafische Oberfläche, die den Entwurf komplexer Arbeitsabläufe ermöglicht. Diese umfassen die Segmentierung von Zielgruppen, die Ausführung von Kampagnen, die Verarbeitung von Dateien usw. Erstellen Sie zum Beispiel einen Workflow, um eine Datei von einem Server herunterzuladen, sie zu entkomprimieren und die Datensätze in die Adobe-Campaign-Datenbank zu importieren.

Oder fordern Sie andere Benutzer auf, Aufgaben auszuführen oder zu validieren. Auf diese Weise ist es möglich, anderen Benutzern Aufgaben wie Inhaltsgestaltung, Zielgruppenbestimmung und Validierung von Testsendungen zuzuweisen, bevor eine Nachricht an die Empfänger verschickt wird.

Workflows können in unterschiedlichsten Kontexten zum Einsatz kommen:

* Zielgruppenbestimmung für Audiences oder zum Versand von Nachrichten.
* Daten-Management (ETL) zum Bearbeiten von Daten.
* Import von Daten in die Campaign-Datenbank.
* Technische Prozesse wie Datenbankbereinigung (Cleanup), Abruf von Tracking-Informationen etc.

:bulb: Erfahren Sie, wie Sie Workflows in [diesem Abschnitt](../config/workflows.md) entwerfen und ausführen.

## Berichte und Analyse {#analysis-and-reporting}

Mit Adobe Campaign können Sie das Verhalten Ihrer Kunden überwachen und interpretieren, indem Sie ihre Daten und Profil schrittweise bereichern. Mit den Tools für Berichte und Analyse können Sie jede neue Kampagne nutzen, Ihre Marketinginitiativen besser Zielgruppe und ihre Wirkung und Rentabilität optimieren.

:bulb:  Weitere Informationen zu Berichts- und Verfolgungsfunktionen finden Sie in [diesem Abschnitt](reporting.md).

## Integration mit Adobe Experience Cloud {#adobe-experience-cloud-integrations}

Sie können die Versand-Funktionen und die Funktionen der erweiterten Kampagnenverwaltung von Adobe Campaign mit einer Reihe von Lösungen kombinieren, mit denen Sie Ihre Benutzererfahrung personalisieren können: Trigger von Adobe Experience Manager, Adobe Analytics, Adobe Target oder Adobe Experience Cloud.

:bulb: Erfahren Sie, wie Sie in [dieser Abschnitt](../connect/integration.md) Adobe-Services und -Lösungen integrieren können.

## Weitere Informationen zu Kampagnen-Funktionen {#core-capabilities-and-add-ons}

Adobe Campaign Angebot eine Reihe von Funktionen, die Sie bei der Implementierung und Optimierung der Marketingfunktionen für Konversationen unterstützen, je nach Ihren Bedürfnissen und Ihrer Architektur. Einige davon sind Kernfunktionen und andere hängen von der Installation eines Pakets auf Ihrer Konfiguration ab. Eine ausführliche Produktbeschreibung finden Sie hier: [Adobe Campaign v8 Produktbeschreibung](https://helpx.adobe.com/de/legal/product-descriptions/adobe-campaign-classic---product-description.html).

:bulb: Sie kennen sich bereits mit Campaign Classic aus? Lernen Sie die wichtigsten Unterschiede zwischen Campaign Classic und Kampagne v8 in [dieser Seite](capability-matrix.md) kennen.

## Arbeitsbereich und Anpassung

Der Arbeitsbereich für Kampagnen ist über die Client-Konsole verfügbar.

:bulb:  Erfahren Sie, wie Sie den Arbeitsbereich &quot;Kampagne&quot;in [diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html) verwenden.

:bulb:  Informationen zum Anpassen von Listen in [diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html)

Sie können auch über das Internet auf einige Funktionen zugreifen.

