---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 32%
---
# Methode

Die HTTP-Methode in Form einer Zeichenfolge

```text
method
```

## Bemerkungen

Der Wert dieser Eigenschaft wird systematisch in Großbuchstaben geändert. Beispiel:

```javascript
var http = new HttpClientRequest(url)
http.method = "SEARCH"
```

## Funktionen

**Eigenschaft der Klasse:** [HttpClientRequest](c-httpclientrequest.md)

**Schreibgeschützt:**

Nein

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
