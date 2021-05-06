---
solution: Campaign Classic
product: campaign
title: Arbeiten mit Kampagne und CRM
description: 'Erfahren Sie, wie Sie mit Kampagne und Ihrem CRM-System arbeiten können '
feature: Übersicht
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8c9f59067cd0e5a39e84315e5836a32bdf7a0864
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 25%

---

# Verbinden Sie Ihr CRM mit der Kampagne {#gs-crm}

Adobe Campaign stellt verschiedene CRM-Connectoren zur Verfügung, die die Verbindung der Adobe Campaign-Plattform mit Drittsystemen ermöglichen. So erlauben die CRM-Connectoren z. B. das Synchronisieren von Kontakten, Konten und Bestellungen. Zudem vereinfachen sie die Integration der Anwendung in bestehende Systeme.

Diese Connectors ermöglichen eine schnelle und einfache Datenintegration: Adobe Campaign bietet einen engagierten Assistenten zur Erfassung und Auswahl aus den im CRM verfügbaren Tabellen. Dadurch wird eine bidirektionale Synchronisierung gewährleistet, um sicherzustellen, dass die Daten jederzeit auf dem gesamten System auf dem neuesten Stand sind.

>[!NOTE]
>
>Diese Funktion ist in Adobe Campaign über das **CRM Connectoren-** Package verfügbar.

## Kompatible Systeme {#compatible-crm-systems-and-limitations}

Unterstützte CRM-Systeme und Versionen werden in der [Kompatibilitätsmatrix](../start/compatibility-matrix.md) von Campaign erläutert.

**HINWEIS** : Die CRM-Connectors funktionieren nur mit einer sicheren URL (https).

## Umsetzung {#crm-implementation-steps}

:arrow_upper_right: Anleitung zum Anschließen von Kampagne und Microsoft Dynamics in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps)

:arrow_upper_right: Anleitung zum Anschließen von Kampagne und Salesforce in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started)


Die Datensynchronisierung zwischen Adobe Campaign und CRM erfolgt über eine dedizierte Workflow-Aktivität. Erstellen Sie Ihre Workflows, um die Synchronisierung zwischen Kampagne und CRM zu automatisieren. Sie können einen Workflow erstellen, der die Kontakte über Microsoft Dynamics importiert, sie mit den vorhandenen Adobe Campaign-Daten synchronisiert, Duplikat-Kontakte löscht und dann die Adobe Campaign-Datenbank aktualisiert.

:arrow_upper_right: Weitere Informationen finden Sie in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)

