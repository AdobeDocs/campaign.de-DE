---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 8%
---
# sqlGetInt

Gibt die aus einer SQL-Abfrage resultierende Ganzzahl zurück.

```text
sqlGetInt (query [, value1, ... ])
```

## Parameter

**query** Die SQL-Abfrage.

**value1, …** Variablen der SQL-Abfrage.

## Rückgabewert

Der ganzzahlige Wert, der der Abfrage entspricht.

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

Die Verwendung von Variablen ändert nichts an der Leistung von Adobe Campaign. Die SQL-Abfrage muss eine einzelne Zeile und ein einzelnes Textfeld auswählen. Der Operator muss über das Recht „sql“ verfügen, um diese Funktion verwenden zu können. Andernfalls wird eine Ausnahme ausgelöst. Beispiel:

```javascript
      var age = sqlGetInt('select sAge from nmsRecipient where sEmail =$(sz) order by tsCreated DESC LIMIT 1', email)
var iRecipientId = sqlGetInt("select irecipientId FROM NmsRecipient WHERE sLastName=$(sz) and tsCreated>$(ts)", strName);
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
