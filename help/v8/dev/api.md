---
title: Erste Schritte mit Campaign-APIs
description: Erste Schritte mit Campaign-APIs
feature: API
role: Data Engineer
level: Beginner
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: c44fb2de4ed0e1661801313ae0430ba9d19542f0
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 82%

---

# Erste Schritte mit [!DNL Campaign] APIs{#gs-ac-api}

In [!DNL Adobe Campaign] stehen Ihnen eine Reihe von JavaScript-Funktionen zur Verfügung, die Sie wie folgt verwenden können:

* Innerhalb von Skripten – in [!DNL Adobe Campaign]-Workflows
* Über APIs für externe Systeme

Sie können JavaScript-APIs verwenden, um in der Cloud-Datenbank von Campaign Schreibvorgänge auszuführen oder aus ihr Daten abzufragen:

* Geschäftsspezifische APIs, mit denen Sie auf jedes Objekt reagieren können: Sendungen, Workflows, Abonnements usw. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html?lang=de#configuring-campaign-classic){target=&quot;_blank&quot;}.
* Generische Datenzugriffs-APIs zur Abfrage von Datenmodelldaten. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html?lang=de){target=&quot;_blank&quot;}.

Beachten Sie Folgendes: [Enterprise (FFDA)-Bereitstellung](../architecture/enterprise-deployment.md), Campaign verwendet zwei Datenbanken: eine lokale Datenbank für die Echtzeit-Messaging- und Einzelabfragen der Benutzeroberfläche und das Schreiben über APIs sowie eine Cloud-Datenbank für die Kampagnenausführung, Berichterstellung, Datenerfassung, Batch-Abfragen und Workflow-Ausführung.

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


**Verwandte Themen**

* [Best Practices für Datenmodelle](datamodel-best-practices.md)
