---
product: Adobe Campaign
title: Erste Schritte mit Campaign v8
description: Entdecken Sie wichtige Funktionen, die Benutzeroberfläche und globale Richtlinien
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 88%

---

# Erste Schritte mit Adobe Campaign{#gs-ac-v8}

Adobe Campaign bietet eine Plattform für die Konzeption kanalübergreifender Kundenerlebnisse, auf der über eine visuell-gestützte Umgebung Kampagnen orchestriert, Interaktionen in Echtzeit verwaltet und Kampagnen kanalübergreifend ausgeführt werden können.

Mit Campaign können Sie:

* **Personalisierung und Interaktion mit der Hilfe einer umfassenden, zentralen Sicht auf den Kunden fördern**
* **E-Mail-, Mobil-, Online- und Offline-Kanälen in die Customer Journey integrieren**
* **Zielführende, zeitlich optimal abgestimmte Nachrichten und Angebote automatisch versenden**

![](assets/ac-capabilities.png)

## Integriertes Kundenprofil {#integrated-customer-profile}

Profile werden in einer funktionsstarken Cloud-Datenbank zentralisiert. Die Akquise von Profilen und die Datenbankerstellung können auf verschiedenste Weisen erfolgen: Online-Akquise über Web-Formulare, manueller oder automatisierter Import von Textdateien, Replikation von bereits existierenden Datenbanken oder Informationssystemen des Unternehmens. Mit Adobe Campaign können Sie Marketing-Verlauf, Kaufinformationen, Voreinstellungen, CRM-Daten und alle relevanten PII-Daten in eine konsolidierte Ansicht integrieren, um sie zu analysieren und Maßnahmen zu ergreifen.

In Adobe Campaign sind Empfänger die Standardprofile, an die Sendungen übermittelt werden (E-Mails, SMS usw.). Dank der in der Datenbank gespeicherten Empfängerdaten können Sie die Zielgruppe filtern, die eine bestimmte Sendung erhält, und Personalisierungsdaten in Ihren Versandinhalten hinzufügen. In der Datenbank sind weitere Profiltypen vorhanden. Sie sind für andere Verwendungszwecke gedacht. Beispielsweise dienen Testprofile zum Testen von Sendungen, bevor sie tatsächlich an das endgültige Ziel übermittelt werden.

[!DNL :bulb:] Die Grundlagen zur Verwaltung von Profilen werden in [diesem Abschnitt](audiences.md) erläutert.

[!DNL :bulb:] In  [diesem Abschnitt](import.md) erfahren Sie, wie Sie Campaign Profile hinzufügen.

## Zielgruppensegmentierung {#targeted-segmentation}

Adobe Campaign enthält leistungsstarke Analyse- und Zielgruppenbestimmungsfunktionen, die es Ihnen ermöglichen, sehr spezifische, dem Kundenprofil entsprechende Angebote zu erstellen. Dank der deskriptiven Analysefunktionen können Sie Informationen vor und nach Ihren Marketing-Kampagnen detailliert betrachten. Außerdem ermöglichen es Filter und ein benutzerfreundliches Abfrage-Tool, registrierte Kontakte mithilfe unzähliger Kriterien zu kategorisieren und extrem genaue Zielgruppen zu definieren.

Fortschrittliche Funktionen für das Daten-Management erweitern die Datenverarbeitungskapazitäten. Sie vereinfachen und optimieren den Zielgruppenbestimmungsprozess, indem sie nicht modellierte Daten in den Datamart einschließen.

[!DNL :bulb:] Weitere Informationen zur Segmentierung, Erstellung und Personalisierung von Audiences finden Sie in [diesem Abschnitt](audiences.md).

## Kanalübergreifende Orchestrierung einer Kampagne {#cross-channel-campaign-orchestration}

Adobe Campaign unterstützt Sie bei der Konzeption und Orchestrierung von zielgerichteten und personalisierten Kampagnen auf verschiedenen Kanälen: E-Mail, Briefpost, SMS und Push-Benachrichtigung. Über nur eine Oberfläche können Sie all Ihre Kampagnen und Kommunikationen planen, orchestrieren, konfigurieren, personalisieren, automatisieren, ausführen und messen.

[!DNL :bulb:] Näheres dazu, wie Sie eine Kampagne planen und ausführen, finden Sie in [diesem Abschnitt](campaigns.md).

## Workflows

Adobe Campaign bietet eine umfassende grafische Oberfläche, die den Entwurf komplexer Arbeitsabläufe ermöglicht. Diese umfassen die Segmentierung von Zielgruppen, die Ausführung von Kampagnen, die Verarbeitung von Dateien usw. Erstellen Sie zum Beispiel einen Workflow, um eine Datei von einem Server herunterzuladen, sie zu entkomprimieren und die Datensätze in die Adobe Campaign-Datenbank zu importieren.

Oder fordern Sie andere Benutzer auf, Aufgaben auszuführen oder zu validieren. Auf diese Weise ist es möglich, anderen Benutzern Aufgaben wie Inhaltsgestaltung, Zielgruppenbestimmung und Validierung von Testsendungen zuzuweisen, bevor eine Nachricht an die Empfänger verschickt wird.

Workflows können in unterschiedlichsten Kontexten zum Einsatz kommen:

* Zielgruppenbestimmung für Audiences oder zum Versand von Nachrichten.
* Daten-Management (ETL) zum Bearbeiten von Daten.
* Import von Daten in die Campaign-Datenbank.
* Technische Prozesse wie Datenbankbereinigung (Cleanup), Abruf von Tracking-Informationen etc.

[!DNL :bulb:] Näheres dazu, wie Sie Workflows erstellen und ausführen, finden Sie in [diesem Abschnitt](../config/workflows.md).

## Reporting und Analysen {#analysis-and-reporting}

Adobe Campaign ermöglicht es Ihnen, das Verhalten Ihrer Kunden zu verfolgen und besser zu verstehen, indem Sie Daten und Profile kontinuierlich anreichern. Dank der Reporting- und Analyse-Tools trägt jede neue Kampagne zur Optimierung Ihrer Datenbestände bei. Marketing-Maßnahmen können besser auf die jeweiligen Zielgruppen abgestimmt werden und Wirksamkeit sowie ROI werden gesteigert.

[!DNL :bulb:] Weitere Informationen zu Berichts- und Tracking-Funktionen finden Sie in  [diesem Abschnitt](reporting.md).

## Integration mit Adobe Experience Cloud {#adobe-experience-cloud-integrations}

Sie können die Funktionen für Versand und erweiterte Kampagnenverwaltung von Adobe Campaign mit einer Reihe von Lösungen kombinieren, anhand derer Sie das Benutzererlebnis personalisieren können, darunter z. B. Adobe Experience Manager, Adobe Analytics, Adobe Target oder Adobe Experience Cloud Triggers.

[!DNL :bulb:] Näheres dazu, wie Sie Adobe-Services und -Lösungen integrieren können, finden Sie in [diesem Abschnitt](../connect/integration.md).

## Weitere Informationen zu den Funktionen von Campaign {#core-capabilities-and-add-ons}

Adobe Campaign bietet verschiedenste Funktionen, die eine Ihren Bedürfnissen und Ihrer Architektur entsprechende Implementierung und Optimierung von dialogorientiertem Marketing ermöglichen. Einige davon sind Kernfunktionen, andere wiederum erfordern die Installation eines Package in Ihrer Konfiguration. Eine ausführliche Produktbeschreibung finden Sie hier: [Produktbeschreibung zu Adobe Campaign v8](https://helpx.adobe.com/de/legal/product-descriptions/adobe-campaign-classic---product-description.html)

[!DNL :bulb:] Sie sind bereits vertraut mit Campaign Classic? Eine Erläuterung der wichtigsten Unterschiede zwischen Campaign Classic und Campaign v8 finden Sie auf [dieser Seite](capability-matrix.md).

## Arbeitsbereich und Anpassung

Der Campaign-Arbeitsbereich ist über [Client Console](../dev/general-architecture.md) verfügbar.

[!DNL :bulb:] [Erfahren Sie mehr über die Campaign-Client-Konsole](../start/connect.md).

Der Campaign-Arbeitsbereich kann Ihren Bedürfnissen entsprechend angepasst werden.

[!DNL :arrow_upper_right:]  Erfahren Sie, wie Sie Campaign Workspace in der Dokumentation zu  [Campaign Classic v7 verwenden.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=de)

[!DNL :arrow_upper_right:]  Erfahren Sie, wie Sie Listen in der Dokumentation zu  [Campaign Classic v7 anpassen können.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=de#getting-started)

Auf einige der Funktionen können Sie zudem über einen Webbrowser zugreifen.

[!DNL :bulb:] [Erfahren Sie mehr über den Web-basierten Zugriff auf Campaign](../start/connect.md#web-access).


## Sprachen

Die Benutzeroberfläche von Campaign v8 ist in den folgenden Sprachen verfügbar:

* Englisch (UK)
* Englisch (US)
* Französisch
* Deutsch
* Japanisch

Die Sprache wird während des Installationsprozesses ausgewählt.

>[!CAUTION]
>
>Die Sprache kann nach der Instanzerstellung nicht mehr geändert werden.

Von der Sprache betroffene Daten und Uhrzeitformate. Weitere Informationen hierzu finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#date-and-time).

