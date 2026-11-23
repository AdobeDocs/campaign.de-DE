---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 17%
---
# sqlGetStringOnDataSource

Gibt eine Zeichenfolge zurück, die aus einer SQL-Abfrage für eine Datenquelle resultiert.

```text
sqlGetStringOnDataSource (query, dataSource [, value1, ... ])
```

## Parameter

**query** Die SQL-Abfrage.

**dataSource** Die Datenquelle.

**value1, …** Variablen der SQL-Abfrage.

## Rückgabewert

Die Textzeichenfolge, die der Abfrage entspricht.

## Bemerkungen

Der Parameter „data source“ wird definiert in [sqlExecOnDataSource(query, dataSource, value1, …)](f-sqlexecondatasource.md) Funktion Die optionalen Variablen, die als Parameter dieser Funktion festgelegt werden, sind in [sqlGetString(query, value1, …) definiert](f-sqlgetstring.md)

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
