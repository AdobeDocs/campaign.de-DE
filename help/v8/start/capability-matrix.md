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
ht-degree: 49%

---

# [!DNL Campaign Classic] v7- und [!DNL Campaign] v8-Funktionen{#gs-matrix}

Frühere [!DNL Campaign Classic] Benutzer von v7 sollten keine großen Störungen in der Art und Weise erwarten, mit der Sie normalerweise interagieren [!DNL Adobe Campaign]. Die meisten Änderungen in v8 sind nicht sichtbar, mit Ausnahme kleiner Änderungen, die in der Benutzeroberfläche und in den Konfigurationsschritten erkennbar sind.

Adobe Campaign v8 ist als **Verwalteter Cloud Service**. Das neue Angebot kombiniert erstklassige Dienstleistungen mit proaktiver Aufsicht und rechtzeitiger Warnmeldung und konzentriert sich auf drei Bereiche:

* **Cloud-Agilität** - Automatisierung nach Adobe mit optimierten, standardisierten Cloud-Bereitstellungen für eine vorhersehbarere Leistung, größere Agilität und verbesserte Self-Service-Produktivität.
* **Service-Erlebnis** — proaktive Verfügbarkeit, Kapazität und Leistungsüberwachung und Reaktion, um Unterbrechungen zu verhindern, Störungen schneller zu beheben und den Service regelmäßig auf kontinuierliche Verbesserung zu überprüfen.
* **Expertenwissen zu Deep Campaign** - hochaffiner Service von erfahrenen Customer Engineering-Teams, um funktionale, technische oder Zustellbarkeitserfordernisse zu erfüllen, das Bereitstellungsrisiko zu reduzieren und das Änderungsmanagement zu verbessern.

Frühere [!DNL Campaign Classic] -Benutzer, beachten Sie, dass die meisten [!DNL Campaign Classic] v7-Funktionen sind verfügbar mit [!DNL Campaign] v8, mit Ausnahme eines kleinen Satzes, aufgeführt in [diesem Abschnitt](#gs-removed). Weitere Änderungen werden in zukünftigen Versionen enthalten sein. [Weitere Informationen finden Sie in diesem Abschnitt](#gs-unavailable-features)

>[!NOTE]
>
> Campaign v8 basiert auf einer Hybridarchitektur. Wenn Sie von Campaign Classic v7 wechseln, beachten Sie, dass alle Sendungen den Mid-Sourcing-Server durchlaufen. [Weitere Informationen](../architecture/architecture.md)
>
> Infolgedessen ist internes Routing in Campaign v8 **nicht möglich** und das externe Konto wurde entsprechend deaktiviert.


## [!DNL Campaign] und [!DNL Snowflake] {#ac-gs-snowflake}

Campaign v8 funktioniert mit [!DNL Snowflake]. Es stehen zwei Bereitstellungsmodelle zur Verfügung.

![](../assets/do-not-localize/glass.png) Weitere Informationen zur Architektur von [!DNL Campaign] v8 finden Sie auf [dieser Seite](../architecture/architecture.md).


## Verwenden Sie Ihre Adobe ID, um eine Verbindung mit Campaign herzustellen.{#adobe-id}

Campaign-Benutzer stellen über ihre Adobe ID eine Verbindung her. Dieselbe Adobe ID wird verwendet, um alle Ihre Adoben und Produkte, die mit einem Konto verknüpft sind, für alle Adobe Experience Cloud-Lösungen zu speichern.

![](../assets/do-not-localize/glass.png) Erfahren Sie auf [dieser Seite](connect.md), wie Sie eine Verbindung zu [!DNL Campaign] herstellen können. 

## Daten mit Cubes analysieren{#adobe-reporting}

Verwenden Sie das Modul Marketing Analytics, um Daten zu analysieren und zu messen, Statistiken zu berechnen, die Berichterstellung und -berechnung zu vereinfachen und zu optimieren. Erstellen Sie außerdem Berichte und erstellen Sie Zielgruppen: Nach der Identifizierung werden sie in Listen gespeichert, die in Adobe Campaign verwendet werden können (Targeting, Segmentierung usw.).

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
>* Wenden Sie sich an Ihren Adobe-Kundenbetreuer, wenn Sie sich bezüglich Ihres Bereitstellungsmodells nicht sicher sind oder Fragen haben.


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
