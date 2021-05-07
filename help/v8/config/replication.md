---
solution: Campaign
product: Adobe Campaign
title: Technischen Workflows- und Datenreplikation
description: Technischen Workflows- und Datenreplikation
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 3%

---

# Technischen Workflows- und Datenreplikation

## Technische Workflows

Adobe Campaign verfügt über eine Reihe integrierter Technischen Workflows. Technischen Workflows führen Prozesse oder Aufträge regelmäßig auf dem Server aus.

Diese Workflows führen Datenbankwartungsoperationen durch, nutzen die Verfolgungsinformationen in den Versandlogs, erstellen wiederkehrende Kampagnen und mehr.

:arrow_upper_right: Die vollständige Liste der Technischen Workflows finden Sie in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)

Zusätzlich zu diesen Technischen Workflows setzt Kampagne v8 bei der Verwaltung der [Datenreplikation](#data-replication) auf bestimmte Technischen Workflows.

* **[!UICONTROL Replizieren]**
von Referenztabellen Dieser Arbeitsablauf führt die automatische Replikation von integrierten Tabellen durch, die in der lokalen Kampagne (Postres) und in der Cloud-Datenbank ([!DNL Snowflake]) vorhanden sein müssen. Die Ausführung ist für jede Stunde und jeden Tag geplant. Wenn das Feld **lastModified** vorhanden ist, erfolgt die Replikation inkrementell, ansonsten wird die gesamte Tabelle repliziert. Die Reihenfolge der Tabellen im folgenden Array ist die Reihenfolge, in der der Replikationsarbeitsablauf verwendet wird.
* **[!UICONTROL Staging-]**
Daten replizierenDieser Arbeitsablauf repliziert Staging-Daten für einmalige Aufrufe. Die Ausführung ist für jede Stunde und jeden Tag geplant.
* **[!UICONTROL FFDA sofort freigeben]**\
   Dieser Arbeitsablauf führt eine sofortige Bereitstellung in der Cloud-Datenbank durch.
* **[!UICONTROL Replizieren von FFDA-Daten]**
sofort. Dieser Workflow repliziert die XS-Daten für ein bestimmtes Externe Konto.

Diese Technischen Workflows sind im Knoten **[!UICONTROL Administration > Produktion > Technischen Workflows > Volle FFDA-Replikation]** von Kampagne Explorer verfügbar. **Sie dürfen nicht geändert werden.**

## Datenreplikation{#data-replication}

Einige integrierte Tabellen werden mithilfe der oben beschriebenen dedizierten Workflows von der Kampagnen-Datenbank in die Cloud-Datenbank repliziert.[!DNL Snowflake]

Replikationsrichtlinien basieren auf der Größe der Tabellen. Einige Tabellen werden in Echtzeit repliziert, andere werden stündlich repliziert. Einige Tabellen werden inkrementelle Aktualisierungen erhalten, wenn andere ersetzt werden.

**Verwandte Themen**

:arrow_upper_right: Erfahren Sie, wie Sie mit Worflows in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows) beginnen

:bulb: Zugriff auf Datenaufbewahrungszeiträume in [diesem Abschnitt](../dev/datamodel-best-practices.md#data-retention)

