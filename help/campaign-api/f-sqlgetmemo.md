---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 8%
---
# sqlGetMemo

Gibt das Memo-Feld aus einer SQL-Abfrage zurück.

```text
sqlGetMemo (query [, value1, ... ])
```

## Parameter

**query** Die SQL-Abfrage.

**value1, …** Variablen der SQL-Abfrage.

## Rückgabewert

Das Memo-Feld, das der Abfrage entspricht.

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
* $(Dau)-Zeitspanne in Millisekunden (ms)

Die folgenden Ersatzparameter (nur gültig für ein „Update„) werden automatisch durch einen Wert ersetzt und benötigen keine verknüpfte Variable.

* $(id) Erzeugt einen Bezeichner
* $(id:NmsTrackingLogId) Erzeugt einen Bezeichner mit einer bestimmten Sequenz
* $(aktuelles) Datum und Uhrzeit

Die Verwendung von Variablen hat keine Auswirkungen auf die Leistung von Adobe Campaign. Die SQL-Abfrage muss eine einzelne Zeile und ein einzelnes Textfeld auswählen. Der Operator muss über das Recht „sql“ verfügen, um diese Funktion verwenden zu können. Andernfalls wird eine Ausnahme ausgelöst. Beispiel:

```javascript
      var logData = sqlGetMemo('select log from IncomingLog where sEmail =$(sz) order by tsCreated DESC LIMIT 1', email)
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
