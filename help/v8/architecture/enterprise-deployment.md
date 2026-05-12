---
title: Erste Schritte mit der Campaign FFDA-Bereitstellung
description: Erste Schritte mit der Campaign FFDA-Bereitstellung
feature: Architecture, FFDA, Deployment
role: Admin, Developer
level: Beginner
exl-id: 0a6f6701-b137-4320-9732-31946509ee03
TQID: https://experienceleague.adobe.com/aUERRFZaN8aJ883kmoYz2Yf47A1tYkf2HfOJZtCgs1g
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
subfeature_v2:
  - id: a72a22e0-8c8d-4019-ba42-3f2644aa91a3
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 1073
ht-degree: 95%

---

# [!DNL Campaign] FFDA-Bereitstellung {#gs-ac-ffda}

Durch die Nutzung von [[!DNL Snowflake]](https://www.snowflake.com/){target="_blank"}, einer Cloud-Datenbanktechnologie, wird die Skalierbarkeit und Geschwindigkeit der FFDA-Bereitstellung von Adobe Campaign Enterprise erheblich verbessert. So kann eine größere Anzahl von Kundenprofilen verwaltet werden und es werden deutlich höhere Versandraten und mehr Transaktionen pro Stunde erreicht.

## Vorteile {#ffda-benefits}

Campaign v8 Enterprise (FFDA) bietet eine End-to-End-Skalierung bei jedem Schritt des Prozesses, von der Zielgruppenbestimmung bis zum abschließenden Reporting:

* Skalieren Sie die Datenmenge, die Sie verarbeiten können (bis 8 TB)
* Skalieren Sie die Performance von Abfragen für Segmentierung und Zielgruppenbestimmung, aber auch für Datenaufnahme und -abgabe
* Skalieren der Versandvorbereitung (von Stunden auf Minuten)

Dies ist eine grundlegende Änderung der Software-Architektur. Die Daten sind jetzt remote und Campaign führt die gesamten Daten, einschließlich Profilen, zusammen. Die [!DNL Campaign]-Prozesse skalieren jetzt durchgängig, vom Targeting bis zur Ausführung der Nachricht: Datenaufnahme, Segmentierung, Zielgruppenbestimmung, Abfragen und Sendungen laufen jetzt typischerweise in Minuten ab. Diese neue Version löst die ganze Herausforderung der Skalierung und bewahrt dabei den gleichen Grad an Flexibilität und Erweiterbarkeit. Die Anzahl der Profile ist nahezu unbegrenzt, und die Datenspeicherung kann verlängert werden.

Die Cloud-Datenspeicherung wird in **[!DNL Snowflake]** ausgeführt: Ein neues natives **externes Konto** stellt die Verbindung zur Cloud-Datenbank sicher. Das Konto wird von Adobe eingerichtet und darf nicht geändert werden. [Weitere Informationen](../config/external-accounts.md)

Jedes integrierte Schema (bzw. Tabelle), das in die Cloud-Datenbank verschoben oder repliziert werden muss, verfügt unter dem **xxl**-Namespace über eine integrierte Schemaerweiterung. Diese Erweiterungen enthalten alle Änderungen, die erforderlich sind, um native Schemata von der lokalen [!DNL Campaign]-Datenbank in die [!DNL Snowflake]-Cloud-Datenbank zu verschieben und ihre Struktur entsprechend anzupassen: neue UUID, aktualisierte Links usw.

>[!CAUTION]
>
> Kundendaten werden nicht in der lokalen [!DNL Campaign]-Datenbank gespeichert. Daher müssen benutzerdefinierte Tabellen in der Cloud-Datenbank erstellt werden.
>

## Architektur von Campaign Enterprise (FFDA){#ffda-archi}

In einer [Enterprise (FFDA)-Bereitstellung](../architecture/enterprise-deployment.md) kann [!DNL Adobe Campaign] v8 mit zwei Datenbanken verwendet werden: einer lokalen [!DNL Campaign]-Datenbank für Echtzeit-Messaging und Einzelabfragen und das Schreiben über APIs sowie einer Cloud-[!DNL Snowflake]-Datenbank für die Kampagnenausführung, für Batch-Abfragen und die Workflow-Ausführung.

Campaign v8 Enterprise bietet das Konzept des **Full Federated Data Access** (FFDA): Alle Daten befinden sich nun entfernt in der Cloud-Datenbank.

Für die Verwaltung von Daten zwischen der lokalen und der Cloud-Datenbank stehen spezifische APIs zur Verfügung. Erfahren Sie auf [dieser Seite](new-apis.md), wie diese neuen APIs funktionieren und wie Sie sie verwenden können.

Die allgemeine Kommunikation zwischen Servern und Prozessen erfolgt gemäß dem folgenden Schema:

![](assets/architecture.png)

* Die Ausführungs- und Bounce-Management-Module sind in der Instanz deaktiviert.
* Das Programm ist so konfiguriert, dass Nachrichten auf einem entfernten &quot;Mid-Sourced&quot;-Server ausgeführt werden, der über SOAP-Aufrufe (über HTTP oder HTTPS) gesteuert wird.

Die [!DNL Snowflake]-Datenbank auf Marketing-Seite wird verwendet, um:

* Alle Kundendaten zu speichern: Profile, kundenspezifische Daten wie Transaktionen, Produkte, Standorte usw.
* Alle Ereignisse und Verhaltensdaten, die von Campaign generiert oder gesammelt werden, zu speichern, z. B. Versandlogs, Trackinglogs, Push-Registrierungen usw.
* Alle Datenaggregate der oben Genannten zu speichern.
* Eine Kopie (h+1) von Referenztabellen (wie Sendungen, Auflistungen, Länder usw.) die in Workflows, Kampagnen und Berichten verwendet werden.
* Alle Batch-Prozesse und -Workflows auszuführen.


Die PostgreSQL-Datenbank in der Marketing-Instanz wird verwendet, um:

* Bestimmte Workloads auszuführen, z. B. APIs mit geringem Volumen.
* Alle Campaign-Daten zu speichern, einschließlich Versand- und Kampagneneinstellungen, Workflow- und Service-Definitionen.
* Alle integrierten Referenztabellen (Auflistungen, Länder usw.) die nach [!DNL Snowflake] repliziert werden.

  Folgendes können Sie jedoch nicht tun:
   * Anpassungen für Kundendaten erstellen, z. B. keine Haushaltstabelle in PostgreSQL erstellen, sondern nur in Snowflake.
   * Versandlogs, Trackinglogs usw. in der FFDA-Zielgruppendimension speichern
   * Große Datenmengen speichern.


Die PostgreSQL-Datenbank in der Mid-Sourcing-Instanz wird verwendet, um:

* Batch- und Echtzeitsendungen auszuführen.
* Versand- und Trackinglogs zu senden. Beachten Sie, dass Bereitstellungs- und Trackinglog-IDs UUIDs und keine 32-Bit-IDs sind.
* Tracking-Daten zu erfassen und zu speichern.


## Auswirkungen{#ffda-impacts}

### API-Staging-Mechanismus von [!DNL Campaign]{#staging-api}

In der Cloud-Datenbank von [!DNL Campaign] wird das Bündeln von einzelnen Abfragen aufgrund von Performance-Einbußen (Latenz und gleichzeitige Nutzung) nicht empfohlen. Es müssen Batch-Vorgänge verwendet werden, um eine optimale API-Leistung zu gewährleisten, es sei denn, Sie senden ein extrem niedriges Volumen. Um die Performance zu verbessern, werden Aufnahme-APIs an die lokale Datenbank weitergeleitet. [Weitere Informationen zum API-Staging-Mechanismus von Campaign](staging.md)

### Neue APIs{#new-apis}

Für die Verwaltung der Datensynchronisation zwischen der lokalen [!DNL Campaign]-Datenbank und der Cloud-Datenbank stehen neue APIs zur Verfügung. Außerdem wurde ein neuer Mechanismus zur Verarbeitung von API-Aufrufen auf lokaler Datenbankebene eingeführt, um Latenzen zu minimieren und die Gesamt-Performance zu erhöhen.

[Neue APIs werden auf dieser Seite beschrieben.](new-apis.md)


### Datenreplikation{#data-replication}

Ein spezieller technischer Workflow behandelt die Replikation von Tabellen, die auf beiden Seiten vorhanden sein müssen (lokale Campaign-Datenbank und Cloud-Datenbank). Dieser Workflow wird stündlich ausgelöst und basiert auf einer neuen integrierten JavaScript-Bibliothek.

>[!NOTE]
>
> Es wurden mehrere Replikationsrichtlinien erstellt, die auf der Größe der Tabelle basieren (XS, XL usw.).
> Einige Tabellen werden in Echtzeit repliziert, andere werden stündlich repliziert. Einige Tabellen werden inkrementelle Aktualisierungen aufweisen, andere werden eine vollständige Aktualisierung durchlaufen.
>

[Weitere Informationen zur Datenreplikation](replication.md)

### ID-Management{#id-mgt-ffda}

Campaign v8-Objekte verwenden jetzt eine **Universally Unique ID (UUID)**, die die Identifizierung von Daten durch unbegrenzte eindeutige Werte ermöglicht.

Beachten Sie, dass diese Kennung zeichenfolgenbasiert und nicht sequenziell ist. In Campaign v8 ist der Primärschlüssel kein numerischer Wert. In Ihren Schemata müssen Sie die Attribute **autouid** und **autopk** verwenden.

In Campaign Classic v7 und früheren Versionen wird die Eindeutigkeit eines Schlüssels innerhalb eines Schemas (d. h. einer Tabelle) auf der Ebene der Datenbank-Engine gewährleistet. Im Allgemeinen verfügen klassische Datenbank-Engines wie PostgreSQL, Oracle oder SQL Server über einen nativen Mechanismus, der verhindert, dass duplizierte Zeilen basierend auf einer Spalte oder einem Satz von Spalten über Primärschlüssel und/oder eindeutige Indizes eingefügt werden. Wenn der richtige Index und die richtigen Primärschlüssel auf Datenbankebene festgelegt wurden, sind duplizierte Kennungen bei diesen Versionen nicht möglich.

Adobe Campaign v8 wird mit Snowflake als Hauptdatenbank bereitgestellt. Um eine deutlich erhöhte Anzahl der Abfragen zu vermeiden, bietet die verteilte Architektur der Snowflake-Datenbank keine solchen Mechanismen zur Verwaltung und Durchsetzung eindeutiger Schlüssel innerhalb einer Tabelle. Dementsprechend wird bei Adobe Campaign v8 die Aufnahme duplizierter Schlüssel in einer Tabelle nicht verhindert. Endbenutzer sind nun selbst dafür verantwortlich, die Konsistenz der Schlüssel in der Adobe Campaign-Datenbank sicherzustellen. [Weitere Informationen](keys.md)

### Funktionsverfügbarkeit {#feature-availability}

Einige Funktionen sind nicht im Kontext einer Enterprise (FFDA)-Bereitstellung von Campaign verfügbar, z. B.:

* Verwaltung von Marketing-Ressourcen
* Coupons
* Webtracking
* Umfragen


**Verwandte Themen**

* [Best Practices für Datenmodelle](../dev/datamodel-best-practices.md)
