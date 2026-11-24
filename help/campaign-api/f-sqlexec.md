---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 9%
---
# sqlExec

Führt ein SQL-Script aus.

```text
sqlExec (query [, value1, ... ])
```

## Parameter

**query** Die SQL-Abfrage.

**value1, …** Variablen der SQL-Abfrage.

## Rückgabewert

Die Anzahl der Datensätze, die im Falle einer AKTUALISIERUNG oder eines INSERT SQL-Befehls aktualisiert oder eingefügt wurden.

## Bemerkungen

Variablen ersetzen die Parameter im Befehl . Der Variablentyp muss mit dem im Befehl deklarierten Parameter übereinstimmen. Diese Variablen sind in einer Deklaration vom Typ „Auswählen“ oder „Aktualisieren“ verfügbar. Es gibt folgende Typen:

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

Die folgenden Ersatzparameter (nur gültig für ein „Update„) werden automatisch durch einen Wert ersetzt und benötigen keine verknüpfte Variable.

* $(id) - Kennung erzeugen
* $(id:NmsTrackingLogId) - Generieren einer Kennung mithilfe einer bestimmten Sequenz
* $(aktuelles) Datum und aktuelle Stunde

Der Operator muss über das Recht „sql“ verfügen, um diese Funktion verwenden zu können. Andernfalls wird eine Ausnahme ausgelöst. Beispiel:

```javascript
      var sql4 = "INSERT INTO Reporting (sClientdesc,sClient) values ('" + client.@description.toString() + "','" + client.@clientCode.toString() +"')";
sqlExec(sql4);
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
