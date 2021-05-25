---
solution: Campaign v8
product: Adobe Campaign
title: Neue Funktionen in Campaign v8
description: Weitere wichtige Funktionen
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 1%

---

# Neue Funktionen in Adobe Campaign v8 {#ac-gs-what-is-new}

Adobe Campaign v8 bietet wichtige Verbesserungen in den Bereichen Infrastruktur, Sicherheit, Zustellbarkeit und Überwachung. Durch die Nutzung von [[!DNL Snowflake]](https://www.snowflake.com/), einer Cloud-Datenbanktechnologie, verbessert Adobe Campaign erheblich den Umfang und die Geschwindigkeit, da eine größere Anzahl von Kundenprofilen sowie deutlich höhere Zustellraten und Transaktionen pro Stunde verwaltet werden können.

Die wichtigsten Funktionen von Creative Designer ermöglichen Folgendes:

* **Geschwindigkeit und Skalierung**. Adobe Campaign v8 nutzt den Cloud Database Manager, was zu Abfragen mit bis zu 200-facher Leistung, einer Multipetabyte-Skalierung, einer erhöhten Anzahl von Nachrichten pro Stunde mit bis zu 20 MB/h oder 1,5 MB/h für Transaktionsnachrichten führt, und verwaltet bis zu 200 M aktive Profile mit der Möglichkeit, 1B zu erreichen.

* **Verbindungen zur Adobe Experience Platform**. Adobe Campaign v8 unterstützt Data Connectors mit Adobe Experience Platform/RT-CDP, Unified Customer Profile und die native Integration mit Journey Orchestration. Durch diese Investitionen wird das Kundenerlebnis in der Adobe Campaign optimiert und neue Anwendungsfälle freigesetzt, wie z. B. die Möglichkeit, Kampagnen individuelle Echtzeit-Journey hinzuzufügen.

* **Verwaltete Cloud Services**. Adobe Campaign v8 ist als erstklassige Managed Cloud Services mit proaktiver Aufsicht, zeitnaher Warnmeldung und Dienstverwaltung verfügbar. Der Wert für den Marketingexperten ist eine flexiblere und skalierbarere kanalübergreifende Kampagnenverwaltung.

>[!CAUTION]
>
>Derzeit ist Campaign v8 **nur** als verwalteter Cloud Service verfügbar und kann nicht in On-Premise- oder Hybridumgebungen bereitgestellt werden.
>
>Die Migration aus einer bestehenden Campaign Classic v7-Umgebung ist noch nicht verfügbar.


## Skala

Campaign v8 bietet umfassende Skalierung für jeden Schritt des Prozesses, von der Zielgruppenbestimmung bis zur endgültigen Berichterstellung:

* Skalieren Sie das Datenvolumen, das Sie verarbeiten können (bis zu 8 TB).
* Skalieren der Leistung von Abfragen für Segmentierung und Targeting, aber auch für Datenerfassung und Ausstieg
* Versandvorbereitung skalieren (von Stunden auf Minuten)

## Vereinfachung und Leistungssteigerung

Campaign v8 bietet das Konzept **Vollständiger Federated Data Access** (FDA): Alle Daten befinden sich jetzt an Remote-Standorten in der Cloud-Datenbank.

Mit dieser neuen Architektur vereinfacht Campaign v8 die Datenverwaltung: In der Cloud-Datenbank ist kein Index erforderlich. Sie müssen nur die Tabellen erstellen, die Daten kopieren und starten.

[!DNL Snowflake] ist die Campaign Cloud-Datenbank. Sie ermöglicht Geschwindigkeit und Ausdauer: keine Überlastung der Spitzen der Systemaktivität.

Die Cloud-Datenbanktechnologie erfordert keine spezifische Wartung, um das Leistungsniveau zu gewährleisten.

## Integriertes Ökosystem

Sie können Campaign mit einer Reihe leistungsstarker Adobe-Lösungen integrieren, z. B.: Adobe Analytics, Workfront, Journey Orchestration, Echtzeit-Kundendatenplattform und mehr.

Sie können auch mithilfe von Journey AI eine prädiktive Sendezeitoptimierung und eine prädiktive Interaktionsbewertung konfigurieren und Öffnungsraten, Klicks und Umsätze steigern.

:bulb: [Weitere Informationen zu Campaign-Integrationen](../connect/integration.md)

