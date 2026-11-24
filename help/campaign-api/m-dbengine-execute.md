---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 9%
---
# vollziehen

Führt einen SQL-Befehl aus.

```text
execute (command [, value1, ... ])
```

## Parameter

**Befehl** SQL-Befehl.

**value1, …** Variablen des Befehls.

## Rückgabewert

Die Anzahl der aktualisierten oder eingefügten Datensätze, falls für den ausgeführten Befehl zutreffend, andernfalls null.

## Bemerkungen

Die Variablen werden verwendet, um die Parameter des Befehls zu ersetzen. Der Variablentyp muss dem im Befehl deklarierten Typ entsprechen. Es gibt folgende Typen:

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
* $(Dauer) Zeitspanne in Millisekunden (ms)

Die folgenden Ersatzparameter werden automatisch durch einen Wert ersetzt und erfordern keine zugehörige Variable.

* $(id) Erzeugt einen Bezeichner
* $(id:NmsTrackingLogId) Erzeugt einen Bezeichner anhand einer bestimmten Sequenz
* $(aktuelles) Datum und Uhrzeit

Der Operator benötigt „SQL“-Rechte, um diese Funktion verwenden zu können. Andernfalls wird eine Ausnahme ausgelöst.

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
