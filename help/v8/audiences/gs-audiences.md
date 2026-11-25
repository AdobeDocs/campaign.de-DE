---
title: Erste Schritte mit Profilen und Zielgruppen in Campaign
description: Erfahren Sie, wie Sie in Campaign Profile und Zielgruppen erstellen und verwalten.
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
version: Campaign v8, Campaign Classic v7
TQID: 'https://experienceleague.adobe.com/rk1-Q8Ghg8L8jSqGNvTRYY0alwUry6l8lPv-GROTfFQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bf608c313c238d3ba16f9fe6902bb66bb2b90d98
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 80%
---
# Erste Schritte mit Profilen und Zielgruppen{#gs-profiles-and-audiences}

Profile sind in der Campaign-Datenbank gespeicherte Kontakte, z. B. Kunden, Abonnenten eines Services oder potenzielle Kunden. Die Akquise von Profilen und die Datenbankerstellung können auf viele verschiedene Weisen erfolgen: Online-Akquise über Web-Formulare, manueller oder automatisierter Import von Textdateien, Replikation von bereits existierenden Datenbanken oder Informationssystemen des Unternehmens. Mit Adobe Campaign können Sie Marketing-Verlauf, Kaufinformationen, Voreinstellungen, CRM-Daten und alle relevanten PI-Daten in eine konsolidierte Ansicht integrieren, um sie zu analysieren und Maßnahmen zu ergreifen. Profile enthalten alle Informationen, die für Zielgruppenbestimmung, Qualifizierung und Tracking von Personen erforderlich sind.

Ein Profil ist ein Datensatz in der Tabelle **nmsRecipient** oder einer externen Tabelle, in der alle Profilattribute wie Vorname, Nachname, E-Mail-Adresse, Cookie-ID, Kunden-ID, Mobilgerät-Kennung oder andere für einen bestimmten Kanal relevante Informationen gespeichert werden. Andere mit der Empfängertabelle verknüpfte Tabellen enthalten profilbezogene Daten, z. B. die Tabelle &quot;Versand-Logs&quot;, die die Datensätze aller an Empfänger gesendeten Sendungen enthält. Weitere Informationen über integrierte Profile und Empfängertabellen finden Sie unter [Integrierte Profiltabelle](../dev/datamodel.md#ootb-profiles).

![Explorer-Struktur mit ausgewähltem Knoten „Empfänger“, in der Profile und Details des ausgewählten Empfängers aufgelistet sind.](assets/recipients-in-explorer.png)

In Adobe Campaign sind die Standardprofile für Sendungen (E-Mails, SMS usw.) die **Empfänger**.

Die in der Datenbank gespeicherten Empfängerdaten ermöglichen es Ihnen, die Zielgruppe zu filtern, die einen bestimmten Versand erhält, und Personalisierungsdaten in Ihren Versandinhalten hinzuzufügen. In der Datenbank gibt es noch andere Arten von Profilen. Sie sind für unterschiedliche Zwecke gedacht. So werden beispielsweise Testprofile erstellt, um Ihre Sendungen zu testen, bevor sie an die endgültige Zielgruppe gesendet werden.

Um Profildaten zu Adobe Campaign hinzuzufügen, haben Sie folgende Möglichkeiten:

* [Importieren von Datendateien](../start/import.md) aus einer externen Datenquelle, z. B. einem CRM-System oder einer flachen Datei
* [Erstellen von Web-Formularen](../dev/webapps.md), damit Kunden selbst Informationen eingeben und ihr eigenes Profil erstellen können
* [Zuordnen zu einer externen Datenbank](../connect/fda.md), in der Profile gespeichert werden
* Manuelles Eingeben von Profilen über die Client-Konsole, wie unten beschrieben:

![Dialogfeld „Neuer Empfänger“ von Erstellen auf der Seite „Empfänger“ mit allgemeinen Feldern wie Vorname und E-Mail geöffnet.](assets/create-profile.png)

Nach dem Import können Sie Zielgruppen erstellen, um Ihre Nachrichten zu versenden. [In diesem Abschnitt](create-audiences.md) erfahren Sie, wie Sie Zielgruppen erstellen.