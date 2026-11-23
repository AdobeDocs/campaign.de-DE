---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 20%
---
# sqlSelect

Führt eine SQL-Abfrage aus und gibt das Ergebnis als XML-Dokument zurück.

```text
sqlSelect (format, query [, dataSource ])
```

## Parameter

**format** Eine durch Kommas getrennte Zeichenfolge, die das Format der erwarteten Daten als Name beschreibt:type\[:length\] type list docName, \[fieldXPath:type,\]\*

**query** Die SQL-Abfrage.

**dataSource** Die Datenquelle.

## Rückgabewert

Ein XML-Objekt mit einer Liste von Elementen für jede Zeile des Abfrageergebnisses.

## Bemerkungen

Beispiel:

```javascript
var res = sqlSelect("publicUrl,@sstringValue:string",
        "select sstringValue from XtkOption where sname='XtkFileRes_PublicUrl'")
logInfo(res.publicUrl.@sstringValue.toString())
```

```javascript
var xmlRes = sqlSelect("name:string,file:string:64","select relname, relfilenode from  pg_class WHERE relkind='r' AND pg_get_userbyid(relowner)<>'postgres';");
```

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
