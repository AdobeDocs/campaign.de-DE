---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 16%
---
# getUrl

Ruft einen Textinhalt von einer URL ab.

```text
getUrl (url [, timeout ])
```

## Parameter

**url** Die Adresse der abzurufenden Seite.

**Zeitüberschreitung** Verbindungsüberschreitung. Wenn die Verbindung innerhalb der angegebenen Verzögerung nicht hergestellt werden kann, wird ein Fehler ausgelöst und das Skript wird unterbrochen.

## Rückgabewert

Eine Zeichenfolge, die die Textseite enthält.

## Bemerkungen

Die Codierung der zurückgegebenen Zeichenfolge entspricht der in der Antwort angegebenen Codierung (Content-Type). Wenn beim Herunterladen ein Fehler auftritt oder der Rückgabecode ungleich 200 (OK) ist, wird ein Fehler ausgelöst und das ausgeführte Skript wird unterbrochen. Beispiel:

```javascript
      var content = getUrl("http://www.google.com/index.html")
```

## Funktionen

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
