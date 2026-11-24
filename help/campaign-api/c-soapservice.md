---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 8%
---
# SoapService (Klasse)

Ermöglicht das Ausführen von SOAP-Aufrufen für einen Webdienst.

## Sperren von Aufrufen

Im Folgenden finden Sie ein typisches Anwendungsbeispiel: Zunächst müssen Sie eine Verbindung erstellen, dann mithilfe dieser Verbindung einen Service erstellen und schließlich die SOAP-Methoden für diesen Service deklarieren. Die SOAP-Methode wird in Form einer JavaScript-Methode des Service-Objekts bereitgestellt.

```text
var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0) var session = new SoapService(cnx, "xtk:session") session.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) var result = session.GetOption("admin/", "NmsBroadcast_DefaultProvider") var value = result[0] var type = result[1] logInfo("Value = " + value) logInfo("Type = " + type)
```

## Nicht blockierende Anrufe

Es ist möglich, nicht blockierende (asynchrone) Aufrufe durchzuführen, d. h. eine SOAP-Abfrage an einen Server auszuführen und das Skript weiter auszuführen, ohne auf das Ergebnis zu warten. Die Hauptunterschiede mit dem Sperrmodus sind:

* Die Verbindung muss im asynchronen Modus erstellt werden

* Verwenden Sie die

  [start](m-soapservice-start.md)

  Funktion.

* Definieren eines

  [vollständig](p-soapservice-complete.md)

  Funktion des Dienstes, die beim Empfang der Antwort aufgerufen wird.

* null

  [SoapService.wait](m-soapservice-wait.md)

  -Funktion wird verwendet, um auf das Ende der Verarbeitung für einen Satz von Abfragen zu warten.

Das folgende Beispielskript führt eine Reihe von „GetOption“-SOAP-Aufrufen an einen Adobe Campaign-Server durch, indem es drei Verbindungen gleichzeitig öffnet.

```text
var list = [ "XtkDatabaseId", "XtkKey", "WdbcTimeZone", "NmsServer_URL", "NmsBroadcast_DefaultProvider"] var requests = [] function complete(service, result, context, status) { if( status == "success" ) logInfo("option " + context + ": value = " + result[0]) else if( status == "fault" ) logInfo("option " + context + ": fault = " + result.message) else logInfo("option " + context + ": " + status) sendNext(service) } function createService() { // Create the connection var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0, true) // Create the service var service = new SoapService(cnx, "xtk:session") service.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) // Change the timeout to 5 seconds service.timeout = 5000 // Setup the callback function service.complete = complete return service } function sendNext(service) { if( list.length == 0) return // Pick an item from the list var name = list.shift() // Use the name as context var context = name // Send the request var req = service.start(context, "GetOption", "admin/", name) // Add the request to the wait queue requests.push(req) } // Open 3 connections and start a request on each one sendNext(createService()) sendNext(createService()) sendNext(createService()) SoapService.wait(requests) logInfo("Done.")
```

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [SoapService](m-soapservice-soapservice.md) | Erstellt einen Dienst zum Aufrufen der Funktionen eines Webdiensts. |
| [addMethod](m-soapservice-addmethod.md) | Deklariert eine Funktion für den Dienst. |
| [dispose](m-soapservice-dispose.md) | Gibt die vom -Objekt verwendeten Ressourcen frei. |
| [Start](m-soapservice-start.md) | Startet eine Abfrage im asynchronen Modus. |
| [Warten](m-soapservice-wait.md) | Wartet auf das Ende einer Liste asynchroner SOAP-Abfragen. |

## Eigenschaften

| Eigenschaft | Beschreibung |
| --- | --- |
| [Abschließen](p-soapservice-complete.md) | Funktion, die aufgerufen wird, wenn eine asynchrone Abfrage abgeschlossen ist. |
| [Kopfzeile](p-soapservice-header.md) | Ein wortwörtlich in den SOAP-Header kopierter String. |
| [Zeitüberschreitung](p-soapservice-timeout.md) | Maximale Wartezeit in Millisekunden bei einer asynchronen Abfrage. Wenn dieser Parameter nicht definiert ist, beträgt die Wartezeit 5 Minuten. |

## Funktionen

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
