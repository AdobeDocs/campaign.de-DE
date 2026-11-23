---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 13%
---
# vollständig

Funktion, die aufgerufen wird, wenn eine asynchrone Abfrage abgeschlossen ist.

```text
complete
```

## Bemerkungen

Die Funktion muss drei Argumente akzeptieren:

* Die Abfrage
* Kontext
* Der Status: „Erfolg“, „Fehler“ oder „Zeitüberschreitung“

Der Status „Erfolg“ bedeutet, dass eine Antwort empfangen wurde, die Antwort kann jedoch einen beliebigen Code enthalten (200, 404, 503 usw.). Der Status „Fehler“ kann auf eine Unterbrechung der Kommunikation einer schlecht strukturierten Antwort hinweisen. Der Status „Zeitüberschreitung“ bedeutet, dass die Verbindung nicht hergestellt werden konnte oder dass innerhalb der konfigurierten Frist keine Antwort empfangen wurde. Beispiel:

```javascript
http.complete = function(req, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + req.response.code)
}
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
