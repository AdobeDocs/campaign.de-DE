---
title: Schlüsselverwaltung in Campaign
description: Erste Schritte mit der Schlüsselverwaltung
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 19%

---

# Schlüsselverwaltung und Eindeutigkeit {#key-management}

Im Kontext eines [Enterprise (FFDA)-Bereitstellung](enterprise-deployment.md), ist der Primärschlüssel eine Universally Unique IDentifier (UUID), eine Zeichenfolge für Zeichen. Um diese UUID zu erstellen, muss das Hauptelement des Schemas die Attribute **autouid** und **autopk** enthalten, die auf **true** gesetzt sind.

Adobe Campaign v8 verwendet [!DNL Snowflake] als Hauptdatenbank. Die verteilte Architektur der [!DNL Snowflake] -Datenbank bietet keinen Mechanismus, um die Einheitlichkeit eines Schlüssels in einer Tabelle sicherzustellen: Endbenutzer sind für die Schlüsselkonsistenz innerhalb der Adobe Campaign-Datenbank verantwortlich.

Die Vermeidung von Duplikaten bei Schlüsseln, insbesondere bei Primärschlüsseln, ist zur Wahrung der relationalen Datenbankkonsistenz unverzichtbar. Duplikate bei Primärschlüsseln führen zu Problemen mit Workflow-Aktivitäten für die Datenverwaltung, wie **Abfrage**, **Abstimmung**, **Daten-Update** und anderen. Dies ist wichtig, um bei der Aktualisierung geeignete Abstimmkriterien festzulegen [!DNL Snowflake] -Tabellen.


>[!CAUTION]
>
>Duplizierte Schlüssel sind nicht auf UUIDs beschränkt. Duplikate können bei IDs auftreten, einschließlich benutzerdefinierter Schlüssel, die in benutzerdefinierten Tabellen erstellt werden.


## Unicity Service{#unicity-service}

Unicity Service ist eine Cloud Database Manager-Komponente, mit der Benutzer die Integrität eindeutiger Schlüsseleinschränkungen in Cloud-Datenbanktabellen wahren und überwachen können. Dies hilft Ihnen zu verhindern, dass doppelte Schlüssel eingefügt werden.

Da in der Cloud-Datenbank keine Einschränkungen hinsichtlich der Einheitlichkeit erzwungen werden, reduziert Unicity Service das Risiko, bei der Datenverwaltung mit Adobe Campaign Duplikate einzufügen.

### Arbeitsablauf für die Einheitlichkeit{#unicity-wf}

Unicity Service verfügt über eine eigene **[!UICONTROL Unizitätswarnung]** integrierter Workflow zur Überwachung von Unitätsbeschränkungen und zur Warnung bei der Erkennung von Duplikaten.

Dieser technische Workflow ist im Abschnitt **[!UICONTROL Administration > Betreibung > Technische Workflows > Vollständige FFDA-Unität]** Knoten des Campaign-Explorers. **Es darf nicht geändert werden**.

Dieser Workflow überprüft alle benutzerdefinierten und integrierten Schemata, um duplizierte Zeilen zu erkennen.

![](assets/unicity-alerting-wf.png)

Wenn die Variable **[!UICONTROL Unizitätswarnung]** Der Workflow (ffdaUnicity) erkennt einige doppelte Schlüssel und wird zu einem bestimmten **Prüfungleichheit** -Tabelle, die den Namen des Schemas, den Typ des Schlüssels, die Anzahl der betroffenen Zeilen und das Datum enthält. Sie können auf duplizierte Schlüssel über die **[!UICONTROL Administration > Audit > Schlüsselunität]** Knoten.

![](assets/unicity-table.png)

Als Datenbankadministrator können Sie eine SQL-Aktivität verwenden, um die Duplikate zu entfernen, oder sich an die Kundenunterstützung von Adobe wenden, um weitere Informationen zu erhalten.

### Warnung{#unicity-wf-alerting}

Eine spezifische Benachrichtigung wird an die **[!UICONTROL Workflow-Supervisoren]** Benutzergruppe, wenn duplizierte Schlüssel erkannt werden. Inhalt und Audience dieses Warnhinweises können im Abschnitt **Warnhinweis** der **[!UICONTROL Unizitätswarnung]** Arbeitsablauf.

![](assets/wf-alert-activity.png)


## Zusätzliche Limits{#duplicates-guardrails}

Campaign verfügt über eine Reihe neuer Limits, um das Einfügen eines duplizierten Schlüssels in [!DNL Snowflake] Datenbank.

>[!NOTE]
>
>Diese Limits sind ab Campaign v8.3 verfügbar. Informationen zur Prüfung Ihrer Version finden Sie unter [diesem Abschnitt](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

### Versandvorbereitung{#remove-duplicates-delivery-preparation}

Adobe Campaign entfernt während der Versandvorbereitung automatisch jede duplizierte UUID aus einer Audience. Dieser Mechanismus verhindert, dass bei der Versandvorbereitung Fehler auftreten. Als Endbenutzer können Sie diese Informationen in den Versandlogs überprüfen: Manche Empfänger können wegen eines duplizierten Schlüssels aus der Hauptzielgruppe ausgeschlossen werden. In diesem Fall wird folgender Warnhinweis angezeigt: `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/exclusion-duplicates-log.png)

### Daten in einem Workflow aktualisieren{#duplicates-update-data}

Im Kontext eines [Enterprise (FFDA)-Bereitstellung](enterprise-deployment.md)können Sie keinen internen Schlüssel (UUID) als Feld auswählen, um Daten in einem Workflow zu aktualisieren.

![](assets/update-data-no-internal-key.png)

Bei Verwendung des expliziten Abstimmschlüssels muss die Variable **Daten aktualisieren** Die Aktivität stellt anhand dieses Schlüssels automatisch die Einheitlichkeit des Zielschemas sicher, indem sie:

1. Eingehende Daten deduplizieren (aus der Transition)
1. Daten mit Zieltabelle deduplizieren (Zusammenführen)


![](assets/update-data-deduplicate.png)

>[!CAUTION]
>
>Diese Schutzmaßnahme gilt nur mit der Option **[!UICONTROL Über Abstimmschlüssel]**.


### Abfrage eines Schemas mit Duplikaten{#query-with-duplicates}

Wenn ein Workflow mit der Ausführung der Abfrage eines Schemas beginnt, prüft Adobe Campaign, ob duplizierte Datensätze im [Tabelle &quot;Audit Unicity&quot;](#unicity-wf). In diesem Fall protokolliert der Workflow eine Warnung, da der nachfolgende Vorgang für die duplizierten Daten möglicherweise das Workflow-Ergebnis beeinflusst.

![](assets/query-with-duplicates.png)

Diese Prüfung wird in den folgenden Workflow-Aktivitäten durchgeführt:

* Abfrage
* Inkrementelle Abfrage
* Liste lesen