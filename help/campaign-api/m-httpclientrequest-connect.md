---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 13%
---
# verbinden

Öffnet die HTTP-Verbindung und übergibt das -Objekt in den „Keep-Alive“-Modus

```text
connect ( [hasProxy ] [, async ])
```

## Parameter

**hasProxy** Boolesch auf „true“, wenn Sie einen HTTP-Proxy verwenden müssen. Standardmäßig ist dies auf „false“ festgelegt.

**async** Boolescher Wert auf „true“ gesetzt, wenn die Verbindung zum Ausführen einer asynchronen Abfrage bestimmt ist. Standardmäßig auf „false“ festgelegt.

## Rückgabewert

Keine.

## Bemerkungen

Wenn die HTTP-Verbindung fehlschlägt, wird eine Ausnahme ausgelöst. Die Antworteigenschaft wird erst nach einem erfolgreichen Aufruf der Ausführungsfunktion gültig. Vergessen Sie nicht, disconnect() aufzurufen, sobald Sie die Verbindung verwendet haben. Beispiel:

```javascript
// Mistake with the hostname gogle instead of google
var badHttp = new HttpClientRequest("www.gogle.fr");
try {
  badHttp.connect();
} catch (e) {
  // Here an exception has been raised
}

var goodHttp = new HttpClientRequest("www.google.fr");
try {
  goodHttp.connect();
} catch (e) {
  // No exeception raised
}
...
goodHttp.disconnect();
```

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
