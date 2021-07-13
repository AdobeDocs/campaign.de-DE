---
product: Adobe Campaign
title: Neue Funktionen in Campaign v8
description: Wichtige Funktionen in Campaign v8 kennenlernen
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 100%

---

# Neue Funktionen in Adobe Campaign v8  {#ac-gs-what-is-new}

Adobe Campaign v8 bietet erhebliche Verbesserungen in den Bereichen Infrastruktur, Sicherheit, Zustellbarkeit und Monitoring. Durch die Nutzung von [[!DNL Snowflake]](https://www.snowflake.com/), einer Cloud-Datenbanktechnologie, verbessert Adobe Campaign seine Skalierbarkeit und Geschwindigkeit drastisch. So kann eine größere Anzahl von Kundenprofilen verwaltet werden und es werden deutlich höhere Versandraten und mehr Transaktionen pro Stunde erreicht.

Die wichtigsten Funktionen von Creative Designer ermöglichen Folgendes:

* **Geschwindigkeit und Skalierung**. Adobe Campaign v8 nutzt Cloud Database Manager, was dazu führt, dass Abfragen bis zu 200-mal schneller ausgeführt werden, eine Skalierung im Multi-Petabyte-Bereich möglich ist, die Anzahl der Nachrichten pro Stunde mit bis zu 20 Millionen/Stunde bzw. 1 Millionen/Stunde für transaktionale Nachrichten erhöht wird und bis zu 200 Millionen aktive Profile verwaltet werden können – mit dem Potenzial, 1 Milliarde zu erreichen.

* **Verbindungen zu Adobe Experience Platform**. Adobe Campaign v8 unterstützt Daten-Connectoren mit Adobe Experience Platform/RT-CDP, einem einheitlichen Kundenprofil und der nativen Integration mit Journey Orchestration. Diese Investitionen werden das Kundenerlebnis mit Adobe Campaign optimieren und neue Anwendungsfälle erschließen, wie z. B. die Möglichkeit, individualisierte Customer Journeys in Echtzeit zu Kampagnen hinzuzufügen.

* **Managed Cloud Services** Adobe Campaign v8 ist als marktführender Managed Cloud Services verfügbar und bietet proaktive Überwachung, rechtzeitige Benachrichtigung und Service-Governance. Marketer profitieren von einem agileren und skalierbaren Cross-Channel-Kampagnen-Management.

>[!CAUTION]
>
>Derzeit ist Campaign v8 **nur** als Managed Cloud Service verfügbar und kann nicht in On-Premise- oder Hybridumgebungen bereitgestellt werden.
>
>Die Migration aus einer bestehenden Campaign Classic v7-Umgebung ist noch nicht möglich.
>
>Wenden Sie sich an Ihr Account-Team, wenn Sie sich bezüglich Ihres Bereitstellungsmodells nicht sicher sind oder Fragen haben.

![](assets/home-page.png)

## Skalierung

Campaign v8 bietet eine End-to-End-Skalierung bei jedem Schritt des Prozesses, von der Zielgruppenbestimmung bis zum abschließenden Reporting:

* Skalieren Sie die Datenmenge, die Sie verarbeiten können (bis 8 TB)
* Skalieren Sie die Leistung von Abfragen für Segmentierung und Zielgruppenbestimmung, aber auch für Datenaufnahme und -abgabe
* Skalieren der Sendungsvorbereitung (von Stunden auf Minuten)

## Vereinfachung und Leistungssteigerung

Campaign v8 bietet das Konzept des **Full Federated Data Access** (FFDA): Alle Daten befinden sich nun remote in der Cloud-Datenbank.

Mit dieser neuen Architektur vereinfacht Campaign v8 die Datenverwaltung: Es wird kein Index in der Cloud-Datenbank benötigt. Sie müssen nur die Tabellen erstellen, die Daten kopieren und schon können Sie loslegen.

[!DNL Snowflake] ist die Campaign Cloud-Datenbank und bringt Ihnen Geschwindigkeit und Ausdauer: keine Überlastung der Systemaktivitätsspitzen.

Die Cloud-Datenbanktechnologie erfordert keine spezielle Wartung, um das Leistungsniveau zu gewährleisten.

## Integriertes Ökosystem

Sie können Campaign mit einer Reihe von leistungsstarken Adobe-Lösungen integrieren, wie z. B. Adobe Analytics, Adobe Journey Orchestration, Real-Time CDP und mehr.

Mit Journey-KI können Sie auch eine prädiktive Sendezeitoptimierung und ein prädiktives Interaktivitäts-Scoring konfigurieren und Öffnungsraten, Klicks und Umsätze steigern.

💡 [Weitere Informationen zu Integrationen mit Campaign](../connect/integration.md)

