---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 28%
---
# Header

Ein -Objekt, das alle HTTP-Kopfzeilen enthält.

```text
header
```

## Bemerkungen

Beim Namen der Eigenschaften wird nicht zwischen Groß- und Kleinschreibung unterschieden. Beispiel:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
for(var i in response.header)
  logInfo("header[" + i + "] => " + response.header[i])
    
```

Um mehrere Header mit demselben Namen wiederherzustellen, verwenden Sie die [headers](p-httpclientresponse-headers.md)-Eigenschaft anstelle der Header-Eigenschaft.

## Funktionen

**Eigenschaft der Klasse:** [HttpClientResponse](c-httpclientresponse.md)

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
