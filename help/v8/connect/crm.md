---
title: Mit Campaign und dem CRM-System arbeiten
description: Erfahren Sie, wie Sie mit Campaign und Ihrem CRM-System arbeiten können
feature: Overview
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 63%

---

# Campaign mit Ihrem CRM verbinden {#gs-crm}

Adobe Campaign stellt verschiedene CRM-Connectoren zur Verfügung, die die Verbindung der Adobe Campaign-Plattform mit Drittsystemen ermöglichen. So erlauben die CRM-Connectoren z. B. das Synchronisieren von Kontakten, Konten und Käufen. Zudem vereinfachen sie die Integration Ihres Programms mit bestehenden Systemen von Drittanbietern und Geschäftsprogrammen.

Diese Connectoren ermöglichen eine schnelle und einfache Datenintegration: Adobe Campaign bietet einen dedizierten Assistenten zur Erfassung und Auswahl aus den im CRM verfügbaren Tabellen. Damit ist eine bidirektionale Synchronisation gewährleistet, die sicherstellt, dass die Daten in den Systemen jederzeit aktuell sind.

Die wichtigsten Vorteile sind:

* Konsistentes Messaging zwischen Vertrieb und Marketing: Durch die Integration von Adobe Campaign in Ihr CRM erhalten beide Systeme Zugriff auf Kundeneinblicke und E-Mail-Marketingverlauf, sodass alle Nachrichten für den Kunden dasselbe konsistente Messaging nutzen können.

* Ganzheitliche Ansicht aller Interessenten- und Kundendaten: Durch die Integration von Adobe Campaign in Ihr CRM-System ist es möglich, den E-Mail-Marketing-Verlauf für jeden Kontakt innerhalb des CRM-Systems freizugeben und darauf zuzugreifen.

* Aktivieren Sie Ihre CRM-Daten auf allen Kanälen: Mit Kontaktdaten, die mit Adobe Campaign synchronisiert werden, können Nachrichten über jeden Online- oder Offline-Kanal mit Campaign gesendet werden, einschließlich Mobile Push, In-App, E-Mail oder Briefpost.


>[!NOTE]
>
>Diese Funktion ist in Adobe Campaign über das Package **CRM Connectoren** verfügbar.

## Kompatible Systeme {#compatible-crm-systems-and-limitations}

Unterstützte CRM-Systeme und Versionen werden in der [Kompatibilitätsmatrix](../start/compatibility-matrix.md) von Campaign erläutert.

![](../assets/do-not-localize/speech.png)  Die CRM-Connectoren funktionieren ausschließlich mit einer sicheren URL (https).

## Implementierungsschritte {#crm-implementation-steps}

Schrittweise Anleitung zum Verbinden von Campaign und Microsoft Dynamics in [diese Seite](ac-ms-dyn.md).

Schrittweise Anleitung zur Verbindung von Campaign und Salesforce.com finden Sie unter [diese Seite](ac-sfdc.md).

Die Datensynchronisation zwischen Adobe Campaign und dem CRM-System erfolgt über die spezifische Workflow-Aktivität. Erstellen Sie eigene Workflows, um die Synchronisierung zwischen Campaign und Ihrem CRM-System zu automatisieren. Sie können einen Workflow erstellen, der die Kontakte über Microsoft Dynamics importiert, sie mit den vorhandenen Adobe Campaign-Daten synchronisiert, doppelte Kontakte löscht und dann die Adobe Campaign-Datenbank aktualisiert.

![](../assets/do-not-localize/book.png) Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=de#getting-started).
