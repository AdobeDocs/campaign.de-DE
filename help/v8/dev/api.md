---
title: Erste Schritte mit Campaign-APIs
description: Erste Schritte mit Campaign-APIs
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 94fc2739c538f3aa8b11e0ea69d08f1bfffb5d32
workflow-type: ht
source-wordcount: '330'
ht-degree: 100%

---

# Erste Schritte mit [!DNL Campaign] APIs{#gs-ac-api}

In [!DNL Adobe Campaign] stehen Ihnen eine Reihe von JavaScript-Funktionen zur Verfügung, die Sie wie folgt verwenden können:

* Innerhalb von Skripten – in [!DNL Adobe Campaign]-Workflows
* Über APIs für externe Systeme

Sie können JavaScript-APIs verwenden, um in der Cloud-Datenbank von Campaign Schreibvorgänge auszuführen oder aus ihr Daten abzufragen:

* Geschäftsspezifische APIs, mit denen Sie auf jedes Objekt reagieren können: Sendungen, Workflows, Abonnements usw. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html?lang=de#configuring-campaign-classic).
* Generische Datenzugriffs-APIs zur Abfrage von Datenmodelldaten. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html?lang=de).

Campaign v8 kann mit zwei Datenbanken verwendet werden: einer lokalen Datenbank für Echtzeit-Messaging und Einzelabfragen und das Schreiben über APIs sowie einer Cloud-Datenbank für Kampagnenausführung, Berichterstellung, Datenaufnahme, Batch-Abfragen und Workflow-Ausführung.

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8 enthält eine Begrenzung des Durchsatzes (TPS) auf API-Ebene. Das Aufheben dieser Begrenzung führt zu einem standardmäßigen HTTP-Fehler (429). Als Benutzer von Managed Cloud Services können Sie sich an Adobe wenden, um die Begrenzung für jede API anzupassen.

## Voraussetzungen

Vor der Arbeit mit [!DNL Adobe Campaign]-APIs sollten Sie sich mit den folgenden Themen vertraut machen:

* JavaScript
* SOAP-Protokoll
* [!DNL Adobe Campaign]-Datenmodell

Um APIs verwenden und mit [!DNL Adobe Campaign] interagieren zu können, müssen Sie auch mit Ihrem Datenmodell vertraut sein.

>[!NOTE]
>Sie können eine vollständige Beschreibung Ihres Datenmodells erzeugen. Weiterführende Informationen finden Sie auf [dieser Seite](datamodel.md).

## [!DNL Campaign]-API-Staging-Mechanismus

In der [!DNL Campaign]-Cloud-Datenbank werden gebündelte Einzelabfragen aufgrund von Leistungseinbußen (Latenz und gleichzeitige Nutzung) nicht empfohlen. Batch-Vorgänge sind daher vorzuziehen. Um eine optimale Leistung der APIs zu gewährleisten, verarbeitet Campaign API-Aufrufe weiterhin auf lokaler Datenbankebene.

![](../assets/do-not-localize/glass.png) [Der API-Staging-Mechanismus wird auf dieser Seite beschrieben.](staging.md)

## Neue APIs

Für die Verwaltung der Datensynchronisation zwischen der lokalen [!DNL Campaign]-Datenbank und der Cloud-Datenbank stehen neue APIs zur Verfügung. Außerdem wurde ein neuer Mechanismus zur Verarbeitung von API-Aufrufen auf lokaler Datenbankebene eingeführt, um Latenzzeiten zu minimieren und die Gesamtleistung zu erhöhen.

![](../assets/do-not-localize/glass.png) [Neue APIs werden auf dieser Seite beschrieben.](new-apis.md)

**Verwandte Themen**

* [Best Practices für Datenmodelle](datamodel-best-practices.md)
