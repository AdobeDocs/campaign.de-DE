---
solution: Campaign v8
product: Adobe Campaign
title: Erste Schritte mit Campaign-APIs
description: Erste Schritte mit Campaign-APIs
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 32%

---

# Erste Schritte mit [!DNL Campaign] APIs{#gs-ac-api}

[!DNL Adobe Campaign]In stehen Ihnen eine Reihe von JavaScript-Funktionen zur Verfügung, die Sie wie folgt verwenden können:

* in Skripten - in [!DNL Adobe Campaign]-Workflows
* Über APIs für externe Systeme

Sie können JavaScript-APIs verwenden, um in der Cloud-Datenbank von Campaign Schreibvorgänge auszuführen oder aus ihr Daten abzufragen:

* Business-orientierte APIs, mit denen Sie auf diese einzelnen Objekte, also Versand, Workflows, Abonnements usw., Aktionen ausführen können. Weitere Informationen finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html?lang=de#configuring-campaign-classic).
* APIs zum allgemeinen Datenzugriff, mittels derer Datenmodell-Daten abgefragt werden können. Weitere Informationen finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html?lang=de).

Campaign v8 kann mit zwei Datenbanken verwendet werden: eine lokale Datenbank für die Echtzeit-Messaging- und Einzelabfragen der Benutzeroberfläche und das Schreiben über APIs sowie eine Cloud-Datenbank für die Kampagnenausführung, Berichterstellung, Datenerfassung, Batch-Abfragen und Workflow-Ausführung.

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8 enthält eine Begrenzung des Durchsatzes (TPS) unserer API-Ebene. Das Aufheben der Beschränkung führt zu einem standardmäßigen HTTP-Fehler (429). Als Benutzer von Managed Cloud Services können Sie sich an Adobe wenden, um die Einschränkungen für jede API anzupassen.


## Voraussetzungen

Bevor Sie [!DNL Adobe Campaign]-APIs verwenden, müssen Sie sich mit den folgenden Themen vertraut machen:

* JavaScript
* SOAP-Protokoll
* [!DNL Adobe Campaign] datamodel

Um APIs verwenden und mit [!DNL Adobe Campaign] interagieren zu können, müssen Sie auch mit Ihrem Datenmodell vertraut sein.

>[!NOTE]
>Sie können eine vollständige Beschreibung Ihres Datenmodells erstellen. Weiterführende Informationen finden Sie auf [dieser Seite](datamodel.md).

## [!DNL Campaign] API-Staging-Mechanismus

Bei der Cloud-Datenbank [!DNL Campaign] werden gebündelte Einzelaufrufe aufgrund der Leistung (Latenz und gleichzeitige Nutzung) nicht empfohlen. Batch-Vorgänge werden immer bevorzugt. Um eine optimale Leistung der APIs zu gewährleisten, verarbeitet Campaign API-Aufrufe weiterhin auf lokaler Datenbankebene.

[!DNL :bulb:] [Der API-Staging-Mechanismus wird auf dieser Seite beschrieben.](staging.md)

## Neue APIs

Für die Verwaltung der Datensynchronisation zwischen der lokalen Datenbank [!DNL Campaign] und der Cloud-Datenbank stehen neue APIs zur Verfügung. Außerdem wurde ein neuer Mechanismus zur Verarbeitung von API-Aufrufen auf lokaler Datenbankebene eingeführt, um Latenzzeiten zu vermeiden und die Gesamtleistung zu erhöhen

[!DNL :bulb:] [Neue APIs werden auf dieser Seite beschrieben.](new-apis.md)

**Verwandte Themen**

* [Best Practices für Datenmodelle](datamodel-best-practices.md)
