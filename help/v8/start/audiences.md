---
title: Erste Schritte mit Audiences
description: Erste Schritte mit Audiences
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 780a29dab99ad2bda554134ca95c435b9e76b494
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 100%

---

# Erste Schritte mit Audiences{#gs-ac-audiences}

## Arbeiten mit Profilen {#gs-ac-profiles}

Profile sind in der Campaign-Datenbank gespeicherte Kontakte, einschließlich Kunden, Abonnenten und Interessenten. Die Akquise von Profilen und die Datenbankerstellung können auf verschiedenste Weisen erfolgen: Online-Akquise über Web-Formulare, manueller oder automatisierter Import von Textdateien, Replikation von bereits existierenden Datenbanken oder Informationssystemen des Unternehmens. Mit Adobe Campaign können Sie Marketing-Verlauf, Kaufinformationen, Voreinstellungen, CRM-Daten und alle relevanten PI-Daten in eine konsolidierte Ansicht integrieren, um sie zu analysieren und Maßnahmen zu ergreifen. Profile enthalten alle Informationen, die für Zielgruppenbestimmung, Qualifizierung und Tracking von Personen erforderlich sind.

Ein Profil ist ein Datensatz in der Tabelle **nmsRecipient** oder einer externen Tabelle, in der alle Profilattribute wie Vorname, Nachname, E-Mail-Adresse, Cookie-ID, Kunden-ID, Smartphone-Kennung oder andere für einen bestimmten Kanal relevante Informationen gespeichert werden. Andere mit der Empfängertabelle verknüpfte Tabellen enthalten profilbezogene Daten, z. B. die Tabelle &quot;Versand-Logs&quot;, die die Datensätze aller an Empfänger gesendeten Sendungen enthält. Weitere Informationen zu den in Campaign integrierten Profil- und Empfängertabellen finden Sie in [diesem Abschnitt](../dev/datamodel.md#ootb-profiles).

In Adobe Campaign sind die Standardprofile für Sendungen (E-Mails, SMS usw.) die **Empfänger**. Mit den in der Datenbank gespeicherten Empfängerdaten können Sie die Zielgruppe filtern, die einen bestimmten Versand erhalten soll, und Personalisierungsdaten in den Versandinhalt einfügen. In der Datenbank gibt es noch andere Arten von Profilen. Sie sind für unterschiedliche Zwecke gedacht. So werden beispielsweise Testprofile erstellt, um Ihre Sendungen zu testen, bevor sie an die endgültige Zielgruppe gesendet werden.

Profile können in Listen gruppiert oder mittels Datenbankabfrage erfasst werden.


Um Profildaten für Campaign bereitzustellen, haben Sie folgende Möglichkeiten:

* [Importieren von Datendateien](import.md) aus einer externen Datenquelle, z. B. einem CRM-System
* [Erstellen von Web-Formularen](../dev/webapps.md), damit Kunden selbst Informationen eingeben und ihr eigenes Profil erstellen können
* [Zuordnen zu einer externen Datenbank](../connect/fda.md), in der Profile gespeichert werden
* Geben Sie Profile wie unten beschrieben manuell über die Client-Konsole ein:

![](assets/create-profile.png)


![](../assets/do-not-localize/book.png) Weitere Informationen zum Verwalten von Profilen finden Sie in der [Dokumentation zu Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html?lang=de){target=&quot;_blank&quot;}.


## Datenschutz und Einverständniserklärung

Adobe Campaign ist ein leistungsstarkes Tool zur Erfassung und Verarbeitung von großen Datenmengen, einschließlich personenbezogener Daten und vertraulicher Informationen. Mit Adobe Campaign können Sie Daten, einschließlich personenbezogener und vertraulicher Daten, erfassen. Es ist daher unerlässlich, dass Sie das Einverständnis Ihrer Empfänger erhalten und überwachen.

![](../assets/do-not-localize/book.png) Wie Sie Datenschutz und Einverständnis gewährleisten, erfahren Sie in der [Dokumentation zu Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=de){target=&quot;_blank&quot;}.

## Erstellen von Listen

Eine Liste ist eine statische Gruppe von Profilen, die als Zielgruppe für Sendungen verwendet oder durch Importe sowie Workflows aktualisiert werden kann. So kann beispielsweise eine mithilfe einer Abfrage aus der Datenbank gefilterte Population in einer Liste gespeichert werden.

![](../assets/do-not-localize/book.png) Wie Sie Listen erstellen und verwalten, erfahren Sie in der [Dokumentation zu Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html?lang=de){target=&quot;_blank&quot;}.

## Abfrage der Datenbank

Verwenden Sie die Aktivität **Abfrage** in einem Workflow, um Datenbankabfragen auszuführen, Daten zu segmentieren und komplexe Audiences zu erstellen.

![](../assets/do-not-localize/book.png) Weitere Informationen zu Campaign-Abfragen finden Sie in der [Dokumentation zu Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html?lang=de#automating-with-workflows){target=&quot;_blank&quot;}.

![](../assets/do-not-localize/book.png) Alle Zielgruppenbestimmungsaktivitäten werden in der [Dokumentation zu Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html?lang=de){target=&quot;_blank&quot;} aufgeführt.

## Eine Audience in einem Workflow erstellen

Zielgruppenbestimmung kann über eine Kombination von Abfragen in einer grafischen Abfolge in einem Workflow erstellt werden. Sie können Audiences erstellen und deren Targeting entsprechend Ihren Anforderungen anpassen. Um den Workflow-Editor anzuzeigen, klicken Sie im Campaign-Dashboard auf die Registerkarte **[!UICONTROL Zielgruppenbestimmung und Workflows]**.

![](../assets/do-not-localize/book.png) Weitere Informationen zur Erstellung einer Audience in einem Kampagnen-Workflow erhalten Sie in der [Dokumentation zu Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=de#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;}.


## Aktive Profile{#active-profiles}

Gemäß Ihrem Vertrag erhalten alle Ihre Campaign-Instanzen eine bestimmte Anzahl aktiver Profile, die zu Abrechnungszwecken gezählt werden. Informationen zur Anzahl der gekauften aktiven Profile finden Sie in Ihrem aktuellen Vertrag.

**Profil** bezeichnet einen Datensatz, der einen Endkunden, einen Interessenten oder Lead repräsentiert. Bei diesen Daten kann es sich etwa um einen Datensatz in der [Empfängertabelle](../dev/datamodel.md) oder einer externen Tabelle handeln, die die Kennung eines Cookies, eines Kunden oder eines Mobile-Kanals oder andere für einen bestimmten Kanal relevante Informationen enthält. Profile gelten als aktiv, wenn sie in den letzten 12 Monaten über einen beliebigen Kanal angesprochen wurden oder über einen beliebigen Kanal mit ihnen kommuniziert wurde.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

**Verwandte Themen**   in der Dokumentation zu Campaign Classic v7:

* [Kampagnenspezifische Workflows entwerfen und ausführen](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=de#automating-with-workflows){target=&quot;_blank&quot;}

* [Zielgruppe einer Kampagne auswählen](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=de){target=&quot;_blank&quot;}

* [Erste Schritte mit Workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=de){target=&quot;_blank&quot;}
