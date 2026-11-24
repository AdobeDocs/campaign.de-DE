---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 16%
---
# Warten

Wartet auf das Ende einer Liste asynchroner SOAP-Abfragen.

```text
wait (requests)
```

## Parameter

**Anfragen** Eine Tabelle mit Abfragen.

## Rückgabewert

Keine.

## Bemerkungen

Die Funktion gilt nicht für einen Dienst, sondern ist eine Funktion der SoapService-Klasse. Beispiel:

```javascript
...
var req = service.start(1234, "GetOption", sessionToken, "XtkDatabaseId")

// Do some stuff here

// Wait until the end of the request
SoapService.wait( [req] )
```

Nachdem eine Abfrage abgeschlossen ist, wird sie automatisch aus der Liste gelöscht. Das bedeutet, dass die als Parameter übergebene Tabelle leer ist, wenn die Funktion das Steuerelement zurückgibt. Die Liste kann durch die Funktion [complete](p-soapservice-complete.md) geändert werden: Zum Beispiel ist es möglich, eine neue Abfrage zu starten und sie zur Liste hinzuzufügen.

## Funktionen

**Methode der Klasse:** [SoapService](c-soapservice.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Versandnachricht
* Typologieregel
* Import
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
