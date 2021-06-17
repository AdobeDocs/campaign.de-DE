---
product: Adobe Campaign
title: Technische Workflows und Datenreplikation
description: Technische Workflows und Datenreplikation
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: ht
source-wordcount: '382'
ht-degree: 100%

---

# Technische Workflows und Datenreplikation

## Technische Workflows{#tech-wf}

Adobe Campaign verfügt über eine Reihe integrierter technischer Workflows. Technische Workflows führen Prozesse oder Aufträge aus und werden auf dem Server regelmäßig geplant.

Solche Workflows führen Operationen zur Datenbankwartung aus, nutzen die Tracking-Informationen in den Versand-Logs, erstellen wiederkehrende Kampagnen und mehr.

[!DNL :arrow_upper_right:] Eine vollständige Liste der technischen Workflows finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=de).


Zusätzlich zu diesen technischen Workflows setzt Campaign v8 bei der Verwaltung von [Datenreplikation](#data-replication) auf bestimmte technische Workflows.

* **[!UICONTROL Referenztabellen replizieren]**
Dieser Workflow sorgt für die automatische Replikation von integrierten Tabellen, die in der lokalen Campaign-Datenbank (Postgres) und in der Cloud-Datenbank ([!DNL Snowflake]) vorhanden sein müssen. Er ist so geplant, dass er Tag für Tag einmal stündlich ausgeführt wird. Wenn das Feld **lastModified** vorhanden ist, erfolgt die Replikation inkrementell, ansonsten wird die gesamte Tabelle repliziert. Die Reihenfolge der Tabellen im folgenden Array ist die Reihenfolge, die vom Replikations-Workflow verwendet wird.
* **[!UICONTROL Staging-Daten replizieren]**
Dieser Workflow repliziert Staging-Daten für einheitliche Aufrufe. Er ist so geplant, dass er Tag für Tag einmal stündlich ausgeführt wird.
* **[!UICONTROL FFDA sofort freigeben]**\
   Dieser Workflow sorgt für eine sofortige Bereitstellung in der Cloud-Datenbank.
* **[!UICONTROL FFDA-Daten sofort replizieren]**
Dieser Workflow repliziert die XS-Daten für ein bestimmtes externes Konto.

Diese technischen Workflows sind im Knoten **[!UICONTROL Administration > Betreibung > Technische Workflows > Vollständige FFDA-Replikation]** von Campaign Explorer verfügbar. **Sie dürfen nicht geändert werden.**

Bei Bedarf können Sie die Datensynchronisation manuell starten. Klicken Sie dazu mit der rechten Maustaste auf die Aktivität **Planung** und wählen Sie **Aufgabe(n) jetzt bearbeiten**.

## Datenreplikation{#data-replication}

Einige integrierte Tabellen werden mithilfe der oben beschriebenen dedizierten Workflows von der Campaign-Datenbank in die [!DNL Snowflake]-Cloud-Datenbank repliziert.

Replikationsrichtlinien richten sich nach der Größe der Tabellen. Einige Tabellen werden in Echtzeit repliziert, andere werden hingegen stündlich repliziert. Einige Tabellen erhalten inkrementelle Aktualisierungen, während andere ersetzt werden.

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

[!DNL :arrow_upper_right:] Lernen Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=de#automating-with-workflows) die ersten Schritte mit Workflows kennen.

[!DNL :bulb:] Erfahren Sie in [diesem Abschnitt](../dev/datamodel-best-practices.md#data-retention) mehr über Datenaufbewahrungsfristen.
