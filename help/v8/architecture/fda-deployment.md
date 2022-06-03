---
title: Erste Schritte mit der Implementierung von FDA-Snowflake in Campaign
description: Erste Schritte mit der Implementierung von FDA-Snowflake in Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: 0fa0db62f45097755bebcbf434614c4c835d886a
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 100%

---

# [!DNL Campaign] FDA[!DNL Snowflake]-Implementierung{#gs-fda-snowflake}

In einer [!DNL Snowflake] FDA-Implementierung (Standard) ist [!DNL Adobe Campaign] v8 zwecks Datenzugriff über die [Federated Data Access](../connect/fda.md)-Funktion mit [!DNL Snowflake] verbunden: Sie können auf externe Daten und Informationen, die in Ihrer [!DNL Snowflake]-Datenbank gespeichert sind, zugreifen und diese verarbeiten, ohne die Datenstruktur in Adobe Campaign ändern zu müssen.

## Vorteile{#fda-benefits}

Dieses Implementierungsmodell bietet die folgenden Vorteile:

* **Speicherung und Leistung**
Sie können Ihre historischen Daten nach [!DNL Snowflake] verschieben und dann die Abhängigkeiten auf den Grenzwert für Adobe Campaign IDs reduzieren. Diese Architektur reduziert auch Ihre Abhängigkeit vom PostgreSQL-Speicher und von Leistungsbeschränkungen. Da weniger Daten in der Campaign-Datenbank gespeichert werden, ist die Leistung besser und Wartungsaufgaben werden schneller ausgeführt.

* **Datenmodellerweiterung und Daten-Management**
Sie können in [!DNL Snowflake] Tabellen erstellen und diese mit Adobe Campaign verknüpfen, um z. B. archivierte Daten während der Aufbewahrungsfrist zu nutzen oder Segmentierungsprozesse mit hervorragender Performance durchzuführen.

   Diese Architektur ermöglicht Ihnen auch die Verwendung von Workflow-Funktionen für das Daten-Management in [!DNL Snowflake]. Nur Aggregate und temporäre Tabellen werden zu Personalisierungs- und Versandzwecken nach Campaign verschoben.


## Architektur{#fda-archi}

Mit diesem Implementierungsmodell können Adobe Campaign-Benutzer ihre Daten nach [!DNL Snowflake] erweitern und in Echtzeit die Vorteile einer zentralen, integrierten Datenplattform für umfassende Dateneinblicke mithilfe von Marketing-Kampagnen nutzen. Es bietet den Benutzern die Möglichkeit, ihre Daten durch eine zentrale, einheitliche und benutzerfreundliche Datenanalyse-Plattform optimal zu nutzen. Die Cloud-Datenplattform erfordert keine Verwaltung, da sie unbegrenzt skaliert werden kann, um ein beliebiges Volumen an Marketing-Daten aus Adobe Campaign aufzunehmen.

Die allgemeine Kommunikation zwischen Servern und Prozessen erfolgt gemäß dem folgenden Schema:

![](assets/fda-architecture.png)

PostgreSQL ist die primäre Datenbank und Snowflake ist die sekundäre Datenbank. Sie können Ihr Datenmodell erweitern und Ihre Daten in Snowflake speichern. Anschließend können Sie ETL, Segmentierung und Berichte für einen großen Datensatz ausführen und hervorragende Leistung erzielen.
