---
solution: Campaign v8
product: Adobe Campaign
title: Erste Schritte mit Audiences
description: Erste Schritte mit Audiences
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 345d324363782df6f7753d5099c4382628f5a048
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 57%

---

# Erste Schritte mit Audiences{#gs-ac-audiences}

## Mit Profilen arbeiten{#gs-ac-profiles}

Profile sind in der Campaign-Datenbank gespeicherte Kontakte, einschließlich Kunden, Abonnenten und Interessenten. Die Akquise von Profilen und die Datenbankerstellung können auf verschiedenste Weisen erfolgen: Online-Akquise über Web-Formulare, manueller oder automatisierter Import von Textdateien, Replikation von bereits existierenden Datenbanken oder Informationssystemen des Unternehmens. Mit Adobe Campaign können Sie Marketing-Verlauf, Kaufinformationen, Voreinstellungen, CRM-Daten und alle relevanten PI-Daten in eine konsolidierte Ansicht integrieren, um sie zu analysieren und Maßnahmen zu ergreifen. Profile enthalten alle Informationen, die für die Zielgruppenbestimmung, Qualifizierung und Verfolgung von Personen erforderlich sind.

Ein Profil ist ein Datensatz in der Tabelle **nmsRecipient** oder einer externen Tabelle, in der alle Profilattribute wie Vorname, Nachname, E-Mail-Adresse, Cookie-ID, Kunden-ID, Mobiltelefonkennung oder andere für einen bestimmten Kanal relevante Informationen gespeichert werden. Andere mit der Empfängertabelle verknüpfte Tabellen enthalten profilbezogene Daten, z. B. die Tabelle Versandlogs , die die Datensätze aller an Empfänger gesendeten Sendungen enthält. Weitere Informationen zu den in Campaign integrierten Profil- und Empfängertabellen finden Sie in [diesem Abschnitt](../dev/datamodel.md#ootb-profiles).

In Adobe Campaign sind **Empfänger** die Standardprofile, die für den Versand von Nachrichten angesprochen werden (E-Mails, SMS usw.). Mit den in der Datenbank gespeicherten Empfängerdaten können Sie die Zielgruppe filtern, die einen bestimmten Versand erhalten soll, und Personalisierungsdaten in den Versandinhalt einfügen. In der Datenbank gibt es noch andere Arten von Profilen. Sie sind für unterschiedliche Zwecke gedacht. So werden beispielsweise Testprofile erstellt, um Ihre Sendungen zu testen, bevor sie an die endgültige Zielgruppe gesendet werden.

Profile können in Listen gruppiert oder mittels Datenbankabfrage erfasst werden.


Um Campaign mit Profildaten zu füllen, können Sie:

* [Importieren von ](import.md) Datendateien aus einer externen Datenquelle, z. B. einem CRM-System
* [Webformate erstellen, ](../dev/webapps.md) damit Kunden eigene Informationen eingeben und ihr eigenes Profil erstellen können
* [einer externen ](../connect/fda.md) Datenbank zuordnen, in der Profile gespeichert werden
* Geben Sie Profile manuell über die Client-Konsole ein, wie unten dargestellt:

![](assets/create-profile.png)


[!DNL :arrow_upper_right:] Informationen zum Verwalten von Profilen finden Sie in der  [Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html?lang=de#getting-started) zu Adobe Campaign Classic v7.


## Datenschutz und Einverständniserklärung

Adobe Campaign ist ein leistungsstarkes Tool zur Erfassung und Verarbeitung großer Datenmengen, einschließlich personenbezogener Daten und sensibler Daten. Mit Adobe Campaign können Sie Daten, einschließlich personenbezogener und vertraulicher Daten, erfassen. Es ist daher unerlässlich, dass Sie das Einverständnis Ihrer Empfänger erhalten und überwachen.

[!DNL :arrow_upper_right:] Erfahren Sie, wie Sie Datenschutz und Einverständniserklärung in der  [Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html) zu Adobe Campaign Classic v7 verwalten.

## Erstellen von Listen

Eine Liste ist eine statische Gruppe von Profilen, die als Zielgruppe für Sendungen verwendet oder durch Importe sowie Workflows aktualisiert werden kann. So kann beispielsweise eine mithilfe einer Abfrage aus der Datenbank gefilterte Population in einer Liste gespeichert werden.

[!DNL :arrow_upper_right:] Erfahren Sie, wie Sie Listen in der  [Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html) zu Adobe Campaign Classic v7 erstellen und verwalten.

## Abfrage der Datenbank

Verwenden Sie die Aktivität **Abfrage** in einem Workflow, um Datenbankabfragen auszuführen, Daten zu segmentieren und komplexe Audiences zu erstellen.

[!DNL :arrow_upper_right:] Weitere Informationen zu Campaign-Abfragen finden Sie in der  [Dokumentation zu Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html?lang=de#automating-with-workflows).

[!DNL :arrow_upper_right:] Alle Targeting-Aktivitäten werden in der Dokumentation zu  [Adobe Campaign Classic v7 aufgeführt](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html?lang=de)

## Eine Audience in einem Workflow erstellen

Zielgruppenbestimmung kann über eine Kombination von Abfragen in einer grafischen Abfolge in einem Workflow erstellt werden. Sie können Audiences erstellen und deren Targeting entsprechend Ihren Anforderungen anpassen. Um den Workflow-Editor anzuzeigen, klicken Sie im Campaign-Dashboard auf die Registerkarte **[!UICONTROL Zielgruppenbestimmung und Workflows]**.

[!DNL :arrow_upper_right:] Informationen zum Erstellen einer Zielgruppe in einem Kampagnen-Workflow in der Dokumentation zu  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=de#building-the-main-target-in-a-workflow)


## Aktive Profile{#active-profiles}

Gemäß Ihrem Vertrag erhalten alle Ihre Campaign-Instanzen eine bestimmte Anzahl aktiver Profile, die zu Abrechnungszwecken gezählt werden. Informationen zur Anzahl der gekauften aktiven Profile finden Sie in Ihrem aktuellen Vertrag.

**** Profil bezeichnet einen Datensatz mit Informationen (z. B.: einen Datensatz in der  [Empfängertabelle ](../dev/datamodel.md) oder eine externe Tabelle, die eine Cookie-ID, Kunden-ID, mobile Kennung oder andere für einen bestimmten Kanal relevante Informationen enthält), der einen Endkunden, einen Interessenten oder einen Lead darstellt. Profile gelten als aktiv, wenn sie in den letzten 12 Monaten über einen beliebigen Kanal angesprochen wurden oder über einen beliebigen Kanal mit ihnen kommuniziert wurde.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

[!DNL :arrow_upper_right:] For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

**Verwandte Themen**

[!DNL :arrow_upper_right:] [Kampagnenspezifische Workflows erstellen und ausführen](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=de#automating-with-workflows)

[!DNL :arrow_upper_right:] [Erfahren Sie, wie Sie die Audience einer Kampagne auswählen](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=de#orchestrating-campaigns)

[!DNL :arrow_upper_right:] [Erste Schritte mit Workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=de)
