---
title: Technische Workflows und Datenreplikation
description: Technische Workflows und Datenreplikation
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Technische Workflows und Datenreplikation {#wf-data-replication}

## Technische Workflows {#tech-wf}

Im Kontext einer [Enterprise (FFDA)-Bereitstellung](enterprise-deployment.md) bietet Adobe Campaign eine Reihe integrierter technischer Workflows. Technische Workflows führen Prozesse oder Vorgänge aus und werden auf dem Server regelmäßig geplant.

Solche Workflows führen Operationen zur Datenbankwartung aus, nutzen die Tracking-Informationen in den Versand-Logs, erstellen wiederkehrende Kampagnen und mehr.

Die vollständige Liste der technischen Workflows ist auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=de) aufgeführt{target="_blank"}.

Zusätzlich zu diesen technischen Workflows setzt Campaign v8 bei der Verwaltung von [Datenreplikation](#data-replication) auf bestimmte technische Workflows.

* **[!UICONTROL Referenztabellen replizieren]**
Dieser Workflow sorgt für die automatische Replikation von integrierten Tabellen, die in der lokalen Campaign-Datenbank (Postgres) und in der Cloud-Datenbank ([!DNL Snowflake]) vorhanden sein müssen. Er ist so geplant, dass er Tag für Tag einmal stündlich ausgeführt wird. Wenn das Feld **lastModified** vorhanden ist, erfolgt die Replikation inkrementell, ansonsten wird die gesamte Tabelle repliziert. Die Reihenfolge der Tabellen im folgenden Array ist die Reihenfolge, die vom Replikations-Workflow verwendet wird.
* **[!UICONTROL Staging-Daten replizieren]**
Dieser Workflow repliziert Staging-Daten für einheitliche Aufrufe. Er ist so geplant, dass er Tag für Tag einmal stündlich ausgeführt wird.
* **[!UICONTROL FFDA sofort bereitstellen]**\
  Dieser Workflow sorgt für eine sofortige Bereitstellung in der Cloud-Datenbank.
* **[!UICONTROL FFDA-Daten sofort replizieren]**
Dieser Workflow repliziert die XS-Daten für ein bestimmtes externes Konto.

Diese technischen Workflows sind im Knoten **[!UICONTROL Administration > Produktion > Technische Workflows > Vollständige FFDA-Replikation]** von Campaign Explorer verfügbar. **Sie dürfen nicht geändert werden.**

Bei Bedarf können Sie die Datensynchronisation manuell starten. Klicken Sie dazu mit der rechten Maustaste auf die Aktivität **Planung** und wählen Sie **Ausstehende Aufgabe(n) ausführen**.

## Datenreplikation {#data-replication}

Einige integrierte Tabellen werden mithilfe der oben beschriebenen dedizierten Workflows von der Campaign-Datenbank in die [!DNL Snowflake]-Cloud-Datenbank repliziert.

Erfahren Sie, welche Datenbanken Adobe Campaign v8 verwendet, warum Daten repliziert werden, welche Daten repliziert werden und wie der Replikationsprozess funktioniert.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)


### Datenreplikationsrichtlinien {#data-replication-policies}

Replikationsrichtlinien richten sich nach der Größe der Tabellen. Einige Tabellen werden in Echtzeit repliziert, andere hingegen stündlich. Einige Tabellen erhalten inkrementelle Aktualisierungen, während andere ersetzt werden.

Zusätzlich zum integrierten technischen Workflow **Referenztabellen replizieren** können Sie die Datenreplikation in Ihren Workflows erzwingen.

Sie haben folgende Möglichkeiten:

* Fügen Sie eine bestimmte Aktivität des Typs **JavaScript-Code** mit dem folgenden Code hinzu:

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* Fügen Sie eine bestimmte **nlmodule**-Aktivität mit dem folgenden Befehl hinzu:

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)


**Verwandte Themen**

* [Erfahren Sie mehr über die ersten Schritte mit Workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=de){target="_blank"}

* [Datenspeicherungszeiträume](../dev/datamodel-best-practices.md#data-retention)
