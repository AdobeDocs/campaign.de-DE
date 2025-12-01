---
title: Erste Schritte mit Campaign-APIs
description: Erste Schritte mit Campaign-APIs
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 75e0069ccd4e23dbf64b9052fd81817e438b333e
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 80%

---

# Erste Schritte mit [!DNL Campaign] APIs {#gs-ac-api}

In [!DNL Adobe Campaign] stehen Ihnen eine Reihe von JavaScript-Funktionen zur Verfügung, die Sie wie folgt verwenden können:

* Innerhalb von Skripten – in [!DNL Adobe Campaign]-Workflows
* Über APIs für externe Systeme

>[!NOTE]
>
>Je nach Bereitstellungsmodell können Sie REST-APIs auch mit Campaign v8 verwenden. [Weitere Informationen](../dev/api/get-started-apis.md).

Sie können [Campaign JavaScript-APIs](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=de){target="_blank"} verwenden, um in der Cloud-Datenbank von Campaign zu schreiben oder aus ihr zu lesen:

* Geschäftsspezifische APIs, mit denen Sie auf jedes Objekt reagieren können: Sendungen, Workflows, Abonnements usw. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html?lang=de#configuring-campaign-classic){target="_blank"}.
* Generische Datenzugriffs-APIs zum Abfragen der Datenmodelldaten mithilfe von `queryDef` und des `NLWS`. Weitere Informationen finden Sie unter [Datenbank mit queryDef abfragen](query-api.md).

Es ist zu beachten, dass Campaign in seiner [Enterprise (FFDA)-Bereitstellung](../architecture/enterprise-deployment.md) mit zwei Datenbanken verwendet werden kann: einer lokalen Datenbank für Echtzeit-Messaging und Einzelabfragen über die Benutzeroberfläche und das Schreiben über APIs sowie einer Cloud-Datenbank für die Kampagnenausführung, für das Reporting, für die Datenaufnahme, für Batch-Abfragen und für die Workflow-Ausführung.

>[!CAUTION]
>
>* Ab Campaign v8.5.1 hat sich der Authentifizierungsprozess für Campaign v8 geändert. Technische Benutzerinnen bzw. Benutzer müssen Adobe Identity Management System (IMS) verwenden, um eine Verbindung mit Campaign herzustellen. Erfahren Sie in [dieser Technote](../../technotes/upgrades/ims-migration.md), wie Sie Ihre vorhandenen technischen Konten migrieren können.
>
>* [!DNL Adobe Campaign] v8 enthält eine Begrenzung des Durchsatzes (TPS) auf API-Ebene. Das Aufheben dieser Begrenzung führt zu einem standardmäßigen HTTP-Fehler (429). Als Benutzer von Managed Cloud Services können Sie sich an Adobe wenden, um die Begrenzung für jede API anzupassen.
> 

## Voraussetzungen {#ac-api-prerequisites}

Vor der Arbeit mit [!DNL Adobe Campaign]-APIs sollten Sie sich mit den folgenden Themen vertraut machen:

* JavaScript
* SOAP-Protokoll
* [!DNL Adobe Campaign]-Datenmodell

Um APIs verwenden und mit [!DNL Adobe Campaign] interagieren zu können, müssen Sie auch mit Ihrem Datenmodell vertraut sein.

>[!NOTE]
>Sie können eine vollständige Beschreibung Ihres Datenmodells erzeugen. Weiterführende Informationen finden Sie auf [dieser Seite](datamodel.md).


**Verwandte Themen**

<!-- * [Query the database with queryDef](query-api.md)-->
* [Best Practices für Datenmodelle](datamodel-best-practices.md)
* [Campaign JSAPI-Dokumentation](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=de){target="_blank"}
