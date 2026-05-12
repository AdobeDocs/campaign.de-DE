---
title: Erste Schritte mit Profilen und Zielgruppen in Campaign
description: Erfahren Sie, wie Sie in Campaign Profile und Zielgruppen erstellen und verwalten.
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
version: Campaign v8, Campaign Classic v7
TQID: https://experienceleague.adobe.com/rk1-Q8Ghg8L8jSqGNvTRYY0alwUry6l8lPv-GROTfFQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 346
ht-degree: 100%

---

# Erste Schritte mit Profilen und Zielgruppen{#gs-profiles-and-audiences}

Profile sind in der Campaign-Datenbank gespeicherte Kontakte, z. B. Kunden, Abonnenten eines Services oder potenzielle Kunden. Die Akquise von Profilen und die Datenbankerstellung können auf viele verschiedene Weisen erfolgen: Online-Akquise über Web-Formulare, manueller oder automatisierter Import von Textdateien, Replikation von bereits existierenden Datenbanken oder Informationssystemen des Unternehmens. Mit Adobe Campaign können Sie Marketing-Verlauf, Kaufinformationen, Voreinstellungen, CRM-Daten und alle relevanten PI-Daten in eine konsolidierte Ansicht integrieren, um sie zu analysieren und Maßnahmen zu ergreifen. Profile enthalten alle Informationen, die für Zielgruppenbestimmung, Qualifizierung und Tracking von Personen erforderlich sind.

Ein Profil ist ein Datensatz in der Tabelle **nmsRecipient** oder einer externen Tabelle, in der alle Profilattribute wie Vorname, Nachname, E-Mail-Adresse, Cookie-ID, Kunden-ID, Mobilgerät-Kennung oder andere für einen bestimmten Kanal relevante Informationen gespeichert werden. Andere mit der Empfängertabelle verknüpfte Tabellen enthalten profilbezogene Daten, z. B. die Tabelle &quot;Versand-Logs&quot;, die die Datensätze aller an Empfänger gesendeten Sendungen enthält. Weitere Informationen zu den in Campaign integrierten Profil- und Empfängertabellen finden Sie in [diesem Abschnitt](../dev/datamodel.md#ootb-profiles).

![](assets/recipients-in-explorer.png)

In Adobe Campaign sind die Standardprofile für Sendungen (E-Mails, SMS usw.) die **Empfänger**.

Mit den in der Datenbank gespeicherten Empfängerdaten können Sie die Zielgruppe filtern, die einen bestimmten Versand erhalten soll, und Personalisierungsdaten in den Versandinhalt einfügen. In der Datenbank gibt es noch andere Arten von Profilen. Sie sind für unterschiedliche Zwecke gedacht. So werden beispielsweise Testprofile erstellt, um Ihre Sendungen zu testen, bevor sie an die endgültige Zielgruppe gesendet werden.

Um Profildaten zu Adobe Campaign hinzuzufügen, haben Sie folgende Möglichkeiten:

* [Importieren von Datendateien](../start/import.md) aus einer externen Datenquelle, z. B. einem CRM-System oder einer flachen Datei
* [Erstellen von Web-Formularen](../dev/webapps.md), damit Kunden selbst Informationen eingeben und ihr eigenes Profil erstellen können
* [Zuordnen zu einer externen Datenbank](../connect/fda.md), in der Profile gespeichert werden
* Manuelles Eingeben von Profilen über die Client-Konsole, wie unten beschrieben:

![](assets/create-profile.png)

Nach dem Import können Sie Zielgruppen erstellen, um Ihre Nachrichten zu versenden. [In diesem Abschnitt](create-audiences.md) erfahren Sie, wie Sie Zielgruppen erstellen.