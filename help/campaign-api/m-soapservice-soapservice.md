---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 36%
---
# SoapService

Erstellt einen Dienst zum Aufrufen der Funktionen eines Webdiensts.

```text
SoapService (cnx, namespace)
```

## Parameter

**cnx** Die ([HttpSoapConnection](c-httpsoapconnection.md)) HTTP-Verbindung.

**namespace** Namespace des Services.

## Rückgabewert

Keine.

## Bemerkungen

Beispiel:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
```

## Funktionen

**Methode der Klasse:** [SoapService](c-soapservice.md)

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
