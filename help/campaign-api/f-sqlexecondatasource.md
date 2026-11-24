---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 12%
---
# sqlExecOnDataSource

Führt ein SQL-Script in einer Datenquelle aus.

```text
sqlExecOnDataSource (query, dataSource [, value1, ... ])
```

## Parameter

**query** Die SQL-Abfrage.

**dataSource** Die Datenquelle.

**value1, …** Variablen der SQL-Abfrage.

## Rückgabewert

Die Anzahl der Datensätze, die in einem UPDATE- oder INSERT SQL-Befehl aktualisiert oder eingefügt wurden.

## Bemerkungen

Die zulässigen Werte für die Datenquelle können sein:

* &quot;&quot; oder „Standard“ verweist auf die Adobe Campaign-Datenbank

* „nms:extAccount:internalName“ verweist auf eine Datenquelle, die in den externen Adobe Campaign-Konten (FDA) definiert ist

* „name“ (Name der Datenquelle) verweist auf eine Datenquelle, die in der Konfigurationsdatei der Instanz (config-instance.xml) in der folgenden Form definiert ist:

  ```xml
                   <dataStore hosts="*" lang="">
        <dataSource name="datasourcename">
          <dbcnx encrypted="" login="" password=""
                 provider="" server=""/>
        </dataSource>
      </dataStore>
  ```

Beispiel:

```javascript
sqlExecOnDataSource("UPDATE XtkOption SET sStringValue = $(sz) WHERE sName = $(sz)", oracleExternalDB, 'WdbcOptions_TableSpaceWork_nms:extAccount:' + sExtAccount)
```

Die optionalen Variablen, die als Parameter dieser Funktion festgelegt werden, sind in [sqlGetString(query, value1, …) definiert](f-sqlgetstring.md)

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
