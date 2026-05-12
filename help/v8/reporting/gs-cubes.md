---
title: Erste Schritte mit Adobe Campaign-Analyseberichten
description: Wie man Cubes erstellt
feature: Reporting
role: Developer
level: Beginner
exl-id: f57f3074-981f-4bcf-9274-7908cd00a4a2
TQID: https://experienceleague.adobe.com/rWE0PPnY4uRgpGy9a-cucZFSGnRyaI9IwwjJFmvYY9s
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 529
ht-degree: 80%

---

# Erste Schritte mit Campaign-Analyseberichten {#gs-cube}

Adobe Campaign verfügt über ein intuitives Tool zur Daten-Exploration, um dynamische Berichte zu erstellen.

Verwenden Sie das Marketing-Analyse-Modul, um Daten zu analysieren und zu messen, Statistiken zu berechnen und die Berichterstellung und Berechnung zu vereinfachen und zu optimieren. Sie können Berichte erstellen, Zielgruppen-Populationen aufbauen und in Listen speichern, die in Adobe Campaign für Zielgruppenbestimmungs- oder Segmentierungsaufgaben verwendet werden können.

Dies ermöglicht es, die Kapazitäten zur Datenexploration und -analyse optimal zu nutzen. Gleichzeitig wird die Konfiguration der Berichte und Tabellen für den Endbenutzer vereinfacht: Es muss nur ein existierender, vollständig konfigurierter Cube bei der Bericht- oder Tabellenerstellung ausgewählt werden, um dessen Berechnungen, Kennzahlen und Statistiken zu übernehmen.

Cubes werden für die Erstellung bestimmter integrierter Berichte verwendet, einschließlich [Versandberichte](delivery-reports.md) (Versand-Tracking, Klicks, Öffnungen usw.).

Nachdem sie erstellt und konfiguriert wurden, werden Cubes in Berichtsabfragefeldern und Web-Anwendungen verwendet. Sie können in Pivot-Tabellen verwendet und bearbeitet werden.

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

* **Dimension** – Mit Dimensionen können Sie Daten in Gruppen unterteilen: Nach ihrer Erstellung dienen die Dimensionen als Analyseachsen. In den meisten Fällen werden für eine bestimmte Dimension mehrere Ebenen definiert. Für eine zeitliche Dimension sind die Ebenen beispielsweise Monate, Tage, Stunden, Minuten usw. Dieser Satz von Ebenen stellt die Dimensionshierarchie dar und ermöglicht verschiedene Ebenen der Datenanalyse.

* **Klassierung** – Für einige Felder können Sie eine Klassierung definieren, um Werte zu gruppieren und die Lesbarkeit der Informationen zu vereinfachen. Die Klassierung wird auf Ebenen angewendet. Es wird empfohlen, eine Klassierung zu definieren, wenn es viele verschiedene mögliche Werte gibt.

* **Kennzahl** - Die häufigsten Kennzahlen sind Summe, Durchschnitt, Maximum, Minimum, Standardabweichung usw. Kennzahlen können berechnet werden: Zum Beispiel ist die Annahmerate eines Angebots das Verhältnis der Anzahl der unterbreiteten Angebote im Vergleich zur Anzahl der angenommenen Angebote.
