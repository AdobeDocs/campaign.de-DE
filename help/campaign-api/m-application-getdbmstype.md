---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 15%
---
# getDBMSType

Gibt den Servertyp der Datenbank zurück.

```text
getDBMSType ( [name ] [, checkIfUpdated ])
```

## Parameter

**name** Name der Datenquelle.

**checkIfUpdated** Überprüfen Sie, ob das Schema im Cache aktualisiert wurde. Keine Auswirkung, wenn das Schema bereits im Skript instanziiert ist.

## Rückgabewert

Eine Textzeichenfolge, die den Typ des Servers der Datenbank enthält.

## Bemerkungen

Wenn die Datenquelle nicht angegeben ist, verwendet die Funktion standardmäßig &quot;:default&quot;. Die Datenquelle muss vorhanden sein, andernfalls wird eine Ausnahme ausgelöst.

## Funktionen

**Methode der Klasse:** [Application](c-application.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
