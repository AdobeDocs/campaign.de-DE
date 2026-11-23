---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 6%
---
# Abfrage

Führt eine SQL-Abfrage vom Typ SELECT aus.

```text
query (command [, value1, ... ])
```

## Parameter

**Befehl** SQL-Befehl.

**value1, …** Variablen des Befehls.

## Rückgabewert

Ein Cursor, mit dem Sie das Abfrageergebnis iterieren können.

## Bemerkungen

Warnung: Im Gegensatz zu dem, was im Abschnitt Funktionen angegeben ist, ist die Abfragefunktion in WebApp nicht verfügbar. Variablen ersetzen die Parameter des Befehls . Der Variablentyp muss mit dem im Befehl angegebenen Parameter übereinstimmen. Die folgenden Typen sind verfügbar:

* Zeichenfolge $(sz)
* $(M)-Memo
* $(l) lang
* $(s) kurz
* $(b) Byte
* $(d) doppelt
* $(f) Gleitkommazahl
* $(ts) Zeitstempel
* $(dt) Datum
* $(tm)-Zeit
* $(Dau) Zeitspanne

Die folgenden Ersatzparameter werden automatisch durch einen Wert ersetzt und benötigen keine verknüpfte Variable.

* $(id) Erzeugt einen Bezeichner
* $(id:NmsTrackingLogId) Erzeugt einen Bezeichner anhand einer bestimmten Sequenz
* $(aktuelles) Datum und Uhrzeit

Die Iteration auf dem Cursor erfolgt über „for each“ und gibt für jede wiederhergestellte Zeile eine Tabelle zurück. Jedes Element der Tabelle entspricht einem Feld der Abfrage, und der Elementtyp hängt vom Feldtyp ab. Beispiel:

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)", 1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

In diesem Beispiel ist Zeile\[0\] eine Zahl, die mit iOperatorId übereinstimmt, Zeile\[1\] ist eine Zeichenfolge, die mit sName übereinstimmt, und Zeile\[2\] ist ein Datum, das mit tsLastModified übereinstimmt. Der Operator benötigt „SQL“-Rechte, um diese Funktion verwenden zu können. Andernfalls wird eine Ausnahme ausgelöst.

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
