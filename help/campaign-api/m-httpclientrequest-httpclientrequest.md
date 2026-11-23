---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 30%
---
# HttpClientRequest

Erstellt ein neues -Objekt zum Ausführen einer HTTP-Client-Abfrage.

```text
HttpClientRequest ( [URL ])
```

## Parameter

**URL** URL des Empfängers der Abfrage.

## Rückgabewert

Keine.

## Bemerkungen

Wenn der FTP-Befehl fehlschlägt, wird eine Ausnahme ausgelöst. Beispiel:

```javascript
var http = new HttpClientRequest("http://www.somewhere.com/login")

var buffer = new MemoryBuffer()
buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"

http.method = "SEARCH"
http.body = "<xml>any content</xml>"

http.execute()
       
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
