---
solution: Campaign v8
product: Adobe Campaign
title: Funktionsmatrix von Campaign Classic v7 - Campaign v8
description: Unterschiede zwischen Campaign Classic v7 und Campaign v8
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 4%

---

# [!DNL Campaign Classic] v7 -  [!DNL Campaign] v8-Funktionen{#gs-matrix}

Als bestehender [!DNL Campaign Classic] v7-Benutzer sollten Sie keine großen Störungen in der Art und Weise erwarten, wie Sie normalerweise mit [!DNL Adobe Campaign] interagieren. Die meisten Änderungen in v8 sind nicht sichtbar, mit Ausnahme kleiner Änderungen, die in der Benutzeroberfläche und in den Konfigurationsschritten sichtbar sind.

Wichtige Änderungen:

* Segmente bis zu 200 x schneller erstellen
* Geschwindigkeit der Auslieferung erhöhen
* Echtzeitberichterstellung mit Cubes

Beachten Sie als Benutzer von [!DNL Campaign Classic], dass die meisten [!DNL Campaign Classic] v7-Funktionen mit [!DNL Campaign] v8 verfügbar sind, mit Ausnahme eines kleinen Satzes, der in [diesem Abschnitt](#gs-removed) aufgelistet ist. Andere werden in zukünftigen Versionen verfügbar sein. [Weitere Informationen finden Sie in diesem Abschnitt](#gs-unavailable-features)

[!DNL :bulb:] Weitere Informationen zur Architektur von  [!DNL Campaign] v8 finden Sie auf  [dieser Seite](../dev/architecture.md).

## Änderungen der Produktkonfiguration

### [!DNL Campaign] und [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8 funktioniert mit zwei Datenbanken: eine lokale Datenbank für die Echtzeit-Messaging- und Einzelabfragen der Benutzeroberfläche und das Schreiben über APIs sowie eine Cloud-Datenbank für die Kampagnenausführung, Batch-Abfragen und Workflow-Ausführung.

Dies ist ein grundlegender Wandel in der Softwarearchitektur. Daten sind jetzt remote und Campaign führt die gesamten Daten, einschließlich Profile, zusammen. [!DNL Campaign] -Prozesse werden jetzt von der Zielgruppenbestimmung zur Nachrichtenausführung skaliert: Datenerfassung, Segmentierung, Targeting, Abfragen, Sendungen werden jetzt in der Regel in Minuten ausgeführt. Diese neue Version löst die gesamte Herausforderung der Skalierung, während gleichzeitig das gleiche Maß an Flexibilität und Erweiterbarkeit beibehalten wird. Die Anzahl der Profile ist fast unbegrenzt und die Datenaufbewahrung kann erweitert werden.

Cloud-Speicher wird in **[!DNL Snowflake]** ausgeführt: Ein neues integriertes **externes Konto** stellt die Verbindung mit der Cloud-Datenbank sicher. Sie wird von Adobe konfiguriert und darf nicht geändert werden. [Weitere Informationen](../config/external-accounts.md).

Jedes integrierte Schema/jede integrierte Tabelle, das/die in der Cloud-Datenbank verschoben oder repliziert werden muss, enthält eine integrierte Schemaerweiterung unter dem Namespace **xxl**. Diese Erweiterungen enthalten alle erforderlichen Änderungen, um die integrierten Schemata aus der lokalen Datenbank [!DNL Campaign] in die Cloud-Datenbank zu verschieben und ihre Struktur entsprechend anzupassen: neue UUID, aktualisierte Links usw.[!DNL Snowflake]

>[!CAUTION]
>
> Kundendaten werden nicht in der lokalen [!DNL Campaign]-Datenbank gespeichert. Daher muss jede benutzerdefinierte Tabelle in der Cloud-Datenbank erstellt werden.


Es stehen spezifische APIs zur Verwaltung von Daten zwischen der lokalen und der Cloud-Datenbank zur Verfügung. Erfahren Sie, wie diese neuen APIs funktionieren und wie Sie sie auf [dieser Seite](../dev/new-apis.md) verwenden.

### Datenreplikation

Ein spezifischer technischer Workflow verarbeitet die Replikation von Tabellen, die auf beiden Seiten vorhanden sein müssen (lokale Campaign-Datenbank und Cloud-Datenbank). Dieser Workflow wird stündlich ausgelöst und stützt sich auf eine neue integrierte JavaScript-Bibliothek.

>[!NOTE]
>
> Es wurden mehrere Replikationsrichtlinien erstellt, die auf der Größe der Tabelle (XS, XL usw.) basieren.
> Einige Tabellen werden in Echtzeit repliziert, andere werden stündlich repliziert. Einige Tabellen werden inkrementelle Aktualisierungen aufweisen, andere müssen vollständig aktualisiert werden.


[Weitere Informationen zur Datenreplikation](../config/replication.md)

### ID-Management

Campaign v8-Objekte verwenden jetzt eine **Universally Unique ID (UUID)**, die die Identifizierung von Daten durch unbegrenzte eindeutige Werte ermöglicht

Beachten Sie, dass diese ID zeichenfolgenbasiert und nicht sequenziell ist.

### Vereinfachte Wartung

Campaign-Benutzer müssen keine Datenbankexperten sein: Es ist nicht mehr erforderlich, komplexe Datenbankwartungsvorgänge oder komplexe Tabellenindizierungen durchzuführen.

## Temporäre nicht verfügbare Funktionen{#gs-unavailable-features}

Beachten Sie, dass einige Funktionen in dieser ersten Version noch nicht verfügbar sind, z. B.:

* Verwaltung von Marketing-Ressourcen
* Dezentrales Marketing
* Eingehendes Angebotsmanagement (Interaction-Modul)
* Kampagnenoptimierung (Campaign Optimization)
* Reaktionsverwaltung
* Hybride/On-Premise-Bereitstellungsmodelle

## Entfernte Funktionen{#gs-removed}

In Übereinstimmung mit der neuen Architektur und dem neuen Bereitstellungsmodell von Campaign v8 sind einige Funktionen des historischen Campaign Classic v7 nicht mehr in Campaign v8 verfügbar.

* Coupons
* Webtracking
* Umfragen
* Social Marketing
* ACS Connector (Prime-Angebot)

