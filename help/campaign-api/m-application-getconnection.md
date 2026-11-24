---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 25%
---
# getConnection

Gibt eine neue Verbindung zum Datenbankserver zurück.

```text
getConnection ()
```

## Parameter

Keine.

## Rückgabewert

Eine [Verbindung](c-dbengine.md) zum Datenbankserver.

## Bemerkungen

Es ist möglich, die Verbindung vor dem Ende der Skriptausführung mit der Methode [dispose](m-dbengine-dispose.md) freizugeben.

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
