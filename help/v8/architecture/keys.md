---
title: Schlüsselverwaltung in Campaign
description: Erste Schritte mit der Schlüsselverwaltung
feature: Configuration, FFDA
role: Developer
level: Intermediate
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
TQID: 'https://experienceleague.adobe.com/DfuZXr3sXnip35yNPRvZBDZ1BVb6dJFWYA2j90vc7RE'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
    internal-label: Schemas
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: 702a1f63-4da5-5981-83b3-4d5b14e90420
    internal-label: FFDA
subfeature_v2:
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
    internal-label: PI
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 9d4ec9f8454acd6a939221075251c265a1ffd672
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 55%
---
# Schlüsselverwaltung und Eindeutigkeit {#key-management}

Im Kontext einer [Enterprise (FFDA)-Bereitstellung](enterprise-deployment.md) ist der Primärschlüssel ein Universally Unique IDentifier (UUID), d. h. eine Zeichenfolge. Um diese UUID zu erstellen, muss das Hauptelement des Schemas die Attribute **autouid** und **autopk** enthalten, die auf **true** gesetzt sind.

Adobe Campaign v8 verwendet [!DNL Snowflake] als Hauptdatenbank. Die verteilte Architektur der [!DNL Snowflake] bietet keine Mechanismen zur Gewährleistung der Eindeutigkeit eines Schlüssels in einer Tabelle. Die Endbenutzer sind dafür verantwortlich, die Konsistenz der Schlüssel in der Adobe Campaign-Datenbank sicherzustellen.

Die Vermeidung von Duplikaten bei Schlüsseln, insbesondere bei Primärschlüsseln, ist zur Wahrung der relationalen Datenbankkonsistenz unverzichtbar. Duplikate bei Primärschlüsseln führen zu Problemen mit Workflow-Aktivitäten für die Datenverwaltung, wie der **Abfrage**, der **Abstimmung**, dem **Daten-Update** und anderen. Dies ist entscheidend für die Definition geeigneter Abstimmkriterien bei der Aktualisierung [!DNL Snowflake] Tabellen.


>[!CAUTION]
>
>Duplizierte Schlüssel sind nicht auf UUIDs beschränkt. Dies kann mit IDs passieren, einschließlich benutzerdefinierter Schlüssel, die in benutzerdefinierten Tabellen erstellt werden.


## Unicity Service{#unicity-service}

Unicity Service ist eine Cloud Database Manager-Komponente, mit der Benutzer die Integrität der Einschränkungen eindeutiger Schlüssel in Cloud-Datenbanktabellen wahren und überwachen können. Dies hilft Ihnen zu verhindern, dass doppelte Schlüssel eingefügt werden.

Da in der Cloud-Datenbank keine Einschränkungen hinsichtlich der Einheitlichkeit erzwungen werden, reduziert Unicity Service das Risiko, bei der Verwaltung von Daten mit Adobe Campaign Duplikate einzufügen.

### Eindeutigkeits-Workflow{#unicity-wf}

Unicity Service verfügt über den speziellen, integrierten Workflow **[!UICONTROL Warnhinweise für Eindeutigkeit]**, der Eindeutigkeitseinschränkungen überwacht und Alarm schlägt, wenn Duplikate entdeckt werden.

Dieser technische Workflow ist im Knoten **[!UICONTROL Administration > Produktion > Technische Workflows > Vollständige FFDA-Eindeutigkeit]** von Campaign Explorer verfügbar. **Er darf nicht geändert werden**.

Dieser Workflow überprüft alle benutzerdefinierten und integrierten Schemata, um duplizierte Zeilen zu erkennen.

![Workflow Warnhinweise für Eindeutigkeit (ffdaUnicity): Schemaprüfungen, doppelte Zeilen erkannt, Test-, Warnhinweis-, End- und Bereinigungsaktivitäten](assets/unicity-alerting-wf.png)

Wenn der Workflow **[!UICONTROL Warnhinweise für Eindeutigkeit]** (ffdaUnicity) doppelte Schlüssel entdeckt, werden diese zu einer bestimmten **Audit-Unicity**-Tabelle hinzugefügt, die den Namen des Schemas, den Typ des Schlüssels, die Anzahl der betroffenen Zeilen und das Datum enthält. Über den Knoten **[!UICONTROL Administration > Audit > Schlüsseleindeutigkeit]** können Sie auf doppelte Schlüssel zugreifen.

![Eindeutigkeitsliste für Schlüssel mit Schema-ID, Schlüsseldefinition, Schlüsseltyp, doppeltem Wert, doppelter Anzahl, Erstellungsdatum](assets/unicity-table.png)

Als Datenbankadministrator können Sie eine SQL-Aktivität verwenden, um die Duplikate zu entfernen, oder sich an die Kundenunterstützung von Adobe wenden, um weitere Anleitungen zu erhalten.

### Warnhinweise{#unicity-wf-alerting}

Wenn doppelte Schlüssel erkannt werden, wird eine bestimmte Benachrichtigung an die Benutzergruppe **[!UICONTROL Workflow-Verantwortliche]** gesendet. Inhalt und Zielgruppe dieses Warnhinweises können in der Aktivität **Warnhinweis** des Workflows **[!UICONTROL Warnhinweise für Eindeutigkeit]** geändert werden.

![Warnaktivität in Warnhinweisen für Eindeutigkeit, die der Gruppe der Workflow-Verantwortlichen mit den doppelten Schlüsseln zugewiesen ist](assets/wf-alert-activity.png)


## Zusätzliche Schutzmaßnahmen {#duplicates-guardrails}

Campaign verfügt über eine Reihe neuer Schutzmaßnahmen, um das Einfügen doppelter Schlüssel in die [!DNL Snowflake]-Datenbank zu verhindern.

>[!NOTE]
>
>Diese Schutzmaßnahmen sind ab Campaign v8.3 verfügbar. Informationen zum Überprüfen Ihrer Version finden Sie in [&#x200B; Kompatibilitätsmatrix für Campaign v8](../start/compatibility-matrix.md)

### Versandvorbereitung {#remove-duplicates-delivery-preparation}

Adobe Campaign entfernt während der Versandvorbereitung automatisch jede doppelte UUID aus einer Zielgruppe. Dieser Mechanismus verhindert, dass bei der Vorbereitung eines Versands ein Fehler auftritt. Als Endbenutzer können Sie diese Informationen in den Versandlogs überprüfen: Einige Empfänger können aufgrund doppelter Schlüssel aus der Hauptzielgruppe ausgeschlossen werden. In diesem Fall wird folgender Warnhinweis angezeigt: `Exclusion of duplicates (based on the primary key or targeted records)`.

![Versandlog mit der Zeile Ausschluss von Duplikaten (basierend auf dem Primärschlüssel der Zieldatensätze), hervorgehoben durch einen Pfeil](assets/exclusion-duplicates-log.png)

### Aktualisieren von Daten in einem Workflow {#duplicates-update-data}

Im Kontext einer [Enterprise (FFDA)-Bereitstellung &#x200B;](enterprise-deployment.md) Sie keinen internen Schlüssel (UUID) als Feld auswählen, um Daten in einem Workflow zu aktualisieren.

![Datenaktivität mit der Feldauswahl für Empfänger (nms) aktualisieren:recipient wobei kein internes Schlüsselfeld ausgewählt werden kann](assets/update-data-no-internal-key.png)

### Abfrage eines Schemas mit Duplikaten {#query-with-duplicates}

Wenn ein Workflow mit der Ausführung einer Abfrage eines Schemas beginnt, prüft Adobe Campaign, ob ein doppelter Eintrag in der [Audit-Unicity-Tabelle) &#x200B;](#unicity-wf). In diesem Fall protokolliert der Workflow eine Warnung, da der nachfolgende Vorgang mit den duplizierten Daten möglicherweise das Workflow-Ergebnis beeinflusst.

![Workflow-Protokoll mit der Warnung Eindeutigkeitsbeschränkung verletzt. Duplizierte Daten auf Schema-Nms gefunden:recipient](assets/query-with-duplicates.png)

Diese Prüfung wird in den folgenden Workflow-Aktivitäten durchgeführt:

* Abfrage
* Inkrementelle Abfrage
* Liste lesen


>[!NOTE]
>
>Wenn Sie von einer anderen Campaign-Version wechseln, müssen Sie unbedingt Duplikate entfernen, Fehler beheben und Daten bereinigen, um eine Beeinträchtigung Ihrer Umstellung zu vermeiden.
