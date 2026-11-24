---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 7%
---
# addMethod

Deklariert eine Funktion für den Dienst.

```text
addMethod (name, action, arguments, responses, requestNodeName, responseNodeName)
```

## Parameter

**name** Name der Methode. Dies ist der in JavaScript angezeigte Name und der Name der SOAP-Methode.

**action** SOAP-Action-Parameter.

**Argumente** Argumentdeklaration in Form einer Tabelle, die eine Liste von Zeichenfolgen enthält, die nach Paaren gruppiert sind. Die erste Zeichenfolge ist der Name des Arguments und die zweite entspricht dem Typ: \[„name1“, „type1“, „name2“, „type2“, …\]

**responses** Deklaration von Rückgabewerten in Form einer Tabelle, die eine Liste von Zeichenfolgen enthält, die nach Paaren gruppiert sind: Die erste Zeichenfolge ist der Name des Arguments und die zweite entspricht dem Typ: \[„name1“, „type1“, „name2“, „type2“, …\]

**requestNodeName** Eine Zeichenfolge, die den Namen des XML-Knotens der SOAP-Abfrage anstelle des Methodennamens angibt.

**responseNodeName** Eine Zeichenfolge, die den Namen des XML-Knotens der SOAP-Antwort anstelle des Methodennamens gefolgt von Response angibt.

## Rückgabewert

Keine.

## Bemerkungen

Die folgenden Typen werden unterstützt:

* Zeichenfolge
* Boolesch
* Lang
* Kurz
* Byte
* float
* double
* Datum
* Uhrzeit
* datetime
* NLDocument
* NLElement
* NLRawXML
* NLCollection

Wenn eine Methode für den Dienst deklariert wird, wird sie zu einer Methode des Dienstes und kann direkt aufgerufen werden, indem die Methode mit ihrem Namen aufgerufen wird. Der für einen eingehenden Parameter verwendete NLRawXML-Typ kopiert den gesamten XML-Knoten, um das Argument zu ersetzen. Sie wird als Rückgabetyp verwendet und enthält das gesamte erste untergeordnete Element der SOAP-Antwort. Seine Verwendung bedeutet, dass die SOAP-Antwort nur über ein untergeordnetes Element verfügt. Der NLCollection-Typ, der für einen eingehenden Parameter verwendet wird, kopiert alle untergeordneten Elemente, um das Argument zu ersetzen. Dies ist nützlich, wenn das eingehende Argument ein Variablenparameter ist. Sie wird als Rückgabetyp verwendet und enthält die gesamte SOAP-Antwort, da dies der Stamm des Rückgabewerts ist. Bei Fehlern wird eine Ausnahme ausgelöst. Wenn es sich um einen korrekt formatierten SOAP-Fehler handelt, weist die ausgelöste Ausnahme eine soapFault-Eigenschaft auf und enthält den XML-Knoten des SOAP-Fehlers. Beispiel:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
session.addMethod("GetOption", "xtk:session#GetOption",
  ["token", "string", "name", "string"],
  ["value", "string", "type", "byte"])
try
{
var result  = session.GetOption("admin/", "NmsBroadcast_DefaultProvider")
var value   = result[0]
var type    = result[1]
logInfo("Value = " + value)
logInfo("Type = " + type)
}
catch( e )
{
  if( e.soapFault )
    logInfo("A SOAP Fault occured : " + e.soapFault.toXMLString());
  else
    logInfo("An error occured : " + e);
}
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
