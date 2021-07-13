---
product: Adobe Campaign
title: Mit Campaign und dem CRM-System arbeiten
description: 'Erfahren Sie, wie Sie mit Campaign und Ihrem CRM-System arbeiten können '
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 89%

---

# Campaign mit Ihrem CRM verbinden {#gs-crm}

Adobe Campaign stellt verschiedene CRM-Connectoren zur Verfügung, die die Verbindung der Adobe Campaign-Plattform mit Drittsystemen ermöglichen. So erlauben die CRM-Connectoren z. B. das Synchronisieren von Kontakten, Konten und Käufen. Zudem vereinfachen sie die Integration Ihres Programms mit bestehenden Systemen von Drittanbietern und Geschäftsprogrammen.

Diese Connectoren ermöglichen eine schnelle und einfache Datenintegration: Adobe Campaign bietet einen dedizierten Assistenten zur Erfassung und Auswahl aus den im CRM verfügbaren Tabellen. Damit ist eine bidirektionale Synchronisation gewährleistet, die sicherstellt, dass die Daten in den Systemen jederzeit aktuell sind.

>[!NOTE]
>
>Diese Funktion ist in Adobe Campaign über das Package **CRM Connectoren** verfügbar.

## Kompatible Systeme {#compatible-crm-systems-and-limitations}

Unterstützte CRM-Systeme und Versionen werden in der [Kompatibilitätsmatrix](../start/compatibility-matrix.md) von Campaign erläutert.

?? Die CRM-Connectoren funktionieren ausschließlich unter Verwendung einer sicheren URL (https).

## Implementierungsschritte {#crm-implementation-steps}

↗️ schrittweise Anleitung zum Verbinden von Campaign und Microsoft Dynamics in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=de#microsoft-dynamics-implementation-steps)

↗️ schrittweise Anleitung zum Verbinden von Campaign und Salesforce in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=de#getting-started)


Die Datensynchronisation zwischen Adobe Campaign und dem CRM-System erfolgt über die spezifische Workflow-Aktivität. Erstellen Sie eigene Workflows, um die Synchronisierung zwischen Campaign und Ihrem CRM-System zu automatisieren. Sie können einen Workflow erstellen, der die Kontakte über Microsoft Dynamics importiert, sie mit den vorhandenen Adobe Campaign-Daten synchronisiert, doppelte Kontakte löscht und dann die Adobe Campaign-Datenbank aktualisiert.

↗️ Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=de#getting-started)

