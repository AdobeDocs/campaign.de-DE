---
title: Übergang von Campaign Classic v7 zu Campaign v8
description: Unterschiede zwischen Campaign Classic v7 und Campaign v8 verstehen
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 63e109f31706880a1723dfd0c611835842e39083
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Übergang von [!DNL Campaign Classic] v7 nach [!DNL Campaign] v8{#gs-matrix}

Als früherer [!DNL Campaign Classic] v7-Benutzer sollten Sie bei der Interaktion mit [!DNL Adobe Campaign] keine größeren Änderungen feststellen. Die meisten Änderungen in v8 sind nicht sichtbar, mit Ausnahme kleiner Änderungen, die in der Benutzeroberfläche und in den Konfigurationsschritten erkennbar sind.

>[!AVAILABILITY]
>
>* Derzeit ist Campaign v8 **nur** als Managed Cloud Service verfügbar und kann nicht in On-Premise- oder Hybridumgebungen bereitgestellt werden. [Weitere Informationen](#cloud-services)
>
>* Die Migration aus einer bestehenden Campaign Classic v7-Umgebung ist noch nicht möglich.



## Verwaltete Cloud Services{#cloud-services}

Adobe Campaign v8 ist als **verwalteter Cloud-Service** verfügbar.

Adobe Campaign Managed Cloud Services bietet eine Managed Services-Plattform für die Konzeption kanalübergreifender Kundenerlebnisse und eine Umgebung für die visuelle Kampagnenorchestrierung, Interaktionsverwaltung in Echtzeit und die kanalübergreifende Ausführung. Weitere Informationen zu Campaign Managed Cloud Services finden Sie im Abschnitt [Produktbeschreibungsseite](https://helpx.adobe.com/de/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}..

Das neue Angebot kombiniert erstklassige Dienstleistungen mit proaktiver Aufsicht und rechtzeitigen Warnmeldungen und konzentriert sich auf drei Bereiche:

* **Cloud-Agilität** – Automatisierung durch Adobe mit optimierten, standardisierten Cloud-Implementierungen für eine prognostizierbarere Leistung, größere Agilität und verbesserte Self-Service-Produktivität.
* **Service-Erlebnis** – proaktive Verfügbarkeit, Kapazität und Leistungsüberwachung und -reaktion, um Unterbrechungen zu verhindern, Störungen schneller zu beheben und den Service regelmäßig zu überprüfen, und so kontinuierliche Verbesserungen zu gewährleisten.
* **Profundes Expertenwissen zu Campaign** – hochaffiner Service von erfahrenen Customer-Engineering-Teams, um funktionale, technische oder Zustellbarkeitserfordernisse zu erfüllen, das Implementierungsrisiko zu reduzieren und das Änderungsmanagement zu verbessern.

Als früherer [!DNL Campaign Classic]-Benutzer sollten Sie beachten, dass die meisten Funktionen von [!DNL Campaign Classic] v7 auch in [!DNL Campaign] v8 verfügbar sind, mit Ausnahme einiger weniger, die in [diesem Abschnitt](#gs-removed) aufgeführt sind. Weitere Änderungen werden in zukünftigen Versionen enthalten sein. [Weitere Informationen finden Sie in diesem Abschnitt](#gs-unavailable-features)

>[!NOTE]
>
> Campaign v8 basiert auf einer Hybridarchitektur. Wenn Sie von Campaign Classic v7 wechseln, beachten Sie, dass alle Sendungen den Mid-Sourcing-Server durchlaufen. [Weitere Informationen](../architecture/architecture.md)
>
> Infolgedessen ist internes Routing in Campaign v8 **nicht möglich** und das externe Konto wurde entsprechend deaktiviert.


## [!DNL Campaign] und [!DNL Snowflake] {#ac-gs-snowflake}

Campaign v8 arbeitet mit [!DNL Snowflake] zusammen. 

In seiner [Enterprise (FFDA)-Implementierung](../architecture/enterprise-deployment.md) kann [!DNL Adobe Campaign] v8 mit zwei Datenbanken verwendet werden: einer lokalen [!DNL Campaign]-Datenbank für Echtzeit-Messaging und Einzelabfragen und das Schreiben über APIs sowie einer Cloud-[!DNL Snowflake]-Datenbank für die Kampagnenausführung, für Batch-Abfragen und die Workflow-Ausführung.

Campaign v8 Enterprise bietet das Konzept des **Full Federated Data Access** (FFDA): Alle Daten befinden sich nun entfernt in der Cloud-Datenbank. Mit dieser neuen Architektur vereinfacht die Campaign v8 Enterprise (FFDA)-Implementierung die Datenverwaltung: Es wird kein Index in der Cloud-Datenbank benötigt. Sie müssen nur die Tabellen erstellen, die Daten kopieren und starten. Die Cloud-Datenbanktechnologie erfordert keine spezielle Wartung, um das Leistungsniveau zu gewährleisten.

![](../assets/do-not-localize/glass.png) Weitere Informationen zur Architektur von [!DNL Campaign] v8 finden Sie auf [dieser Seite](../architecture/architecture.md).


## Verwenden Sie Ihre Adobe ID, um eine Verbindung mit Campaign herzustellen.{#adobe-id}

Campaign-Benutzer stellen nur über ihre Adobe ID eine Verbindung her. Dieselbe Adobe ID wird verwendet, um alle Ihre Adobe-Pläne und -Produkte für alle Adobe Experience Cloud-Lösungen mit einem einzigen Konto zu verknüpfen.

![](../assets/do-not-localize/glass.png) Erfahren Sie auf [dieser Seite](connect.md), wie Sie eine Verbindung zu [!DNL Campaign] herstellen können. 

## Analysieren von Daten mit Cubes{#adobe-reporting}

Verwenden Sie das Modul &quot;Marketing Analytics&quot;, um Daten zu analysieren und zu messen, Statistiken zu berechnen und die Berichterstellung und -berechnung zu vereinfachen und zu optimieren. Erstellen Sie außerdem Berichte und Zielgruppen: Nach der Identifizierung werden sie in Listen gespeichert, die in Adobe Campaign verwendet werden können (für Targeting, Segmentierung usw.).

Adobe Campaign-Cube-Berichte sind optimiert und bieten bessere Skalierungsfunktionen als Campaign Classic v7. Frühere Einschränkungen für Cubes gelten nicht für Campaign v8.

## Nicht verfügbare Funktionen{#gs-unavailable-features}

Bitte beachten Sie, dass in dieser Version von Campaign einige Funktionen nicht verfügbar sind, z. B.:

* Verwaltung von Marketing-Ressourcen
* Hybrid-/On-Premise-Implementierungsmodelle


## Nicht unterstützte Funktionen{#gs-removed}

Zur Anpassung an die neue Architektur und das Implementierungsmodell von Campaign v8 werden einige frühere Funktionen von Campaign Classic v7 in Campaign v8 nicht mehr unterstützt, wie z. B.:

* Coupons
* Webtracking
* Umfragen
* Social Marketing
* ACS-Connector (Prime-Angebote)
* Integration mit LDAP
* Anmelden mit Benutzer/Kennwort

>[!NOTE]
>
>Einige nicht verfügbare oder nicht unterstützte Funktionen sind möglicherweise weiterhin in der Benutzeroberfläche sichtbar.
