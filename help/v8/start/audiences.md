---
solution: Campaign
product: Adobe Campaign
title: Erste Schritte mit Audiencen
description: Erste Schritte mit Audiencen
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
translation-type: tm+mt
source-git-commit: 3870395ec74dd51ed42944981a3851d1052ee255
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 38%

---

# Erste Schritte mit Audiencen{#gs-ac-audiences}

Profil können in Listen gruppiert oder durch Abfrage der Datenbank erfasst werden.

## Arbeiten mit Profilen{#gs-ac-profiles}

Profil werden in der Cloud-Datenbank zentralisiert. Die Akquise von Profilen und die Datenbankerstellung können auf verschiedenste Weisen erfolgen: Online-Akquise über Web-Formulare, manueller oder automatisierter Import von Textdateien, Replikation von bereits existierenden Datenbanken oder Informationssystemen des Unternehmens. Mit Adobe Campaign können Sie Marketing-Verlauf, Kaufinformationen, Voreinstellungen, CRM-Daten und alle relevanten PI-Daten in eine konsolidierte Ansicht integrieren, um sie zu analysieren und Maßnahmen zu ergreifen.

&quot;**Profil**&quot; bezeichnet einen Datensatz mit Informationen, die einen Kunden, einen Potenzieller Kunde, einen Newsletter-Abonnenten usw. repräsentieren.
Ein Datensatz in der Tabelle **nmsRecipient** oder in einer externen Tabelle enthält eine Cookie-ID, Kunden-ID, Mobilkennung oder andere Informationen, die für einen bestimmten Kanal relevant sind. Weitere Informationen zu integrierten Profilen und Empfängern finden Sie in [diesem Abschnitt](../dev/datamodel.md#ootb-profiles).

In Adobe Campaign sind die Standardprofile für Sendungen (E-Mails, SMS usw.) die Empfänger. Mit den in der Datenbank gespeicherten Empfängerdaten können Sie die Zielgruppe filtern, die einen bestimmten Versand erhalten soll, und Personalisierungsdaten in den Versandinhalt einfügen. In der Datenbank gibt es noch andere Arten von Profilen. Sie sind für unterschiedliche Zwecke gedacht. So werden beispielsweise Testprofile erstellt, um Ihre Sendungen zu testen, bevor sie an die endgültige Zielgruppe gesendet werden.

:arrow_forward: [Verstehen Sie, was ein Profil im Video ist](https://video.tv.adobe.com/v/35611?quality=12)

:arrow_upper_right: Erfahren Sie, wie Sie Profil in [diesem Handbuch](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html) verwalten.

## Datenschutz und Einverständniserklärung

Adobe Campaign ist ein leistungsstarkes Tool zur Erfassung und Verarbeitung sehr großer Datenmengen, einschließlich personenbezogener Daten und vertraulicher Informationen. Mit Adobe Campaign können Sie Daten, einschließlich persönlicher und vertraulicher Daten, erfassen. Es ist daher unerlässlich, dass Sie das Einverständnis Ihrer Empfänger erhalten und überwachen.

:arrow_upper_right: Erfahren Sie, wie Sie Privatsphäre und Zustimmung in [diesem Handbuch](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html) verwalten.


## Listen erstellen

Eine Liste ist eine statische Gruppe von Profilen, die als Zielgruppe für Sendungen verwendet oder durch Importe sowie Workflows aktualisiert werden kann. So kann beispielsweise eine mithilfe einer Abfrage aus der Datenbank gefilterte Population in einer Liste gespeichert werden.

:arrow_upper_right: Erfahren Sie, wie Sie Listen in [diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html) erstellen und verwalten.

## Abfrage der Datenbank

Verwenden Sie die Aktivität **Abfrage** in einem Workflow, um Ihre Datenbank zu Abfrage, Segmentdaten und komplexe Audiencen zu erstellen.

:arrow_upper_right: Weitere Informationen zu Abfragen der Kampagne finden Sie in [diesem Handbuch](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html).

:arrow_upper_right: Alle Targeting-Aktivitäten sind in [dieser Seite](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html) aufgeführt

## Erstellen einer Audience in einem Workflow

Targeting kann über eine Kombination von Abfragen in einer grafischen Abfolge in einem Workflow erstellt werden. Sie können Audiencen erstellen, die Ihren Anforderungen entsprechend ausgerichtet werden. Um den Workflow-Editor anzuzeigen, klicken Sie im Dashboard Kampagne auf die Registerkarte **[!UICONTROL Targeting und Workflows]**.

:arrow_upper_right: Erfahren Sie, wie Sie eine Audience in einem Arbeitsablauf für Kampagnen auf [dieser Seite]https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow) erstellen.


## Aktive Profile{#active-profiles}

Gemäß Ihrem Vertrag erhalten alle Ihre Campaign-Instanzen eine bestimmte Anzahl aktiver Profile, die zu Abrechnungszwecken gezählt werden. Informationen zur Anzahl der gekauften aktiven Profile finden Sie in Ihrem aktuellen Vertrag.

&quot;Profil&quot; einen Datensatz mit Informationen (z. B.: einen Datensatz in der Tabelle [Empfänger](../dev/datamodel.md) oder eine externe Tabelle, die eine Cookie-ID, Kunden-ID, Mobilkennung oder andere für einen bestimmten Kanal relevante Informationen enthält), der einen Endkunden, Potenzieller Kunde oder Interessenten darstellt. Profil gelten als aktiv, wenn sie in den letzten 12 Monaten über einen Kanal anvisiert oder mitgeteilt wurden.

Sie können die Anzahl der aktiven Profil, die auf Ihren Instanzen verwendet werden, direkt über die Systemsteuerung der Kampagne überwachen.

:arrow_upper_right: Weitere Informationen finden Sie in der [Systemsteuerung Dokumentation](https://docs.adobe.com/content/help/de-DE/control-panel/using/performance-mosnitoring/active-profiles-monitoring.html).


**Verwandte Themen**

:arrow_upper_right: [Entwerfen und Ausführen eines Kampagne-spezifischen Workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html)

:arrow_upper_right: [Erfahren Sie, wie die Audience einer Kampagne](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html) ausgewählt wird.

:arrow_upper_right: [Erste Schritte mit Workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
