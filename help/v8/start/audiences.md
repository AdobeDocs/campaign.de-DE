---
title: Arbeiten mit Audiences in Campaign
description: Arbeiten mit Audiences in Campaign
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 100%

---

# Arbeiten mit Audiences in Campaign{#gs-ac-audiences}

Profile sind in der Campaign-Datenbank gespeicherte Kontakte.

In Adobe Campaign sind die Standardprofile für Sendungen (E-Mails, SMS usw.) die **Empfänger**. Mit den in der Datenbank gespeicherten Empfängerdaten können Sie die Zielgruppe filtern, die einen bestimmten Versand erhalten soll, und Personalisierungsdaten in den Versandinhalt einfügen. In der Datenbank gibt es noch andere Arten von Profilen. Sie sind für unterschiedliche Zwecke gedacht. So werden beispielsweise Testprofile erstellt, um Ihre Sendungen zu testen, bevor sie an die endgültige Zielgruppe gesendet werden.

[In diesem Abschnitt](../audiences/gs-audiences.md) erfahren Sie, wie Sie Profile und Audiences importieren, aktualisieren und verwalten.

## Erstellen von Listen{#create-lists}

Eine Liste ist ein statischer Satz von Kontakten, die in Versandaktionen als Zielkontakte dienen oder beim Importieren bzw. bei einer Workflow-Ausführung aktualisiert werden können. So kann beispielsweise eine Population, die über eine Abfrage aus der Datenbank extrahiert wurde, als Liste gespeichert werden.

![](../assets/do-not-localize/glass.png) Näheres dazu, wie Sie Listen erstellen und verwalten, finden Sie auf [dieser Seite](../audiences/create-audiences.md).

## Filtern der Datenbank{#filter-the-database}

Die Filterkonfiguration ermöglicht die **[!UICONTROL dynamische]** Auswahl von Daten aus einer Liste. Bei Änderung der Daten werden die gefilterten Daten aktualisiert. Sie können eigene Filter erstellen oder die integrierten Filter verwenden, um eine Audience zu definieren.

![](../assets/do-not-localize/glass.png) Weitere Informationen dazu, wie Sie Filter erstellen und verwalten, finden Sie auf [dieser Seite](../audiences/create-filters.md).

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

## Datenschutz und Einverständniserklärung{#privacy-and-consent}

Adobe Campaign ist ein leistungsstarkes Tool zur Erfassung und Verarbeitung von großen Datenmengen, einschließlich personenbezogener Daten und vertraulicher Informationen. Mit Adobe Campaign können Sie Daten, einschließlich personenbezogener und vertraulicher Daten, erfassen. Es ist daher unerlässlich, dass Sie das Einverständnis Ihrer Empfänger erhalten und überwachen.

![](../assets/do-not-localize/book.png) Wie Sie Datenschutz und Einverständnis gewährleisten, erfahren Sie in der [Dokumentation zu Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=de){target=&quot;_blank&quot;}.

**Verwandte Themen** in der Dokumentation zu Campaign Classic v7:

* [Entwurf und Ausführung eines kampagnenspezifischen Workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=de#automating-with-workflows){target=&quot;_blank&quot;}

* [Informationen zur Auswahl der Audience für eine Kampagne](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=de){target=&quot;_blank&quot;}

* [Erste Schritte mit Workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=de){target=&quot;_blank&quot;}
