---
title: Mit Campaign und dem CRM-System arbeiten
description: Erfahren Sie, wie Sie mit Campaign und Ihrem CRM-System arbeiten können
feature: Salesforce Integration, Microsoft Integration
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 100%

---

# Campaign mit Ihrem CRM verbinden {#gs-crm}

Adobe Campaign stellt verschiedene CRM-Connectoren zur Verfügung, die die Verbindung der Adobe Campaign-Plattform mit Drittsystemen ermöglichen. So erlauben die CRM-Connectoren z. B. das Synchronisieren von Kontakten, Konten und Käufen. Zudem vereinfachen sie die Integration Ihres Programms mit bestehenden Systemen von Drittanbietern und Geschäftsprogrammen.

Diese Connectoren ermöglichen eine schnelle und einfache Datenintegration: Adobe Campaign bietet einen dedizierten Assistenten zur Erfassung und Auswahl aus den im CRM verfügbaren Tabellen. Damit ist eine bidirektionale Synchronisation gewährleistet, die sicherstellt, dass die Daten in den Systemen jederzeit aktuell sind.

Die wichtigsten Vorteile sind:

* Konsistentes Messaging zwischen Vertrieb und Marketing: Die Integration von Adobe Campaign mit Ihrem CRM ermöglicht beiden Systemen den Zugriff auf Kundeninformationen und E-Mail-Marketing-Verläufe, sodass alle Nachrichten an den Kunden das gleiche konsistente Messaging aufweisen.

* Ganzheitliche Sicht auf alle Daten von Interessenten und Kunden: Durch die Integration von Adobe Campaign mit Ihrem CRM ist es möglich, im CRM-System den E-Mail-Marketing-Verlauf für jeden Kontakt freizugeben und darauf zuzugreifen.

* Aktivieren Ihrer CRM-Daten auf jedem Kanal: Mit Kontaktdaten, die mit Adobe Campaign synchronisiert sind, können Sie unter Verwendung von Campaign über jeden Online- oder Offline-Kanal Nachrichten senden, inklusive Mobile Push, In-App, E-Mail oder Briefpost.


>[!NOTE]
>
>Diese Funktion ist in Adobe Campaign über das Package **CRM-Connectoren** verfügbar.

## Kompatible Systeme {#compatible-crm-systems-and-limitations}

Unterstützte CRM-Systeme und Versionen werden in der [Kompatibilitätsmatrix](../start/compatibility-matrix.md) von Campaign erläutert.

>[!CAUTION]
>
> Die Campaign-CRM-Connectoren funktionieren ausschließlich mit einer sicheren URL (https).

## Implementierungsschritte {#crm-implementation-steps}

Eine schrittweise Anleitung zum Verbinden von Campaign und Microsoft Dynamics finden Sie auf [dieser Seite](ac-ms-dyn.md).

Eine schrittweise Anleitung zum Verbinden von Campaign und Salesforce.com finden Sie auf [dieser Seite](ac-sfdc.md).

Die Datensynchronisation zwischen Adobe Campaign und dem CRM-System erfolgt über die spezifische Workflow-Aktivität. Erstellen Sie eigene Workflows, um die Synchronisierung zwischen Campaign und Ihrem CRM-System zu automatisieren. Sie können einen Workflow erstellen, der die Kontakte über Microsoft Dynamics importiert, mit den vorhandenen Adobe Campaign-Daten synchronisiert, doppelte Kontakte löscht und dann die Adobe Campaign-Datenbank aktualisiert. Weiterführende Informationen finden Sie auf [dieser Seite](crm-data-sync.md).
