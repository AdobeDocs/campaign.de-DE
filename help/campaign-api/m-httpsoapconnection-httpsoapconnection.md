---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 17%
---
# HttpSoap-Verbindung

Erstellt eine HTTP-Verbindung zu einem SOAP-Server.

```text
HttpSoapConnection (url [, codepage ] [, protocol ] [, async ])
```

## Parameter

**url** URL des Servers einschließlich des Pfads.

**codepage** Die Codierung für die Serialisierung des SOAP-Aufrufs. Mit diesem optionalen Parameter können Sie die Zeichencodierung angeben. Standardmäßig ist die Codierung UTF-8. Beispiel:

* ISO-8859-1
* UTF-8
* UTF-16

**protocol** Der Typ des verwendeten SOAP-Protokolls. Mit diesem optionalen Parameter können Sie das verwendete SOAP-Protokoll angeben. Standardmäßig sind dies SOAP\_11-Werte:

* SOAP\_11: SOAP-Protokoll 1.1.
* SOAP\_12: SOAP-Protokoll 1.2.
* 0: Adobe Campaign-internes SOAP-Protokoll.

**async** Boolescher Wert auf „true“ gesetzt, wenn die Verbindung zum Ausführen einer asynchronen Abfrage bestimmt ist. Standardmäßig auf „false“ festgelegt.

## Rückgabewert

Keine.

## Bemerkungen

Beispiele:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp")
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-16", HttpSoapConnection.SOAP_11)
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-8", 0)
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
