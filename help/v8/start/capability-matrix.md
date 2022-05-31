---
title: Funktionsmatrix Campaign Classic v7/Campaign v8
description: Unterschiede zwischen Campaign Classic v7 und Campaign v8 verstehen
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 0c01b0a597e54ae93dd581ccba6f19b2ff13f956
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 100%

---

# [!DNL Campaign Classic] v7- und [!DNL Campaign] v8-Funktionen{#gs-matrix}

Als früherer [!DNL Campaign Classic] v7-Benutzer sollten Sie bei der Interaktion mit [!DNL Adobe Campaign] keine größeren Änderungen feststellen. Die meisten Änderungen in v8 sind nicht sichtbar, mit Ausnahme kleiner Änderungen, die in der Benutzeroberfläche und in den Konfigurationsschritten erkennbar sind.

Adobe Campaign v8 ist als **verwalteter Cloud-Service** verfügbar. Das neue Angebot kombiniert erstklassige Dienstleistungen mit proaktiver Aufsicht und rechtzeitigen Warnmeldungen und konzentriert sich auf drei Bereiche:

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

Campaign v8 arbeitet mit [!DNL Snowflake] zusammen. Es stehen zwei Implementierungsmodelle zur Verfügung.

![](../assets/do-not-localize/glass.png) Weitere Informationen zur Architektur von [!DNL Campaign] v8 finden Sie auf [dieser Seite](../architecture/architecture.md).


## Verwenden Sie Ihre Adobe ID, um eine Verbindung mit Campaign herzustellen.{#adobe-id}

Campaign-Benutzer stellen über ihre Adobe ID eine Verbindung her. Dieselbe Adobe ID wird verwendet, um alle Ihre Adobe-Pläne und -Produkte für alle Adobe Experience Cloud-Lösungen mit einem einzigen Konto zu verknüpfen.

![](../assets/do-not-localize/glass.png) Erfahren Sie auf [dieser Seite](connect.md), wie Sie eine Verbindung zu [!DNL Campaign] herstellen können. 

## Analysieren von Daten mit Cubes{#adobe-reporting}

Verwenden Sie das Modul &quot;Marketing Analytics&quot;, um Daten zu analysieren und zu messen, Statistiken zu berechnen und die Berichterstellung und -berechnung zu vereinfachen und zu optimieren. Erstellen Sie außerdem Berichte und Zielgruppen: Nach der Identifizierung werden sie in Listen gespeichert, die in Adobe Campaign verwendet werden können (für Targeting, Segmentierung usw.).

Adobe Campaign-Cube-Berichte sind optimiert und bieten bessere Skalierungsfunktionen als Campaign Classic v7. Frühere Einschränkungen für Cubes gelten nicht für Campaign v8.

## Datenquelle ändern {#change-data-source}

Campaign v8 bietet eine zusätzliche Workflow-Aktivität für die Zielgruppenbestimmung: **[!UICONTROL Datenquelle ändern]**.

Die Aktivität **[!UICONTROL Datenquelle ändern]** ermöglicht es Ihnen, die Datenquelle des Workflows **[!UICONTROL Arbeitstabelle]** zu ändern, um Daten aus verschiedenen Datenquellen wie FDA, FFDA und lokalen Datenbanken zu verwalten.

![](../assets/do-not-localize/glass.png) Erfahren Sie auf [dieser Seite](../config/workflows.md#change-data-source-activity) mehr über die Aktivität **[!UICONTROL Datenquelle ändern]**.

## Nicht verfügbare Funktionen{#gs-unavailable-features}

Bitte beachten Sie, dass in dieser Version von Campaign einige Funktionen nicht verfügbar sind, z. B.:

* Verwaltung von Marketing-Ressourcen
* Hybrid-/On-Premise-Implementierungsmodelle

>[!CAUTION]
>
>* Derzeit ist Campaign v8 **nur** als Managed Cloud Service verfügbar und kann nicht in On-Premise- oder Hybridumgebungen bereitgestellt werden.
>
>* Die Migration aus einer bestehenden Campaign Classic v7-Umgebung ist noch nicht möglich.
>
>* Wenden Sie sich an Ihren Adobe-Kundenberater, wenn Sie sich bezüglich Ihres Implementierungsmodells nicht sicher sind oder Fragen haben.


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
