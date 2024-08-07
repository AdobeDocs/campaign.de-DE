---
title: Erste Schritte mit Adobe Campaign-Analyseberichten
description: Wie man Cubes erstellt
feature: Reporting
role: Data Engineer
level: Beginner
exl-id: f57f3074-981f-4bcf-9274-7908cd00a4a2
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 100%

---

# Erste Schritte mit Campaign-Analyseberichten {#gs-cube}

Adobe Campaign verfügt über ein intuitives Tool zur Daten-Exploration, um dynamische Berichte zu erstellen.

Verwenden Sie das Marketing-Analyse-Modul, um Daten zu analysieren und zu messen, Statistiken zu berechnen und die Berichterstellung und Berechnung zu vereinfachen und zu optimieren. Sie können Berichte erstellen, Zielgruppen-Populationen aufbauen und in Listen speichern, die in Adobe Campaign für Zielgruppenbestimmungs- oder Segmentierungsaufgaben verwendet werden können.

Dies ermöglicht es, die Kapazitäten zur Datenexploration und -analyse optimal zu nutzen. Gleichzeitig wird die Konfiguration der Berichte und Tabellen für den Endbenutzer vereinfacht: Es muss nur ein existierender, vollständig konfigurierter Cube bei der Bericht- oder Tabellenerstellung ausgewählt werden, um dessen Berechnungen, Kennzahlen und Statistiken zu übernehmen.

Cubes werden für die Erstellung bestimmter integrierter Berichte verwendet, einschließlich [Versandberichte](delivery-reports.md) (Versand-Tracking, Klicks, Öffnungen usw.).

Nach ihrer Erstellung und Konfiguration werden die Cubes in den Abfrage-Aktivitäten der Berichte und Webanwendungen genutzt. Sie können außerdem in Pivot-Tabellen verwendet und verändert werden.

Verwenden Sie das Marketing Analytics-Modul von Campaign, um:

1. Cubes und Indikatoren zu erstellen

   * Daten zu aggregieren und in einer Arbeitstabelle zu speichern, um Indikatoren auf der Grundlage von Benutzeranforderungen im Voraus zu berechnen,
   * das in den verschiedenen Berechnungen der Berichte und Abfragen bewegte Datenenvolumen zu reduzieren und dadurch die Berechnungszeit der Indikatoren deutlich zu optimieren,
   * den Zugriff auf die Daten zu vereinfachen und den Benutzern die Möglichkeit zu geben, die Daten (ob voraggregiert oder nicht) in Abhängigkeit von verschiedenen Dimensionen zu bearbeiten.

   Weiterführende Informationen hierzu finden Sie unter [Erstellen von Indikatoren](cube-indicators.md).

1. Pivot-Tabellen zu erstellen und Daten zu analysieren

   * berechnete Daten und konfigurierte Kennzahlen zu analysieren,
   * die anzuzeigenden Daten sowie ihren Anzeigemodus auszuwählen,
   * die verwendeten Kennzahlen und Indikatoren zu personalisieren,
   * Benutzern mit nichttechnischem Hintergrund interaktive Tools zur Analyse anzubieten.

   Weitere Informationen hierzu finden Sie unter [Verwenden von Cubes zur Datenanalyse](cube-tables.md).

1. Die Erstellung von Abfragen über in einem Cube berechnete und aggregierte Daten.
1. Die Identifizierung von Populationen und deren Referenzierung in Listen.

## Terminologie {#terminology}

Unten finden Sie eine Liste der spezifischen Begriffe bei der Arbeit mit Cubes.

* **Cube** – Ein Cube ist eine Darstellung mehrdimensionaler Informationen: Er bietet Endnutzern Strukturen für die interaktive Datenanalyse.

* **Faktentabelle/-schema** – Die Faktentabelle (oder das Faktenschema) enthält die Roh- oder Elementardaten, auf denen die Analysen basieren. Hierbei handelt es sich hauptsächlich um Tabellen mit großen Volumen (möglicherweise mit verknüpften Tabellen) und potenziell langen Berechnungen. Die Broadlog- oder die Bestelltabelle sind Beispiele für Faktentabellen.

* **Dimension** – Mit Dimensionen können Sie Daten in Gruppen unterteilen: Nach ihrer Erstellung dienen die Dimensionen als Analyseachsen. In den meisten Fällen werden für eine bestimmte Dimension mehrere Ebenen definiert. Für eine zeitliche Dimension beispielsweise sind die Ebenen Monate, Tage, Stunden, Minuten usw. Dieser Satz von Ebenen stellt die Dimensionshierarchie dar und ermöglicht verschiedene Ebenen der Datenanalyse.

* **Klassierung** – Für einige Felder können Sie eine Klassierung definieren, um Werte zu gruppieren und die Lesbarkeit der Informationen zu vereinfachen. Die Klassierung wird auf Ebenen angewendet. Es wird empfohlen, eine Klassierung zu definieren, wenn es viele verschiedene mögliche Werte gibt.

* **Kennzahlen** – Gängige Kennzahlen sind Summe, Durchschnitt, Maximum, Minimum, Standardabweichung etc. Kennzahlen können berechnet werden: Zum Beispiel bezeichnet die Annahmerate eines Angebots das Verhältnis der Anzahl der unterbreiteten Angebote verglichen mit der Anzahl der angenommenen Angebote.
