---
product: Adobe Campaign
title: Funktionsmatrix Campaign Classic v7/Campaign v8
description: Unterschiede zwischen Campaign Classic v7 und Campaign v8 verstehen
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: d61888a4536d6f37f5956c8fd5404bdcd893ae6c
workflow-type: tm+mt
source-wordcount: '921'
ht-degree: 99%

---

# [!DNL Campaign Classic] v7- und [!DNL Campaign] v8-Funktionen{#gs-matrix}

[!DNL Campaign Classic]Als bestehender v7-Benutzer sollten Sie bei der Interaktion mit [!DNL Adobe Campaign] keine größeren Änderungen feststellen. Die meisten Änderungen in v8 sind nicht sichtbar, mit Ausnahme kleiner Änderungen, die in der Benutzeroberfläche und in den Konfigurationsschritten erkennbar sind.

Wichtige Änderungen:

* Segmente können bis zu 200-mal schneller erstellt werden
* Erhöhte Versandgeschwindigkeit
* Echtzeit-Berichte     mit Cubes

Als [!DNL Campaign Classic]-Benutzer sollten Sie beachten, dass die meisten Funktionen von [!DNL Campaign Classic] v7 auch in [!DNL Campaign] v8 verfügbar sind, mit Ausnahme einiger weniger, die in [diesem Abschnitt](#gs-removed) aufgeführt sind. Weitere Änderungen werden in zukünftigen Versionen enthalten sein. [Weitere Informationen finden Sie in diesem Abschnitt](#gs-unavailable-features)

?? Weitere Informationen zur Architektur von [!DNL Campaign] v8 finden Sie auf [dieser Seite](../dev/architecture.md).

## Änderungen bei der Produktkonfiguration

### [!DNL Campaign] und [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8 kann mit zwei Datenbanken verwendet werden: einer lokalen Datenbank für Echtzeit-Messaging und Einzelabfragen und das Schreiben über APIs sowie einer Cloud-Datenbank für Kampagnenausführung, Batch-Abfragen und Workflow-Ausführung.

Dies ist eine grundlegende Änderung der Software-Architektur. Die Daten sind jetzt remote und Campaign führt die gesamten Daten, einschließlich Profilen, zusammen. Die [!DNL Campaign]-Prozesse skalieren jetzt durchgängig, vom Targeting bis zur Ausführung der Nachricht: Datenaufnahme, Segmentierung, Zielgruppenbestimmung, Abfragen und Sendungen laufen jetzt typischerweise in Minuten ab. Diese neue Version löst die ganze Herausforderung der Skalierung und bewahrt dabei den gleichen Grad an Flexibilität und Erweiterbarkeit. Die Anzahl der Profile ist nahezu unbegrenzt, und die Datenspeicherung kann verlängert werden.

Die Cloud-Datenspeicherung wird in **[!DNL Snowflake]** ausgeführt: Ein neues vorkonfiguriertes **externes Konto** stellt die Verbindung zur Cloud-Datenbank sicher. Das Konto wird von Adobe eingerichtet und darf nicht geändert werden. [Weitere Informationen](../config/external-accounts.md)

Jedes integrierte Schema (bzw. Tabelle), das in die Cloud-Datenbank verschoben oder repliziert werden muss, verfügt unter dem **xxl**-Namespace über eine integrierte Schemaerweiterung. Diese Erweiterungen enthalten alle Änderungen, die erforderlich sind, um eingebaute Schemata von der lokalen [!DNL Campaign]-Datenbank in die [!DNL Snowflake]-Cloud-Datenbank zu verschieben und ihre Struktur entsprechend anzupassen: neue UUID, aktualisierte Links usw.

>[!CAUTION]
>
> Kundendaten werden nicht in der lokalen [!DNL Campaign]-Datenbank gespeichert. Daher müssen benutzerdefinierte Tabellen in der Cloud-Datenbank erstellt werden.


Für die Verwaltung von Daten zwischen der lokalen und der Cloud-Datenbank stehen spezifische APIs zur Verfügung. Erfahren Sie auf [dieser Seite](../dev/new-apis.md), wie diese neuen APIs funktionieren und wie Sie sie verwenden können.

### Datenreplikation

Ein spezieller technischer Workflow behandelt die Replikation von Tabellen, die auf beiden Seiten vorhanden sein müssen (lokale Campaign-Datenbank und Cloud-Datenbank). Dieser Workflow wird stündlich ausgelöst und basiert auf einer neuen integrierten JavaScript-Bibliothek.

>[!NOTE]
>
> Es wurden mehrere Replikationsrichtlinien erstellt, die auf der Größe der Tabelle basieren (XS, XL usw.).
> Einige Tabellen werden in Echtzeit repliziert, andere werden stündlich repliziert. Einige Tabellen werden inkrementelle Aktualisierungen aufweisen, andere werden eine vollständige Aktualisierung durchlaufen.


[Weitere Informationen zur Datenreplikation](../config/replication.md)

### ID-Management

Campaign v8-Objekte verwenden jetzt eine **Universally Unique ID (UUID)**, die die Identifizierung von Daten durch unbegrenzte eindeutige Werte ermöglicht..

Beachten Sie, dass diese Kennung zeichenfolgenbasiert und nicht sequenziell ist. In Campaign v8 ist der Primärschlüssel kein numerischer Wert. In Ihren Schemata müssen Sie die Attribute **autouid** und **autopk** verwenden.

In Campaign Classic v7 und früheren Versionen wird die Eindeutigkeit eines Schlüssels innerhalb eines Schemas (d. h. einer Tabelle) auf der Ebene der Datenbank-Engine gewährleistet. Im Allgemeinen verfügen klassische Datenbank-Engines wie PostgreSQL, Oracle oder SQL Server über einen nativen Mechanismus, der verhindert, dass duplizierte Zeilen basierend auf einer Spalte oder einem Satz von Spalten über Primärschlüssel und/oder eindeutige Indizes eingefügt werden. Wenn der richtige Index und die richtigen Primärschlüssel auf Datenbankebene festgelegt wurden, sind duplizierte Kennungen bei diesen Versionen nicht möglich.

Adobe Campaign v8 wird mit Snowflake als Hauptdatenbank bereitgestellt. Um eine deutlich erhöhte Anzahl der Abfragen zu vermeiden, bietet die verteilte Architektur der Snowflake-Datenbank keine solchen Mechanismen zur Verwaltung und Durchsetzung eindeutiger Schlüssel innerhalb einer Tabelle. Dementsprechend wird bei Adobe Campaign v8 die Aufnahme duplizierter Schlüssel in einer Tabelle nicht verhindert. Endbenutzer sind nun selbst dafür verantwortlich, die Konsistenz der Schlüssel in der Adobe Campaign-Datenbank sicherzustellen. [Weitere Informationen](../dev/keys.md)

### Vereinfachte Wartung

Campaign-Benutzer müssen keine Datenbankexperten sein: Es besteht kein Bedarf mehr an komplexen Datenbankwartungsvorgängen oder komplexer Tabellenindizierung.

## Verbindung zu Campaign

Campaign-Benutzer stellen über ihre Adobe ID eine Verbindung her. Dieselbe Adobe ID wird verwendet, um alle Ihre Adobe-Pläne und -Produkte mit einem einzigen Konto zu verknüpfen.

?? Auf [dieser Seite](connect.md) erfahren Sie, wie Sie eine Verbindung zu [!DNL Campaign] herstellen können.

## Reporting

Beachten Sie, dass Adobe Campaign-Berichte optimiert sind und bessere Skalierungsfunktionen als Campaign Classic v7 bieten. Für Cubes gelten keine Einschränkungen.

## Workflow {#workflow}

Campaign v8 bietet eine zusätzliche Workflow-Aktivität für die Zielgruppenbestimmung: **[!UICONTROL Datenquelle ändern]**.

Die Aktivität **[!UICONTROL Datenquelle ändern]** ermöglicht es Ihnen, die Datenquelle des Workflows **[!UICONTROL Arbeitstabelle]** zu ändern, um Daten aus verschiedenen Datenquellen wie FDA, FFDA und lokalen Datenbanken zu verwalten.

?? Weitere Informationen zur Aktivität **[!UICONTROL Datenquelle ändern]** finden Sie auf [dieser Seite](../config/workflows.md#change-data-source-activity).

## Nicht verfügbare Funktionen{#gs-unavailable-features}

Bitte beachten Sie, dass in dieser ersten Version einige Funktionen noch nicht verfügbar sind, z. B.:

* Verwaltung von Marketing-Ressourcen
* Dezentrales Marketing
* Inbound-Angebotsverwaltung (Interaktionsmodul)
* Kampagnenoptimierung (Campaign Optimization)
* Reaktionsverwaltung
* Hybrid-/On-Premise-Implementierungsmodelle

>[!CAUTION]
>
>Derzeit ist Campaign v8 **nur** als Managed Cloud Service verfügbar und kann nicht in On-Premise- oder Hybridumgebungen bereitgestellt werden.
>
>Die Migration aus einer bestehenden Campaign Classic v7-Umgebung ist noch nicht möglich.
>
>Wenden Sie sich an Ihr Account-Team, wenn Sie sich bezüglich Ihres Bereitstellungsmodells nicht sicher sind oder Fragen haben.

## Entfernte Funktionen{#gs-removed}

Zur Anpassung an die neue Architektur und das Implementierungsmodell von Campaign v8 sind einige frühere Funktionen von Campaign Classic v7 in Campaign v8 nicht mehr verfügbar.

* Coupons
* Webtracking
* Umfragen
* Social Marketing
* ACS Connector (Prime-Angebote)
* Integration mit LDAP
* Anmelden mit Benutzer/Kennwort
