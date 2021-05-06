---
solution: Campaign Classic
product: campaign
title: Technischen Workflows- und Datenreplikation
description: Technischen Workflows- und Datenreplikation
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
translation-type: tm+mt
source-git-commit: 369ddafcc64fa418a479ab03092d3475f1c811b2
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 3%

---

# Technischen Workflows- und Datenreplikation

## Technische Workflows

Adobe Campaign verfügt über eine Reihe integrierter Technischen Workflows. Technischen Workflows führen Prozesse oder Aufträge regelmäßig auf dem Server aus.

Diese Workflows führen Datenbankwartungsoperationen durch, nutzen die Verfolgungsinformationen in den Versandlogs, erstellen wiederkehrende Kampagnen und mehr.

:arrow_upper_right: Die vollständige Liste der Technischen Workflows finden Sie in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)

Zusätzlich zu diesen Technischen Workflows setzt Kampagne v8 bei der Verwaltung der [Datenreplikation](#data-replication) auf bestimmte Technischen Workflows.

* **[!UICONTROL Replizieren]**
von Referenztabellen Dieser Arbeitsablauf führt die automatische Replikation von Referenztabellen durch, die in der lokalen Kampagne (Postgres) und in der Cloud-Datenbank ([!DNL Snowflake]) vorhanden sein müssen. Die Ausführung ist für jede Stunde und jeden Tag geplant. Wenn das Feld **lastModified** vorhanden ist, erfolgt die Replikation inkrementell, ansonsten wird die gesamte Tabelle repliziert. Die Reihenfolge der Tabellen im folgenden Array ist die Reihenfolge, in der der Replikationsarbeitsablauf verwendet wird.
* **[!UICONTROL Staging-]**
Daten replizierenDieser Arbeitsablauf repliziert Staging-Daten für einmalige Aufrufe. Die Ausführung ist für jede Stunde und jeden Tag geplant.
* **[!UICONTROL FFDA sofort freigeben]**\
   Dieser Arbeitsablauf führt eine sofortige Bereitstellung in der Cloud-Datenbank durch.
* **[!UICONTROL Replizieren von FFDA-Daten]**
sofort. Dieser Workflow repliziert die XS-Daten für ein bestimmtes Externe Konto.

Diese Technischen Workflows sind im Knoten **[!UICONTROL Administration > Produktion > Technischen Workflows > Volle FFDA-Replikation]** von Kampagne Explorer verfügbar.

**SOLLTEN WIR DAS HINZUFÜGEN? https://wiki.corp.adobe.com/display/neolane/Full+FDA+%3A%3A+Replication+strategy**


**Verwandte Themen**

:arrow_upper_right: Erfahren Sie, wie Sie mit Worflows in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows) beginnen

:bulb: Zugriff auf Datenaufbewahrungszeiträume in [diesem Abschnitt](../dev/datamodel-best-practices.md#data-retention)


## Datenreplikation{#data-replication}

Die Tabellen werden von der Kampagnen-Datenbank in die Cloud-Datenbank repliziert, indem die oben beschriebenen Workflows dediziert werden.[!DNL Snowflake]

Replikationsrichtlinien basieren auf der Größe der Tabelle. Einige Tabellen werden repliziert. Einige Tabellen werden in Echtzeit repliziert, andere werden stündlich repliziert. Einige Tabellen werden inkrementelle Aktualisierungen erhalten, wenn andere ersetzt werden.

| Namespace | Tabelle | Workflow-Replikation | Echtzeit-Replikation |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- | --------------------- |
| **XTK** | xtk:enum<br>xtk:enumValue<br>xtk:enumAlias<br>xtk:folder<br>xtk:formRendering<br>xtk:operator<br>xtk:group<br>xtk:report<br>Cube:olap be<br>xtk:olapDimension<br>xtk:olapMeasure<br>xtk:dictionaryString<br> | Ja (inkrementell) | Ja |
| **XTK** | xtk:opsecurity<br>xtk:rights<br>xtk:operatorGroup<br>xtk:reportHistory<br>xtk:reportRights | Ja (vollständig) | Ja |
| **NMS** | nms:budget<br>nms:Programm<br>nms:operation<br>nms:plan<br>nms:typologyRule<br>nms:typology<br>nms:extAccount<br>nms:deliveryMapping<br>nms:Versand (unmittelbare Replikation)<br>nms:nms Mitglied<br>nms:webApp<br>nms:trackingUrl (unmittelbare Replizierung)<br>nms:service<br>nms:offerEnv<br>nms:offerCategory<br>nms:offerSpace<br>nms:Angebot<br>nms:offerView<br>nms:Empfänger (inkrementell?)<br>nms:<br>groups:<br>dlvExclusionnms:stock | Ja (inkrementell) | Ja |
| **NMS** | nms:country<br>nms:localOrgUnit<br>nms:state<br>nms:suppressionAddress<br>nms:suppressionDomain<br>nms:Kategorie<br>nms:trackingUrlInfo<br>nms:webTrackingLog<br>nms:mobileApp a8/>nms:budgetCategory<br>nms:costType<br>nms:costCenter<br>nms:costStructure<br>nms:stockLine<br>nms:costLine<br>nms:costLine<br> | Ja (vollständig) | Ja |
| **NMS** | nms:address<br>nms:userAgent<br>nms:userAgentReject<br>nms:userAgentStats<br>nms:wideLogMsg<br>nms:wideLog<br>nms:trackingLog<br>nms:deliveryLogStats<br>nms ms:appSubscription<br>nms:proposition<br>nms:rcpGrpRel<br>nms:wideLogRcp<br>nms:excludeLogRcp<br>nms:trackingLogRcp<br>nms:proposition Rcp<br>nms:localValidationRcp<br>nms:Besucher<br>nms:wideLogVisitor<br>nms:trackingLogVisitor<br>nms:propositionVisitor<br>nms:webApp LogRcp<br>nms:appSubscriptionRcp<br>nms:wideLogAppSubRcp<br>nms:excludeLogAppSubRcp<br>nms:trackingLogAppSubRcp<br>nms ms:eventHisto<br>nms:wideLogEventHisto<br>nms:trackingLogEventHisto<br>nms:Abonnement<br>nms:subHisto<br>nms:trackingStats (nur Snowflake-Nutzung)<br>nms:tmpBroadcast (nur Snowflake verwenden)<br>nms:tmpBroadcastExclusion (nur Snowflake verwenden)<br>nms:tmpBroadcastPaper (nur Snowflake verwenden) | Nein | Nein |

