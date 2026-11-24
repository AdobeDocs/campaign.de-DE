---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 12%
---
# Kopfzeilen

Die Liste der Header für die HTTP-Antwort gruppiert nach Namen.

```text
headers
```

## Bemerkungen

Jede Headers-Eigenschaft enthält den Namen der Kopfzeile und den Wert der Tabelle, die jeder Kopfzeile diesen Namen zuordnet. Diese Funktion unterscheidet sich von [header](p-httpclientresponse-header.md), da sie eine Wertetabelle anstelle eines eindeutigen Werts für einen bestimmten Namen zurückgibt. Dies ist für Kopfzeilen nützlich, die mehrmals angezeigt werden können, z. B. Accept-Language oder Set-Cookie. Die Funktion gibt eine leere Tabelle zurück, wenn die HTTP-Antwort keine Kopfzeile mit diesem Namen hat. Beispiel:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = response
var cookies = response.headers["set-cookie"]
for each(var c in cookies)
{
  logInfo("Set-Cookie: " + c)
}
```

Die Header-Eigenschaften sind nicht in Einzelpläne aufgliederbar. Bei Eigenschaftsnamen wird nicht zwischen Groß- und Kleinschreibung unterschieden.

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
