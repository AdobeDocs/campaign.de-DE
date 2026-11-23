---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 23%
---
# setHeader

Gibt einen HTTP-Header an.

```text
setHeader (headerName, headerValue)
```

## Parameter

**headerName** Zeichenfolge, die den Namen der HTTP-Kopfzeile darstellt.

**headerValue** Zeichenfolge, die den Inhalt des HTTP-Headers darstellt.

## Rückgabewert

Keine.

## Bemerkungen

Les en-têtes ainsi spécifiés prévalent sur les en-têtes par défault lors des appels SOAP. Beispiel :

```javascript
      var cnx = new HttpSoapConnection("http://localhost/test/Service1.asmx");
var memBuf = new MemoryBuffer();
memBuf.fromString("rico:pass@word1")
cnx.setHeader("Authorization","Basic " + memBuf.toBase64());
```

## Funktionen

**Methode der Klasse:** [HttpSoapConnection](c-httpsoapconnection.md)

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
