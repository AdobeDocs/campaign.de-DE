---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 6%
---
# HttpClientRequest (Klasse)

Mit einem HttpClientRequest-Objekt können Sie bestimmte Vorgänge als HTTP-Client ausführen.

Beispiel :

```text
var req = new HttpClientRequest("http://www.somewhere.com/login") var buffer = new MemoryBuffer() buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1") req.header["Authorization"] = "Basic " + buffer.toBase64() req.header["Content-Type"] = "text/xml; charset=utf-8" req.method = "SEARCH" req.body = "<xml>any content</xml>" req.execute()
```

## „Keep Alive“

Das Objekt kann in zwei verschiedenen Modi verwendet werden: Standard oder Aufrechterhalten. Im Standardmodus können Sie eine einzelne Abfrage senden, im Keep-Alive-Modus können Sie mehrere Abfragen senden, während die Verbindung offen bleibt. Der Status des Objekts hängt von der Anwendungsreihenfolge der Methode ab. Wenn die Methode connect() aufgerufen wird, wechselt das Objekt in den Modus „Keep Alive“. Beispiel

```text
var req = new HttpClientRequest("http://evc-cit.info/cgi-bin/cit042/timeofday.cgi") req.connect() // Now the object is in keep-alive mode, we can sand many requests using // the same connection // Request ten times the time of the cgi var i = 0 while ( i < 10 ) { req.execute() var response = req.reponse i++ } req.disconnect()
```

## Asynchrone Abfragen

Abfragen werden standardmäßig im Blockierungsmodus ausgeführt, d. h.

[vollziehen](m-httpclientrequest-execute.md)

Die Funktion gibt die Kontrolle erst zurück, nachdem die Abfrage gesendet und die Antwort empfangen wurde. Sie können Abfragen auch asynchron ausführen. In diesem Fall wird die

[vollziehen](m-httpclientrequest-execute.md)

Die Funktion gibt sofort die Kontrolle zurück, und eine Funktion wird aufgerufen, sobald die Antwort eingeht. Dies ermöglicht die gleichzeitige Ausführung mehrerer Abfragen. Das folgende Programm ist ein vollständiges Beispiel, das zeigt, wie Sie eine Reihe von HTTP-Uploads ausführen, die drei Verbindungen gleichzeitig öffnen, wobei jeder Upload beginnt, sobald der letzte abgeschlossen ist.

```text
var list = [ "http://www.adobe.com/de/", "http://www.google.com/", "http://www.mozilla.org/", "http://www.linux.org/", "http://www.postgresql.org/"] var requests = [] var complete = function(req, context, status) { if( status == "success" ) logInfo("Receiving " + context + ": " + req.url + ": code = " + req.response.code) else logWarning("Error " + context + ": " + req.url + ": " + status) sendNext(context) } function sendNext(context) { // Repeat until the first execute() passes while( list.length != 0 ) { // Pick one URL from the list var url = list.shift() var req = new HttpClientRequest(url) req.complete = complete try { req.execute(false, true, context, 5000) logInfo("Sending " + url) requests.push(req) return } catch(e) { // Log a message and pick up next item from list logWarning("Failed to send " + url) } } } // Start 3 requests sendNext(1) sendNext(2) sendNext(3) // Wait until all requests are completed HttpClientRequest.wait(requests) logInfo("Finished.")
```

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [HttpClientRequest](m-httpclientrequest-httpclientrequest.md) | Erstellt ein neues -Objekt zum Ausführen einer HTTP-Client-Abfrage. |
| [Verbinden](m-httpclientrequest-connect.md) | Öffnet die HTTP-Verbindung und übergibt das -Objekt in den „Keep-Alive“-Modus |
| [Trennen](m-httpclientrequest-disconnect.md) | Schließt die HTTP-Verbindung eines Objekts im „Keep-Alive“-Modus |
| [Ausführen](m-httpclientrequest-execute.md) | Führt die HTTP-Abfrage aus. |
| [Warten](m-httpclientrequest-wait.md) | Wartet bis zum Ende einer Liste asynchroner Abfragen. |

## Eigenschaften

| Eigenschaft | Beschreibung |
| --- | --- |
| [body](p-httpclientrequest-body.md) | Der Hauptteil der HTTP-Abfrage. |
| [Abschließen](p-httpclientrequest-complete.md) | Funktion, die aufgerufen wird, wenn eine asynchrone Abfrage abgeschlossen ist. |
| [Kopfzeile](p-httpclientrequest-header.md) | Ein JavaScript-Objekt, das die HTTP-Header der Kopfzeile enthält. |
| [Methode](p-httpclientrequest-method.md) | Die HTTP-Methode in Form einer Zeichenfolge |
| [response](p-httpclientrequest-response.md) | Die Antwort der HTTP-Abfrage. Dies ist ein Objekt vom Typ HttpClientResponse |
| [url](p-httpclientrequest-url.md) | Die Adresse des Remote-Servers. |

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
