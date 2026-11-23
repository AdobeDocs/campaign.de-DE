---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 18%
---
# queryWithTypes

Führt eine SQL-Abfrage vom Typ SELECT mit der Spaltenspezifikation aus.

```text
queryWithTypes (command, types [, value1, ... ])
```

## Parameter

**Befehl** SQL-Befehl.

**types** Tabelle mit dem Spaltentyp

**value1, …** Befehlsvariablen.

## Rückgabewert

Ein Cursor, mit dem Sie das Abfrageergebnis iterieren können.

## Bemerkungen

Warnung: Im Gegensatz zu dem, was im Abschnitt Funktionen angegeben ist, ist die Funktion queryWithTypes in WebApp nicht verfügbar. Die Funktion ist identisch mit [query](m-dbengine-query.md) mit dem hinzugefügten Spaltentyp. In den meisten Fällen wird der Spaltentyp nicht verwendet, da er automatisch abgeleitet werden kann. Aus diesem Grund sollte [Abfrage](m-dbengine-query.md) bevorzugt werden. In einigen Fällen, insbesondere bei Spalten vom Typ &quot;Oracle&quot; und „Datum“, kann es jedoch erforderlich sein, den Typ explizit anzugeben. Spaltentypen sind Zeichenfolgen in der folgenden Liste:

* Zeichenfolge
* datetime
* Datum
* time
* timespan
* double
* float
* Boolesch
* Byte
* Kurz
* Lang
* int64
* Memo
* Klecks
* link
* Klasse

Beispiel:

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)",
                     ["long", "string", "datetime"],
                     1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

Der Operator muss über „SQL“-Rechte verfügen, um diese Funktion verwenden zu können. Andernfalls wird eine Ausnahme ausgelöst.

## Funktionen

**Methode der Klasse:** [DBEngine](c-dbengine.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
