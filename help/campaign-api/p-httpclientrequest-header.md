---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 21%
---
# Header

Ein JavaScript-Objekt, das die HTTP-Header der Kopfzeile enthält.

```text
header
```

## Bemerkungen

Alle Eigenschaften des Header-Objekts sind im Lese-/Schreibmodus verfügbar und aufzählbar. Jeder Inhaber des Header-Objekts ist ein Eintrag im HTTP-Header der Abfrage. Bei Eigenschaftsnamen wird nicht zwischen Groß- und Kleinschreibung unterschieden (wie bei HTTP-Kopfzeilen). Beispiel:

```javascript
var http = new HttpClientRequest(url)

var buffer = new MemoryBuffer()
buffer.fromString(userName + ':' + password, "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"
http.header["Date"] = (new Date()).toGMTString()
//Note: http.header.Date == http.header.date

for( var i in http.header )
logInfo("header[" + i + "] => " + http.header[i])
```

## Funktionen

**Eigenschaft der Klasse:** [HttpClientRequest](c-httpclientrequest.md)

**Schreibgeschützt:**

Ja

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
