---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 7%
---
# getTimezoneJson

Gibt eine Zeichenfolge zurück, die die JSON-Darstellung der Liste der Zeitunterschiede mit UTC-Zeit und ihrem Startdatum im Vergleich zum UNIX-Zeitraum für eine Zeitzone ist.

```text
getTimezoneJson ( [timezone ])
```

## Parameter

**timezone** Der Name der Zeitzone, für die Sie die Liste der Zeitunterschiede im Vergleich zu UTC zurückgeben müssen. Jede Zeitdifferenz ist mit einem Startdatum verknüpft, das bis zum nächsten Startdatum gültig ist. Wenn kein Wert zurückgegeben wird, wird die Standardzeitzone des Operators verwendet.

## Rückgabewert

Gibt einen String zurück, der die JSON-Darstellung der Zeitunterschiede ist, die basierend auf den Datumsangaben angewendet werden sollen. Die zurückgegebene JSON-Zeichenfolge wird in einer Tabelle mit {startDate, offset} Paaren bewertet. Die zurückgegebene Zeichenfolge hat die folgende Form:

```javascript
[
  {"startDate" : -1855958901000, "offset" : 0},
  {"startDate" : -1689814800000, "offset" : 3600000}
]
```

* startDate ist die Posix-Zeit, ab der die Gültigkeit endet.
* Der Offset ist der Wert in Millisekunden der Zeitdifferenz zu UTC. Zum Beispiel UTC+02:00 gleich 7200000.

## Bemerkungen

getTimezoneJson wird über die Anwendungsinstanz aufgerufen.

```javascript
var tzList = eval(application.getTimezoneJson());
```

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
