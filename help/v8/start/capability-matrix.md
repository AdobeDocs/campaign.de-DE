---
product: Adobe Campaign
title: Funktionsmatrix Campaign Classic v7/Campaign v8
description: Unterschiede zwischen Campaign Classic v7 und Campaign v8 verstehen
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 54%

---

# [!DNL Campaign Classic] v7 -  [!DNL Campaign] v8-Funktionen{#gs-matrix}

Als bestehender [!DNL Campaign Classic] v7-Benutzer sollten Sie keine großen Störungen in der Art und Weise erwarten, wie Sie normalerweise mit [!DNL Adobe Campaign] interagieren. Die meisten Änderungen in v8 sind nicht sichtbar, mit Ausnahme kleiner Änderungen, die in der Benutzeroberfläche und in den Konfigurationsschritten erkennbar sind.

Wichtige Änderungen:

* Segmente können bis zu 200-mal schneller erstellt werden
* Erhöhte Versandgeschwindigkeit
* Echtzeit-Berichte mit Cubes

Beachten Sie als Benutzer von [!DNL Campaign Classic], dass die meisten [!DNL Campaign Classic] v7-Funktionen mit [!DNL Campaign] v8 verfügbar sind, mit Ausnahme eines kleinen Satzes, der in [diesem Abschnitt](#gs-removed) aufgelistet ist. Weitere Änderungen werden in zukünftigen Versionen erscheinen. [Weitere Informationen finden Sie in diesem Abschnitt](#gs-unavailable-features)

[!DNL :bulb:] Weitere Informationen zur Architektur von  [!DNL Campaign] v8 finden Sie auf  [dieser Seite](../dev/architecture.md).

## Änderungen bei der Produktkonfiguration

### [!DNL Campaign] und [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8 funktioniert mit zwei Datenbanken: eine lokale Datenbank für die Echtzeit-Messaging- und Einzelabfragen der Benutzeroberfläche und das Schreiben über APIs sowie eine Cloud-Datenbank für die Kampagnenausführung, Batch-Abfragen und Workflow-Ausführung.

Dies ist eine grundlegende Änderung der Software-Architektur. Die Daten sind jetzt remote und Campaign führt die gesamten Daten, einschließlich Profilen, zusammen. [!DNL Campaign] -Prozesse werden jetzt von der Zielgruppenbestimmung zur Nachrichtenausführung skaliert: Datenerfassung, Segmentierung, Targeting, Abfragen, Sendungen werden jetzt in der Regel in Minuten ausgeführt. Diese neue Version löst die ganze Herausforderung der Skalierung und bewahrt dabei den gleichen Grad an Flexibilität und Erweiterbarkeit. Die Anzahl der Profile ist nahezu unbegrenzt, und die Datenspeicherung kann verlängert werden.

Cloud-Speicher wird in **[!DNL Snowflake]** ausgeführt: Ein neues integriertes **externes Konto** stellt die Verbindung mit der Cloud-Datenbank sicher. Sie wird von Adobe konfiguriert und darf nicht geändert werden. [Weitere Informationen](../config/external-accounts.md).

Jedes integrierte Schema (oder Tabelle), das in die Cloud-Datenbank verschoben oder repliziert werden muss, verfügt unter dem **xxl**-Namespace über eine integrierte Schemaerweiterung. Diese Erweiterungen enthalten alle erforderlichen Änderungen, um die integrierten Schemata aus der lokalen Datenbank [!DNL Campaign] in die Cloud-Datenbank zu verschieben und ihre Struktur entsprechend anzupassen: neue UUID, aktualisierte Links usw.[!DNL Snowflake]

>[!CAUTION]
>
> Kundendaten werden nicht in der lokalen [!DNL Campaign]-Datenbank gespeichert. Daher müssen benutzerdefinierte Tabellen in der Cloud-Datenbank erstellt werden.


Es stehen spezifische APIs zur Verwaltung von Daten zwischen der lokalen und der Cloud-Datenbank zur Verfügung. Erfahren Sie, wie diese neuen APIs funktionieren und wie Sie sie auf [dieser Seite](../dev/new-apis.md) verwenden.

### Datenreplikation

Ein spezieller technischer Workflow behandelt die Replikation von Tabellen, die auf beiden Seiten vorhanden sein müssen (lokale Campaign-Datenbank und Cloud-Datenbank). Dieser Workflow wird stündlich ausgelöst und basiert auf einer neuen integrierten JavaScript-Bibliothek.

>[!NOTE]
>
> Es wurden mehrere Replikationsrichtlinien erstellt, die auf der Größe der Tabelle basieren (XS, XL usw.).
> Einige Tabellen werden in Echtzeit repliziert, andere werden stündlich repliziert. Einige Tabellen werden inkrementelle Aktualisierungen aufweisen, andere werden eine vollständige Aktualisierung durchlaufen.


[Weitere Informationen zur Datenreplikation](../config/replication.md)

### ID-Management

Campaign v8-Objekte verwenden jetzt eine **Universally Unique ID (UUID)**, die die Identifizierung von Daten durch unbegrenzte eindeutige Werte ermöglicht..

Beachten Sie, dass diese ID zeichenfolgenbasiert und nicht sequenziell ist.

### Vereinfachte Wartung

Campaign-Benutzer müssen keine Datenbankexperten sein: Es besteht kein Bedarf mehr an komplexen Datenbankwartungsvorgängen oder komplexer Tabellenindizierung.

## Nicht verfügbare Funktionen{#gs-unavailable-features}

Beachten Sie, dass einige Funktionen in dieser ersten Version nicht verfügbar sind, z. B.:

* Verwaltung von Marketing-Ressourcen
* Dezentrales Marketing
* Inbound-Angebotsverwaltung (Interaktionsmodul)
* Kampagnenoptimierung (Campaign Optimization)
* Reaktionsverwaltung
* Hybrid-/On-Premise-Implementierungsmodelle

>[!CAUTION]
>
>Derzeit ist Campaign v8 **nur** als verwalteter Cloud Service verfügbar und kann nicht in On-Premise- oder Hybridumgebungen bereitgestellt werden.
>
>Die Migration aus einer bestehenden Campaign Classic v7-Umgebung ist noch nicht verfügbar.
>
>Wenden Sie sich an Ihr Account-Team, wenn Sie sich bezüglich Ihres Bereitstellungsmodells nicht sicher sind oder Fragen haben.

## Entfernte Funktionen{#gs-removed}

Zur Anpassung an die neue Architektur und das Implementierungsmodell von Campaign v8 sind einige frühere Funktionen von Campaign Classic v7 in Campaign v8 nicht mehr verfügbar.

* Coupons
* Webtracking
* Umfragen
* Social Marketing
* ACS Connector (Prime-Angebote)

