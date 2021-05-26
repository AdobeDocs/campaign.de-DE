---
solution: Campaign v8
product: Adobe Campaign
title: Erste Schritte mit Campaign v8
description: Entdecken Sie wichtige Funktionen, die Benutzeroberfläche und globale Richtlinien
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 39%

---

# Erste Schritte mit Adobe Campaign{#gs-ac-v8}

Adobe Campaign bietet eine Plattform für die Konzeption kanalübergreifender Kundenerlebnisse und eine Umgebung für die visuelle Kampagnenorchestrierung, Interaktionsverwaltung in Echtzeit und die kanalübergreifende Ausführung.

Verwenden Sie Campaign für:

* **** Personalisierung und Interaktion durch eine einzige zugängliche Ansicht des Kunden fördern
* **** Integrieren von E-Mail-, Mobile-, Online- und Offline-Kanälen in die Journey
* **** Automatisieren der Bereitstellung aussagekräftiger und zeitnaher Nachrichten und Angebote

![](assets/ac-capabilities.png)

## Integriertes Kundenprofil {#integrated-customer-profile}

Profile werden in einer leistungsstarken Cloud-Datenbank zentralisiert. Die Akquise von Profilen und die Datenbankerstellung können auf verschiedenste Weisen erfolgen: Online-Akquise über Web-Formulare, manueller oder automatisierter Import von Textdateien, Replikation von bereits existierenden Datenbanken oder Informationssystemen des Unternehmens. Mit Adobe Campaign können Sie Marketingverlauf, Kaufinformationen, Voreinstellungen, CRM-Daten und alle relevanten PII-Daten in eine konsolidierte Ansicht integrieren, um sie zu analysieren und Maßnahmen zu ergreifen.

In Adobe Campaign sind Empfänger die Standardprofile, an die Sendungen übermittelt werden (E-Mails, SMS etc.). Dank der in der Datenbank gespeicherten Empfängerdaten können Sie das Ziel filtern, das eine bestimmte Sendung erhält, und Personalisierungsdaten in Ihren Versandinhalten hinzufügen. In der Datenbank sind weitere Profiltypen vorhanden. Sie sind für andere Verwendungszwecke gedacht. Beispielsweise dienen Testprofile zum Testen von Sendungen, bevor sie tatsächlich an das endgültige Ziel übermittelt werden.

[!DNL :bulb:] Die Grundlagen der Profilverwaltung werden in  [diesem Abschnitt](audiences.md) erläutert.

[!DNL :bulb:] In  [diesem Abschnitt](import.md) erfahren Sie, wie Sie Campaign Profile hinzufügen.

## Zielgruppensegmentierung {#targeted-segmentation}

Adobe Campaign enthält leistungsstarke Analyse- und Zielgruppenbestimmungsfunktionen, die es Ihnen ermöglichen, sehr spezifische, dem Kundenprofil entsprechende Angebote zu erstellen. Dank der deskriptiven Analysefunktionen können Sie Informationen vor und nach Ihren Marketing-Kampagnen detailliert betrachten. Außerdem ermöglichen Filter und ein benutzerfreundliches Abfragetool, registrierte Kontakte mithilfe unzähliger Kriterien zu kategorisieren und extrem genaue Zielgruppen zu definieren.

Die erweiterte Data-Management-Funktion erweitert die Datenverarbeitungsfunktionen. Sie vereinfacht und optimiert den Targeting-Prozess, indem nicht modellierte Daten in den Datamart aufgenommen werden.

[!DNL :bulb:] Weitere Informationen zur Segmentierung, zur Erstellung und Personalisierung von Zielgruppen finden Sie in  [diesem Abschnitt](audiences.md).

## Kanalübergreifende Orchestrierung einer Kampagne {#cross-channel-campaign-orchestration}

Mit Adobe Campaign können Sie zielgerichtete und personalisierte Kampagnen auf mehreren Kanälen entwerfen und organisieren: E-Mail, Briefpost, SMS, Push-Benachrichtigung. Über eine einzige Oberfläche erhalten Sie alle Funktionen, die zum Planen, Orchestrieren, Konfigurieren, Personalisieren, Automatisieren, Ausführen und Messen all Ihrer Kampagnen und Kommunikationen erforderlich sind.

[!DNL :bulb:] In  [diesem Abschnitt](campaigns.md) erfahren Sie, wie Sie eine Kampagne entwerfen, planen und ausführen.

## Workflows

Adobe Campaign bietet eine umfassende grafische Oberfläche, die den Entwurf komplexer Arbeitsabläufe ermöglicht. Diese umfassen die Segmentierung von Zielgruppen, die Ausführung von Kampagnen, die Verarbeitung von Dateien usw. Erstellen Sie zum Beispiel einen Workflow, um eine Datei von einem Server herunterzuladen, sie zu entkomprimieren und die Datensätze in die Adobe-Campaign-Datenbank zu importieren.

Oder fordern Sie andere Benutzer auf, Aufgaben auszuführen oder zu validieren. Auf diese Weise ist es möglich, anderen Benutzern Aufgaben wie Inhaltsgestaltung, Zielgruppenbestimmung und Validierung von Testsendungen zuzuweisen, bevor eine Nachricht an die Empfänger verschickt wird.

Workflows können in unterschiedlichsten Kontexten zum Einsatz kommen:

* Zielgruppenbestimmung für Audiences oder zum Versand von Nachrichten.
* Daten-Management (ETL) zum Bearbeiten von Daten.
* Import von Daten in die Campaign-Datenbank.
* Technische Prozesse wie Datenbankbereinigung (Cleanup), Abruf von Tracking-Informationen etc.

[!DNL :bulb:] In  [diesem Abschnitt](../config/workflows.md) erfahren Sie, wie Sie Workflows entwerfen und ausführen.

## Berichterstellung und Analyse {#analysis-and-reporting}

Mit Adobe Campaign können Sie das Verhalten Ihrer Kunden überwachen und interpretieren, indem Sie deren Daten und Profile schrittweise anreichern. Mit den Berichts- und Analysewerkzeugen können Sie aus jeder neuen Kampagne Kapital schlagen, Ihre Marketinginitiativen besser ansprechen und deren Wirkung und ROI optimieren.

[!DNL :bulb:] Weitere Informationen zu Berichts- und Tracking-Funktionen finden Sie in  [diesem Abschnitt](reporting.md).

## Integration mit Adobe Experience Cloud {#adobe-experience-cloud-integrations}

Sie können die Versandfunktionen und erweiterten Kampagnenverwaltungsfunktionen von Adobe Campaign mit einer Reihe von Lösungen kombinieren, die Ihnen helfen, das Benutzererlebnis zu personalisieren: z. B. Adobe Experience Manager, Adobe Analytics, Adobe Target oder Adobe Experience Cloud-Trigger.

[!DNL :bulb:] Informationen zur Integration mit Adobe-Diensten und -Lösungen finden Sie in  [diesem Abschnitt](../connect/integration.md).

## Weitere Informationen zu Campaign-Funktionen {#core-capabilities-and-add-ons}

Adobe Campaign bietet eine Reihe von Funktionen, mit denen Sie die kommunikativen Marketing-Funktionen je nach Ihren Anforderungen und Ihrer Architektur implementieren und optimieren können. Einige davon sind Kernfunktionen und andere hängen von der Installation eines Pakets von Ihrer Konfiguration ab. Eine ausführliche Produktbeschreibung finden Sie hier: [Adobe Campaign v8 Produktbeschreibung](https://helpx.adobe.com/de/legal/product-descriptions/adobe-campaign-classic---product-description.html).

[!DNL :bulb:] Bereits mit Campaign Classic vertraut? Lernen Sie die wichtigsten Unterschiede zwischen Campaign Classic und Campaign v8 in [dieser Seite](capability-matrix.md) kennen.

## Arbeitsbereich und Anpassung

Der Campaign-Arbeitsbereich ist über [Client Console](../dev/general-architecture.md) verfügbar.

[!DNL :bulb:] [Erfahren Sie mehr über die Campaign Client Console](../start/connect.md).

Der Campaign-Arbeitsbereich kann Ihren Bedürfnissen entsprechend angepasst werden.

[!DNL :arrow_upper_right:]  Erfahren Sie, wie Sie Campaign Workspace in der Dokumentation zu  [Campaign Classic v7 verwenden.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html)

[!DNL :arrow_upper_right:]  Erfahren Sie, wie Sie Listen in der Dokumentation zu  [Campaign Classic v7 anpassen können.](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html)

Sie können auch über das Internet auf einige Funktionen zugreifen.

[!DNL :bulb:] [Erfahren Sie mehr über den Campaign-Webzugriff](../start/connect.md#web-access).


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

