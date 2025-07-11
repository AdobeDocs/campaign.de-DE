---
title: Arbeiten mit Zielgruppen in Campaign
description: Arbeiten mit Zielgruppen in Campaign
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: ad96c126836981f861c246eafa2ec7d2c0e179dc
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 93%

---

# Arbeiten mit Zielgruppen in Campaign{#gs-ac-audiences}

Profile sind in der Campaign-Datenbank gespeicherte Kontakte.

In Adobe Campaign sind die Standardprofile für Sendungen (E-Mails, SMS usw.) die **Empfänger**. Mit den in der Datenbank gespeicherten Empfängerdaten können Sie die Zielgruppe filtern, die einen bestimmten Versand erhalten soll, und Personalisierungsdaten in den Versandinhalt einfügen. In der Datenbank gibt es noch andere Arten von Profilen. Sie sind für unterschiedliche Zwecke gedacht. So werden beispielsweise Testprofile erstellt, um Ihre Sendungen zu testen, bevor sie an die endgültige Zielgruppe gesendet werden.

[In diesem Abschnitt](../audiences/gs-audiences.md) erfahren Sie, wie Sie Profile und Zielgruppen importieren, aktualisieren und verwalten.

## Erstellen von Listen{#create-lists}

Eine Liste ist ein statischer Satz von Kontakten, die in Versandaktionen als Zielkontakte dienen oder beim Importieren bzw. bei einer Workflow-Ausführung aktualisiert werden können. So kann beispielsweise eine Population, die über eine Abfrage aus der Datenbank extrahiert wurde, als Liste gespeichert werden.

Informationen zum Erstellen und Verwalten von Listen finden Sie auf [dieser Seite](../audiences/create-audiences.md).

## Filtern der Datenbank{#filter-the-database}

Die Filterkonfiguration ermöglicht die **[!UICONTROL dynamische]** Auswahl von Daten aus einer Liste. Bei Änderung der Daten werden die gefilterten Daten aktualisiert. Sie können eigene Filter erstellen oder die integrierten Filter verwenden, um eine Zielgruppe zu definieren.

Informationen zum Erstellen und Verwalten von Filtern finden Sie auf [dieser Seite](../audiences/create-filters.md).

## Eine Zielgruppe in einem Workflow erstellen

Zielgruppenbestimmung kann über eine Kombination von Abfragen in einer grafischen Abfolge in einem Workflow erstellt werden. Sie können Zielgruppen erstellen und deren Targeting entsprechend Ihren Anforderungen anpassen. Um den Workflow-Editor anzuzeigen, klicken Sie im Campaign-Dashboard auf die Registerkarte **[!UICONTROL Zielgruppenbestimmung und Workflows]**.

Auf dieser Seite erfahren Sie, wie Sie eine Audience in einem Kampagnen[Workflow ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=de){target="_blank"}.


## Aktive Profile {#active-profiles}

Ein aktives Profil ist ein Profil, mit dem die Kundin oder der Kunde in den letzten 12 Monaten über einen beliebigen Kanal versucht hat, zu kommunizieren.

Gemäß Ihrem Vertrag erhalten alle Ihre Campaign-Instanzen eine bestimmte Anzahl aktiver Profile, die zu Abrechnungszwecken gezählt werden. Informationen zur Anzahl der gekauften aktiven Profile finden Sie in Ihrem aktuellen Vertrag. Weitere Informationen finden Sie in der [Adobe Campaign-Produktbeschreibung](https://helpx.adobe.com/de/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Sie können die Anzahl der aktiven Profile in Ihrer Instanz direkt über das Control Panel von Campaign überwachen. Weitere Informationen hierzu finden Sie in der [Dokumentation zu Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=de){target="_blank"}.


Es gelten die folgenden Schutzmechanismen und Einschränkungen:

* Ein Profil, das durch mehrere Sendungen angesprochen wurde, wird nur einmal gezählt.
* Profile, die im Rahmen von Social-Media-Marketing auf X (Twitter) angesprochen werden, werden nicht als aktive Profile berücksichtigt.
* Die Anzahl basiert auf dem Primärschlüssel der Empfängerin bzw. des Empfängers. Wenn also ein Profil in zwei verschiedenen Empfängertabellen vorhanden ist, kann es zweimal als aktives Profil gezählt werden.

## Datenschutz und Einverständniserklärung{#privacy-and-consent}

Adobe Campaign ist ein leistungsstarkes Tool zur Erfassung und Verarbeitung von großen Datenmengen, einschließlich personenbezogener Daten und vertraulicher Informationen. Mit Adobe Campaign können Sie Daten, einschließlich personenbezogener und vertraulicher Daten, erfassen. Es ist daher unerlässlich, dass Sie das Einverständnis Ihrer Empfänger erhalten und überwachen.

Erfahren Sie in der Dokumentation zu [Adobe Campaign Classic v7, wie Sie Datenschutz und Einverständnis ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=de){target="_blank"}.

