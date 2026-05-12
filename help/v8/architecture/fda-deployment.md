---
title: Erste Schritte mit der Campaign FDA-Bereitstellung
description: Erste Schritte mit der Campaign FDA-Bereitstellung
feature: Architecture, Federated Data Access, Deployment
role: Admin, Developer
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
TQID: https://experienceleague.adobe.com/PfXTlEYfwkN9YRDIx44TdtZLjNZJkHqN73sJGxA0c-E
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2:
  - id: ee3dfd63-9a21-4961-9f24-ea3385284a21
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 329
ht-degree: 84%

---

# [!DNL Campaign] FDA-Bereitstellung{#gs-fda}

In einer FDA-Bereitstellung (Standard) von Campaign ist [!DNL Adobe Campaign] v8 zwecks Datenzugriff über die [Federated Data Access](../connect/fda.md)-Funktion mit [!DNL Snowflake] verbunden: Sie können auf externe Daten und Informationen zugreifen, die in Ihrer [!DNL Snowflake]-Datenbank gespeichert sind, und diese verarbeiten, ohne die Datenstruktur in Adobe Campaign ändern zu müssen.

>[!NOTE]
>
>In diesem Bereitstellungsmodell ist die sekundäre Datenbank von [!DNL Snowflake] nur auf Anfrage verfügbar. Um Ihre Bereitstellung mit [!DNL Snowflake] zu aktualisieren, wenden Sie sich an Ihren Adobe Transition Manager.
>

## Vorteile{#fda-benefits}

Dieses Bereitstellungsmodell bietet die folgenden Vorteile:

* **Speicher und Leistung**
Sie können Ihre historischen Daten nach [!DNL Snowflake] verschieben und dann die Abhängigkeiten auf den Grenzwert für Adobe Campaign IDs reduzieren. Diese Architektur reduziert auch Ihre Abhängigkeit vom PostgreSQL-Speicher und von Performance-Beschränkungen. Da weniger Daten in der Campaign-Datenbank gespeichert werden, ist die Performance besser und Wartungsaufgaben werden schneller ausgeführt.

* **Datenmodellerweiterung und Daten-Management**
Sie können in [!DNL Snowflake] Tabellen erstellen und diese mit Adobe Campaign verknüpfen, um beispielsweise archivierte Daten während der Aufbewahrungsfrist zu verwenden oder Segmentierungsprozesse mit hervorragender Performance durchzuführen.

  Diese Architektur ermöglicht Ihnen auch die Verwendung von Workflow-Funktionen für das Daten-Management in [!DNL Snowflake]. Nur Aggregate und temporäre Tabellen werden zu Personalisierungs- und Versandzwecken nach Campaign verschoben.


## Architektur{#fda-archi}

Mit diesem Bereitstellungsmodell können Adobe Campaign-Benutzer ihre Daten nach [!DNL Snowflake] erweitern und in Echtzeit die Vorteile einer zentralen, integrierten Datenplattform für umfassende Dateneinblicke mithilfe von Marketing-Kampagnen nutzen. Es bietet den Benutzern die Möglichkeit, ihre Daten durch eine zentrale, einheitliche und benutzerfreundliche Datenanalyse-Plattform optimal zu nutzen. Die Cloud-Datenplattform erfordert keine Verwaltung, da sie unbegrenzt skaliert werden kann, um ein beliebiges Volumen an Marketing-Daten aus Adobe Campaign aufzunehmen.

Die allgemeine Kommunikation zwischen Servern und Prozessen erfolgt gemäß dem folgenden Schema:

![](assets/fda-architecture.png)

PostgreSQL ist die primäre Datenbank und Snowflake kann als sekundäre Datenbank verwendet werden. Sie können Ihr Datenmodell erweitern und Ihre Daten in Snowflake speichern. Anschließend können Sie ETL, Segmentierung und Berichte für einen großen Datensatz ausführen und hervorragende Performance erzielen.
