---
title: Wechsel von Campaign Classic v7 zu Campaign v8
description: Lernen Sie die Unterschiede zwischen Campaign Classic v7 und Campaign v8 kennen.
feature: Overview
role: User
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 98%

---

# Wechsel von [!DNL Campaign Classic] v7 zu [!DNL Campaign] v8{#gs-matrix}

Als früherer [!DNL Campaign Classic] v7-Benutzer sollten Sie bei der Interaktion mit [!DNL Adobe Campaign] keine größeren Änderungen feststellen. Die meisten Änderungen in v8 sind nicht sichtbar, mit Ausnahme kleiner Änderungen, die in der Benutzeroberfläche und in den Konfigurationsschritten erkennbar sind.

>[!AVAILABILITY]
>
>* Derzeit ist Campaign v8 **nur** als Managed Cloud Service verfügbar und kann nicht in On-Premise- oder Hybridumgebungen bereitgestellt werden. [Weitere Informationen](#cloud-services)
>
>* Die automatische Migration aus einer bestehenden Campaign Classic v7-Umgebung ist noch nicht verfügbar.


## Managed Cloud Services{#cloud-services}

Adobe Campaign v8 ist als **Managed Cloud Service** verfügbar.

Adobe Campaign Managed Cloud Services bietet eine Managed Cloud Services-Plattform für die Konzeption kanalübergreifender Kundenerlebnisse. In dieser Umgebung können Kampagnen visuell orchestriert, Interaktionen in Echtzeit verwaltet und Kampagnen kanalübergreifend ausgeführt werden. Weitere Informationen zu Campaign Managed Cloud Services finden Sie auf der [Produktbeschreibungsseite](https://helpx.adobe.com/de/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Das neue Angebot kombiniert erstklassige Dienstleistungen mit proaktiver Aufsicht und rechtzeitigen Warnmeldungen und konzentriert sich auf drei Bereiche:

* **Cloud-Agilität** – Automatisierung durch Adobe mit optimierten, standardisierten Cloud-Bereitstellungen für eine prognostizierbarere Performance, größere Agilität und verbesserte Self-Service-Produktivität.
* **Service-Erlebnis** – proaktive Verfügbarkeit, Kapazität und Performance-Überwachung und -reaktion, um Unterbrechungen zu verhindern, Störungen schneller zu beheben und den Service regelmäßig zu überprüfen, und so kontinuierliche Verbesserungen zu gewährleisten.
* **Profundes Expertenwissen zu Campaign** – hochaffiner Service von erfahrenen Customer-Engineering-Teams, um funktionale, technische oder Zustellbarkeitserfordernisse zu erfüllen, das Bereitstellungsrisiko zu reduzieren und das Änderungsmanagement zu verbessern.

Als früherer [!DNL Campaign Classic]-Benutzer sollten Sie beachten, dass die meisten Funktionen von [!DNL Campaign Classic] v7 auch in [!DNL Campaign] v8 verfügbar sind, mit Ausnahme einiger weniger, die in [diesem Abschnitt](#gs-removed) aufgeführt sind.

>Die neue Cloud-Architektur ermöglicht es Campaign, Prozesse zu optimieren, Kosten zu reduzieren, Risiken zu verwalten und die Datensicherheit zu verbessern. Die Campaign v8-Umgebung verfügt über eine dedizierte Virtual Private Cloud (VPC), die schon vorkonfiguriert ist.


## Hybridarchitektur {#hybrid-archi}

Campaign v8 basiert auf einer **Hybridarchitektur**. Wenn Sie von Campaign Classic v7 wechseln, beachten Sie, dass alle Sendungen den Mid-Sourcing-Server durchlaufen.

Dies hat folgende Auswirkungen:

* Das interne Routing in Campaign v8 ist **nicht möglich** und das externe Konto wurde entsprechend deaktiviert.
* Der Versandstatus wird nicht sofort aktualisiert – In der Marketing-Instanz wird ein technischer Prozess ausgeführt, der den Versandstatus zeitnah aktualisiert.


Weitere Informationen zum Senden von Testsendungen für Transaktionsnachrichten beim Übergang von v7 zu einer anderen Version finden Sie auf [dieser Seite](../send/transactional-template.md#transition-from-v7).


## [!DNL Campaign] und [!DNL Snowflake] {#ac-gs-snowflake}

In der [Bereitstellung „Enterprise (FFDA)“](../architecture/enterprise-deployment.md) kann [!DNL Adobe Campaign] v8 mit zwei Datenbanken verwendet werden: einer lokalen [!DNL Campaign]-Datenbank für Echtzeit-Messaging und Einzelabfragen und das Schreiben über APIs sowie einer [!DNL Snowflake]-Cloud-Datenbank für die Kampagnenausführung, für Batch-Abfragen und die Workflow-Ausführung.

Campaign v8 Enterprise bietet das Konzept des **Full Federated Data Access** (FFDA): Alle Daten befinden sich nun entfernt in der Cloud-Datenbank. Mit dieser neuen Architektur vereinfacht die Campaign v8 Enterprise (FFDA)-Bereitstellung die Datenverwaltung: Es wird kein Index in der Cloud-Datenbank benötigt. Sie müssen nur die Tabellen erstellen und die Daten kopieren und schon können Sie loslegen. Die Cloud-Datenbanktechnologie erfordert keine spezielle Wartung für eine garantierte Performance.

Weitere Informationen zur Architektur von [!DNL Campaign] v8 finden Sie auf [dieser Seite](../architecture/architecture.md).


## Verwenden Sie Ihre Adobe ID, um eine Verbindung mit Campaign herzustellen.{#adobe-id}

Campaign-Benutzende stellen über ihre Adobe ID eine Verbindung her. Es wird die gleiche Adobe ID verwendet, um alle Ihre Adobe-Pläne und -Produkte für alle Adobe Experience Cloud-Lösungen mit einem einzigen Konto zu verknüpfen.

Informationen zum Herstellen einer Verbindung mit [!DNL Campaign] finden Sie auf [dieser Seite](connect.md).

## Analysieren von Daten mit Cubes{#adobe-reporting}

Verwenden Sie das Modul &quot;Marketing Analytics&quot;, um Daten zu analysieren und zu messen, Statistiken zu berechnen und die Berichterstellung und -berechnung zu vereinfachen und zu optimieren. Erstellen Sie außerdem Berichte und Zielpopulationen: Nach der Identifizierung werden sie in Listen gespeichert, die in Adobe Campaign verwendet werden können (für Zielgruppenbestimmung, Segmentierung usw.).

In Adobe Campaign v8 sind Cube-Berichte optimiert und bieten bessere Skalierungsfunktionen als Campaign Classic v7. In diesem spezifischen Bereitstellungsmodell gelten frühere Einschränkungen bei Cubes nicht für Campaign v8. Weitere Informationen zu Cubes finden Sie in [diesem Abschnitt](../../v8/reporting/gs-cubes.md).

## Nicht verfügbare Funktionen{#gs-unavailable-features}

Beachten Sie, dass einige Funktionen im Kontext einer [Enterprise (FFDA)-Bereitstellung](../architecture/enterprise-deployment.md) von Campaign nicht verfügbar sind, z. B.:

* Verwaltung von Marketing-Ressourcen
* Coupons
* Webtracking
* Umfragen

## Nicht unterstützte Funktionen{#gs-removed}

Einige historische Funktionen von Campaign Classic v7 werden in Campaign v8 nicht mehr unterstützt, wie etwa:

* Social-Media-Marketing mit Facebook
* ACS-Connector (Prime-Angebote)
* Integration mit LDAP
* Anmelden mit Benutzer/Kennwort
* Hybrid-/On-Premise-Bereitstellungsmodelle


>[!NOTE]
>
>Einige nicht verfügbare oder nicht unterstützte Funktionen sind möglicherweise weiterhin in der Benutzeroberfläche sichtbar.
