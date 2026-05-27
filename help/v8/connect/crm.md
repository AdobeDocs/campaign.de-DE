---
title: Mit Campaign und dem CRM-System arbeiten
description: Erfahren Sie, wie Sie mit Campaign und Ihrem CRM-System arbeiten können
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin, User
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
version: Campaign v8, Campaign Classic v7
TQID: https://experienceleague.adobe.com/gYGdySWZC1j2VkvAkL9rVBes7iQvRkRjNjm-dvFsHBM
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: beb7a3c1-66ab-4786-b879-7621375b3c40id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 339
ht-degree: 87%

---

# Campaign mit Ihrem CRM verbinden {#gs-crm}

Adobe Campaign bietet verschiedene CRM-Connectoren für die Verknüpfung Ihrer Adobe Campaign-Plattform mit Ihren Drittanbietersystemen. Mit diesen CRM-Connectoren können Sie Kontakte, Konten, Käufe usw. synchronisieren. Sie erleichtern die Integration Ihres Programms mit verschiedenen Drittanbieter- und Geschäftsanwendungen.

Diese Connectoren ermöglichen eine schnelle und einfache Datenintegration: Adobe Campaign bietet einen dedizierten Assistenten zur Erfassung und Auswahl aus den im CRM verfügbaren Tabellen. Damit ist eine bidirektionale Synchronisation gewährleistet, die sicherstellt, dass die Daten in den Systemen jederzeit aktuell sind.

Die wichtigsten Vorteile sind:

* Konsistentes Messaging zwischen Vertrieb und Marketing: Die Integration von Adobe Campaign mit Ihrem CRM ermöglicht beiden Systemen den Zugriff auf Kundeninformationen und E-Mail-Marketing-Verläufe, sodass alle Nachrichten an den Kunden das gleiche konsistente Messaging aufweisen.

* Ganzheitliche Sicht auf alle Daten von Interessenten und Kunden: Durch die Integration von Adobe Campaign mit Ihrem CRM ist es möglich, im CRM-System den E-Mail-Marketing-Verlauf für jeden Kontakt freizugeben und darauf zuzugreifen.

* Aktivieren Ihrer CRM-Daten auf jedem Kanal: Mit Kontaktdaten, die mit Adobe Campaign synchronisiert sind, können Sie unter Verwendung von Campaign über jeden Online- oder Offline-Kanal Nachrichten senden, inklusive Mobile Push, In-App, E-Mail oder Briefpost.


>[!NOTE]
>
>Diese Funktion ist in Adobe Campaign über das Package **CRM Connectoren** verfügbar.

## Kompatible Systeme {#compatible-crm-systems-and-limitations}

Unterstützte CRM-Systeme und Versionen werden in der [Kompatibilitätsmatrix](../start/compatibility-matrix.md) von Campaign erläutert.

>[!CAUTION]
>
> Die Campaign-CRM-Connectoren funktionieren ausschließlich mit einer sicheren URL (https).

## Implementierungsschritte {#crm-implementation-steps}

Eine schrittweise Anleitung zum Verbinden von Campaign und Microsoft Dynamics finden Sie auf [dieser Seite](ac-ms-dyn.md).

Eine schrittweise Anleitung zum Verbinden von Campaign und Salesforce.com finden Sie auf [dieser Seite](ac-sfdc.md).

Die Datensynchronisation zwischen Adobe Campaign und dem CRM-System erfolgt über die spezifische Workflow-Aktivität. Erstellen Sie eigene Workflows, um die Synchronisierung zwischen Campaign und Ihrem CRM-System zu automatisieren. Sie können einen Workflow erstellen, der die Kontakte über Microsoft Dynamics importiert, mit den vorhandenen Adobe Campaign-Daten synchronisiert, doppelte Kontakte löscht und dann die Adobe Campaign-Datenbank aktualisiert. Weitere Informationen finden Sie auf [dieser Seite](crm-data-sync.md).
