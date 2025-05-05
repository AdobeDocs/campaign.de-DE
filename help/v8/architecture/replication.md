---
title: Datenreplikation
description: Technische Workflows und Datenreplikation
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: b8f774ce507cff67163064b6bd1341b31512c08f
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 10%

---


# Datenreplikation {#wf-data-replication}

## Funktionsprinzip

Im Kontext einer [Enterprise (FFDA)-Bereitstellung](enterprise-deployment.md) stellt die Datenreplikation sicher, dass die beiden Datenbanken, die lokale Campaign-Datenbank (PostgreSQL) und die Cloud-Datenbank ([!DNL Snowflake]), parallel betrieben werden und in Echtzeit synchronisiert bleiben.

Die Cloud-Datenbank ([!DNL Snowflake]) ist für die Verarbeitung großer Datenstapel optimiert, z. B. für die Aktualisierung von 1 Million Adressen. Gleichzeitig ist die lokale Campaign-Datenbank (PostgreSQL) besser für Einzeloperationen oder Operationen mit geringem Volumen geeignet, z. B. die Aktualisierung einer einzelnen Testadresse. Die Synchronisierung erfolgt automatisch und transparent im Hintergrund, sodass Daten in der lokalen Campaign-Datenbank (PostgreSQL) in Echtzeit in die Cloud-Datenbank ([!DNL Snowflake]) dupliziert werden, sodass beide Datenbanken synchronisiert bleiben. Die Datensynchronisation umfasst Schemata und Tabellen sowie Daten.

➡️ [Im Video erfahren Sie, wie die Datenreplikation funktioniert](#video)

## Replikationsmodi {#modes}

Die Datenreplikation kann je nach Anwendungsfall in verschiedenen Modi erfolgen.

* **On-the-fly-Replikation** Ermöglicht die Verarbeitung von Fällen, in denen eine Duplizierung in Echtzeit erforderlich ist. Sie beruht auf bestimmten technischen Threads, um Daten sofort für Anwendungsfälle wie die Erstellung einer Diffusion oder die Aktualisierung einer Testadresse zu replizieren.
* **Geplante Replikation** wird verwendet, wenn keine sofortige Synchronisierung erforderlich ist. Die geplante Replikation verwendet spezifische [technische Workflows](#workflows) die stündlich zur Synchronisierung von Daten ausgeführt werden, z. B. Typologieregeln.

## Replikationsrichtlinien

Replikationsrichtlinien definieren, wie viele Daten aus einer Tabelle der lokalen Campaign-Datenbank (PostgreSQL) repliziert werden. Diese Richtlinien hängen von der Größe der Tabelle und dem spezifischen Anwendungsfall ab. Einige Tabellen werden inkrementelle Aktualisierungen aufweisen, während andere vollständig repliziert werden. Es gibt drei Haupttypen von Replikationsrichtlinien:

* **XS**: Diese Richtlinie wird für Tabellen mit relativ kleinen Größen verwendet. Die gesamte Tabelle wird in einer einzigen Aufnahme repliziert. Durch inkrementelle Replikation werden dieselben Daten nicht wiederholt repliziert, indem ein Zeitstempelzeiger verwendet wird, der nur die letzten Änderungen repliziert.
* **SingleRow**: Diese Richtlinie repliziert jeweils nur eine Zeile. Sie wird in der Regel für die spontane Replikation von aktuellen Campaign-Objekten und zugehörigen Objekten verwendet.
* **SomeRows**: Diese Richtlinie wurde zum Replizieren einer begrenzten Teilmenge von Daten mithilfe von Abfragedefinitionen oder Filtern entwickelt. Sie wird für größere Tabellen verwendet, bei denen eine selektive Replikation erforderlich ist.

## Replikations-Workflows {#workflows}

Campaign v8 stützt sich bei der Verwaltung geplanter Datenreplikationen auf bestimmte technische Workflows. Diese technischen Workflows sind im Knoten **[!UICONTROL Administration > Produktion > Technische Workflows > Vollständige FFDA-Replikation]** von Campaign Explorer verfügbar. **Sie dürfen nicht geändert werden.**

Technische Workflows führen Prozesse oder Aufträge aus, die regelmäßig auf dem Server geplant werden. Die vollständige Liste der technischen Workflows ist auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=de){target="_blank"} aufgeführt.

Folgende technische Workflows sorgen für die Datenreplikation:

| Technischer Workflow | Beschreibung |
|------|-----------|
| **[!UICONTROL Referenztabellen replizieren]** (ffdaReplicateReferenceTables) | Automatische Replikation von integrierten Tabellen, die in der lokalen Campaign-Datenbank (PostgreSQL) und in der Cloud-Datenbank ([!DNL Snowflake]) vorhanden sein müssen. Er ist so geplant, dass er Tag für Tag einmal stündlich ausgeführt wird. Wenn **lastModified**-Feld vorhanden ist, erfolgt die Replikation inkrementell, ansonsten wird die gesamte Tabelle repliziert. |
| **[!UICONTROL Staging-Daten replizieren]** (ffdaReplicateStagingData) | Repliziert Staging-Daten für einheitliche Aufrufe. Er ist so geplant, dass er Tag für Tag einmal stündlich ausgeführt wird. |
| **[!UICONTROL FFDA sofort bereitstellen]** (ffdaDeploy) | Sofortige Bereitstellung in der Cloud-Datenbank |
| **[!UICONTROL FFDA-Daten sofort replizieren]** (ffdaReplicate) | Repliziert die XS-Daten für ein bestimmtes externes Konto. |

Bei Bedarf können Sie die Datensynchronisation manuell starten. Klicken Sie dazu mit der rechten Maustaste auf die Aktivität **Planung** und wählen Sie **Ausstehende Aufgabe(n) jetzt ausführen**.

Zusätzlich zum integrierten technischen Workflow **Referenztabellen replizieren** können Sie mithilfe einer der folgenden Methoden die Datenreplikation in Ihren Workflows erzwingen

+++So erzwingen Sie die Datenreplikation

* Fügen Sie eine bestimmte **JavaScript-Code**-Aktivität mit dem folgenden Code hinzu:

  ```
  nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
  ```

  ![](assets/jscode.png)

* Fügen Sie eine bestimmte **nlmodule**-Aktivität mit dem folgenden Befehl hinzu:

  ```
  nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
  ```

  ![](assets/nlmodule.png)

+++

<br/>

>[!NOTE]
>
>Die Ad-hoc-Replikation wird von bestimmten technischen Threads statt von Workflows verarbeitet. Die Konfiguration für diesen Modus wird in der Datei „serverConf.xml“ verwaltet. Sie können die Datei serverConf.xml so konfigurieren, dass sie spezifischen Anwendungsfällen entspricht, z. B. dass XS-Tabellen inkrementell repliziert werden, anstatt vollständig. Weitere Informationen erhalten Sie vom Adobe-Support.

## APIs

APIs ermöglichen die Replikation von benutzerdefinierten und vorkonfigurierten Daten aus der lokalen Campaign-Datenbank (PostgreSQL) in die Cloud-Datenbank ([!DNL Snowflake]). Mit diesen APIs können Sie vordefinierte Workflows umgehen und die Replikation für bestimmte Anforderungen anpassen, z. B. für das Replizieren benutzerdefinierter Tabellen.

Beispiel:

```
var dataSource = "nms:extAccount:ffda";
var xml = xtk.builder.CopyXxlData(
    <params dataSource={dataSource} policy="xs">
        <srcSchema name="cus:recipient"/>
    </params>
);
```

## Replikations-Warteschlangen

Wenn gleichzeitig große Mengen an Replikationsanfragen auftreten, können in der Cloud-Datenbank ([!DNL Snowflake]) Leistungsprobleme auftreten, die durch Sperren auf Tabellenebene während ZUSAMMENFÜHRUNGSVORGÄNGEN verursacht werden. Um dies zu umgehen, gruppieren zentralisierte Replikations-Workflows Anfragen in Warteschlangen.

Jede Warteschlange wird von einem technischen Workflow verarbeitet, der die Replikation für eine bestimmte Tabelle verwaltet und ausstehende Anfragen als einen einzigen MERGE-Vorgang ausführt. Diese Workflows werden alle 20 Sekunden ausgelöst, um neue Replikationsanfragen zu verarbeiten:

| Technischer Workflow | Beschreibung |
|------|-----------|
| **NmsDelivery-Warteschlange replizieren** (ffdaReplicateQueueDelivery) | Warteschlange für die `nms:delivery`. |
| **NmsDlvExclusion-Warteschlange replizieren** (ffdaReplicateQueueDlvExclusion) | Warteschlange für die `nms:dlvExclusion`. |
| **NmsDlvMidRemoteIdRel-Warteschlange replizieren** (ffdaReplicateQueueDlvMidRemoteIdRel) | Warteschlange für die `nms:dlvRemoteIdRel`. |
| **NmsTrackingUrl-Warteschlange replizieren** (ffdaReplicateQueueTrackingUrl)<br/>**NmsTrackingUrl-Warteschlange gleichzeitig replizieren** (ffdaReplicateQueueTrackingUrl_2) | Gleichzeitige Warteschlangen für die `nms:trackingUrl`-Tabelle, wobei zwei Workflows verwendet werden, um die Effizienz durch die Verarbeitung von Anfragen basierend auf verschiedenen Prioritäten zu verbessern. |

## Anleitungsvideo {#video}

In diesem Video werden die wichtigsten Konzepte vorgestellt, welche Datenbanken Adobe Campaign v8 verwendet, warum Daten repliziert werden, welche Daten repliziert werden und wie der Replikationsprozess funktioniert.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)

Weitere Tutorials zur Client-Konsole von Campaign v8 [hier](https://experienceleague.adobe.com/de/docs/campaign-learn/tutorials/overview).
