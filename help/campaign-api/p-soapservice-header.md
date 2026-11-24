---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 38%
---
# Header

Ein wortwörtlich in den SOAP-Header kopierter String.

```text
header
```

## Bemerkungen

Les chaînes de caractères sont recopiées in-extenso dans l&#39;en-tête SOAP sans vérification. Beispiel:

```javascript
      var cnx = new HttpSoapConnection(result.serverURL, "utf-8", HttpSoapConnection.SOAP_11)
var service = new SoapService(cnx, "urn:partner.soap.sforce.com")
service.header = "<ns1:SessionHeader xmlns:ns1='urn:partner.soap.sforce.com'><ns1:sessionId>123456</ns1:sessionId></ns1:SessionHeader>"
```

## Funktionen

**Eigenschaft der Klasse:** [SoapService](c-soapservice.md)

**Schreibgeschützt:**

Nein

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
