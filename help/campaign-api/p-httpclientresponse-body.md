---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 18%
---
# Textkörper

Der Hauptteil der HTTP-Antwort in Form eines MemoryBuffer-Objekts.

```text
body
```

## Bemerkungen

Auf die Codierung des Antworttextes kann über die Eigenschaft [codePage](p-httpclientresponse-codepage.md) zugegriffen werden. Der Hauptteil der HTTP-Antwort wird in Form eines „MemoryBuffer[-](c-memorybuffer.md) angegeben. Alle für einen [MemoryBuffer](c-memorybuffer.md) geltenden Methoden sind daher auf den Hauptteil der HTTP-Antwort anwendbar. Beispiel:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
if( response.code != 200 )
  throw "HTTP request failed with " + response.message
var content = response.body.toString(response.codePage)
```

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
