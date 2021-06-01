---
product: Adobe Campaign
title: Neue Funktionen in Campaign v8
description: Weitere Infos zu wichtigen Funktionen
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 62%

---

# Neue Funktionen in Adobe Campaign v8 {#ac-gs-what-is-new}

Adobe Campaign v8 bietet erhebliche Verbesserungen in den Bereichen Infrastruktur, Sicherheit, Zustellbarkeit und Überwachung. Durch die Nutzung von [[!DNL Snowflake]](https://www.snowflake.com/), einer Cloud-Datenbanktechnologie, verbessert Adobe Campaign erheblich den Umfang und die Geschwindigkeit, da eine größere Anzahl von Kundenprofilen sowie deutlich höhere Zustellraten und Transaktionen pro Stunde verwaltet werden können.

Die wichtigsten Funktionen von Creative Designer ermöglichen Folgendes:

* **Geschwindigkeit und Skalierung**. Adobe Campaign v8 nutzt Cloud Database Manager, was dazu führt, dass Abfragen bis zu 200-mal schneller ausgeführt werden, eine Skalierung im Multi-Petabyte-Bereich möglich ist, die Anzahl der Nachrichten pro Stunde mit bis zu 20 Millionen/Stunde bzw. 1 Millionen/Stunde für transaktionale Nachrichten erhöht wird und bis zu 200 Millionen aktive Profile verwaltet werden können – mit dem Potenzial, 1 Milliarde zu erreichen.

* **Verbindungen zu Adobe Experience Platform**. Adobe Campaign v8 unterstützt Daten-Connectoren mit Adobe Experience Platform/RT-CDP, einem einheitlichen Kundenprofil und der nativen Integration mit Journey Orchestration. Diese Investitionen werden das Kundenerlebnis mit Adobe Campaign optimieren und neue Anwendungsfälle erschließen, wie z. B. die Möglichkeit, individualisierte Customer Journeys in Echtzeit zu Kampagnen hinzuzufügen.

* **Managed Cloud Services** Adobe Campaign v8 ist als marktführender Managed Cloud Services verfügbar und bietet proaktive Überwachung, rechtzeitige Benachrichtigung und Service-Governance. Der Wert für den Marketingexperten ist eine flexiblere und skalierbarere kanalübergreifende Kampagnenverwaltung.

>[!CAUTION]
>
>Derzeit ist Campaign v8 **nur** als verwalteter Cloud Service verfügbar und kann nicht in On-Premise- oder Hybridumgebungen bereitgestellt werden.
>
>Die Migration aus einer bestehenden Campaign Classic v7-Umgebung ist noch nicht verfügbar.
>
>Wenden Sie sich an Ihr Account-Team, wenn Sie sich bezüglich Ihres Bereitstellungsmodells nicht sicher sind oder Fragen haben.


## Skala

Campaign v8 bietet umfassende Skalierung für jeden Schritt des Prozesses, von der Zielgruppenbestimmung bis zur endgültigen Berichterstellung:

* Skalieren Sie die Datenmenge, die Sie verarbeiten können (bis 8 TB)
* Skalieren Sie die Leistung von Abfragen für Segmentierung und Zielgruppenbestimmung, aber auch für Datenaufnahme und -abgabe
* Versandvorbereitung skalieren (von Stunden auf Minuten)

## Vereinfachung und Leistungssteigerung

Campaign v8 bietet das Konzept des **Full Federated Data Access** (FDA, Voll verbundener Datenzugriff): Alle Daten befinden sich nun dezentral in der Cloud-Datenbank.

Mit dieser neuen Architektur vereinfacht Campaign v8 die Datenverwaltung: In der Cloud-Datenbank ist kein Index erforderlich. Sie müssen nur die Tabellen erstellen, die Daten kopieren und schon können Sie loslegen.

[!DNL Snowflake] ist die Campaign Cloud-Datenbank. Sie ermöglicht Geschwindigkeit und Ausdauer: keine Überlastung der Spitzen der Systemaktivität.

Die Cloud-Datenbanktechnologie erfordert keine spezielle Wartung, um das Leistungsniveau zu gewährleisten.

## Integriertes Ökosystem

Sie können Campaign mit einer Reihe von leistungsstarken Adobe-Lösungen integrieren, wie z. B. Adobe Analytics, Workfront, Journey Orchestration, Real-Time CDP und mehr.

Mit Journey-KI können Sie auch eine prädiktive Sendezeitoptimierung und ein prädiktives Interaktivitäts-Scoring konfigurieren und Öffnungsraten, Klicks und Umsätze steigern.

[!DNL :bulb:] [Weitere Informationen zu Integrationen mit Campaign](../connect/integration.md)

