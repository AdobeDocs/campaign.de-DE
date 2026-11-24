---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 15%
---
# Textkörper

Der Hauptteil der HTTP-Abfrage.

```text
body
```

## Bemerkungen

Das -Objekt, das dem Hauptteil der Abfrage zugewiesen ist, wird wie folgt verarbeitet:

* undefined, null, function: werden nicht als sendefähige Elemente betrachtet, der Hauptteil der HTTP-Abfrage ist leer.
* number, boolean, string, XML, Object: wird in eine Zeichenfolge geändert, die auf der toString-Methode basiert und auf dem Content-Typ des HTTP-Headers basiert.
* [MemoryBuffer](c-memorybuffer.md): Der Inhalt wird unverändert in den Hauptteil der Abfrage kopiert.

Beispiel:

```javascript
var query = "Select \"urn:schemas:calendar:uid\" " // etc...
var apptRequest =
  "<g:searchrequest xmlns:g="DAV:">\n" +
  "  <g:sql>\n" +
        query +
  "  </g:sql>\n" +
  "</g:searchrequest>"
http.body = apptRequest
    
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
