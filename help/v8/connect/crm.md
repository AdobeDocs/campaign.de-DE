---
solution: Campaign v8
product: Adobe Campaign
title: Campaign und Ihr CRM verwenden
description: 'Erfahren Sie, wie Sie mit Campaign und Ihrem CRM-System arbeiten. '
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 24%

---

# Verbinden Ihres CRM mit Campaign {#gs-crm}

Adobe Campaign stellt verschiedene CRM-Connectoren zur Verfügung, die die Verbindung der Adobe Campaign-Plattform mit Drittsystemen ermöglichen. So erlauben die CRM-Connectoren z. B. das Synchronisieren von Kontakten, Konten und Bestellungen. Zudem vereinfachen sie die Integration der Anwendung in bestehende Systeme.

Diese Connectoren ermöglichen eine schnelle und einfache Datenintegration: Adobe Campaign bietet einen speziellen Assistenten zur Erfassung und Auswahl aus den im CRM-System verfügbaren Tabellen. Dies garantiert eine bidirektionale Synchronisation, um sicherzustellen, dass die Daten in allen Systemen jederzeit auf dem neuesten Stand sind.

>[!NOTE]
>
>Diese Funktion ist in Adobe Campaign über das **CRM Connectoren-** Package verfügbar.

## Kompatible Systeme {#compatible-crm-systems-and-limitations}

Unterstützte CRM-Systeme und Versionen werden in der [Kompatibilitätsmatrix](../start/compatibility-matrix.md) von Campaign erläutert.

:Sprache_Ballon: Die CRM-Connectoren funktionieren nur mit einer sicheren URL (https).

## Umsetzung {#crm-implementation-steps}

:arrow_upper_right: Schrittweise Anleitung zum Verbinden von Campaign und Microsoft Dynamics finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps) .

:arrow_upper_right: Schrittweise Anleitung zum Verbinden von Campaign und Salesforce in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started)


Die Datensynchronisation zwischen Adobe Campaign und dem CRM-System erfolgt über eine spezielle Workflow-Aktivität. Erstellen Sie Ihre Workflows, um die Synchronisation zwischen Campaign und Ihrem CRM zu automatisieren. Sie können einen Workflow erstellen, der die Kontakte über Microsoft Dynamics importiert, mit den vorhandenen Adobe Campaign-Daten synchronisiert, duplizierte Kontakte löscht und dann die Adobe Campaign-Datenbank aktualisiert.

:arrow_upper_right: Weitere Informationen finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)

