---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 9%
---
# Warten

Wartet bis zum Ende einer Liste asynchroner Abfragen.

```text
wait (requests,waitAll)
```

## Parameter

**Anfragen** Eine Tabelle mit Abfragen.

**waitAll** Boolescher Wert (standardmäßig „true„), warten Sie, bis alle Anforderungen aus der Abfrageliste abgeschlossen sind. Wenn dies auf „false“ festgelegt und mindestens eine Anforderung abgeschlossen wird, wird die Funktion aus der Überwachungsschleife entfernt.

## Rückgabewert

Keine.

## Bemerkungen

Die Funktion gilt nicht für eine Abfrage, sondern ist eine Funktion des HttpClientRequest-Bin. Beispiel:

```javascript
var req = new HttpClientRequest("http://www.adobe.com/de/")
req.complete = function(req, context, status) { logInfo(status) }
req.execute(false, true)

HttpClientRequest.wait( [req] )
```

Eine Abfrage kann der Liste nur hinzugefügt werden, wenn sie asynchron ist und der [execute](m-httpclientrequest-execute.md)-Aufruf keine Ausnahme ausgelöst hat. Nachdem eine Abfrage abgeschlossen ist, wird sie automatisch aus der Liste gelöscht. Das bedeutet, dass die als Parameter übergebene Tabelle leer ist, wenn die Funktion das Steuerelement zurückgibt. Die Liste kann durch die Funktion [complete](p-httpclientrequest-complete.md) geändert werden: Zum Beispiel ist es möglich, eine neue Abfrage zu starten und sie zur Liste hinzuzufügen.

## Funktionen

**Methode der Klasse:** [HttpClientRequest](c-httpclientrequest.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
