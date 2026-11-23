---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 9%
---
# vollständig

Funktion, die aufgerufen wird, wenn eine asynchrone Abfrage abgeschlossen ist.

```text
complete
```

## Bemerkungen

Die Funktion muss vier Argumente akzeptieren:

* Der Service
* Das Ergebnis
* Kontext: Dies ist der Parameter, der an die Funktion [start](m-soapservice-start.md) übergeben wird
* Der Status

Der Status kann die folgenden Werte haben:

* „Erfolg“ bedeutet, dass ein Ergebnis empfangen wurde.
* „Fehler“ kann bedeuten, dass die Kommunikation unterbrochen wurde, dass die Antwort schlecht strukturiert war oder dass ein HTTP-Fehler aufgetreten ist.
* „Fehler“, wenn ein SOAP-Fehler zurückgegeben wird. In diesem Fall enthält das Ergebnis ein -Objekt, das den Fehler beschreibt.
* „Zeitüberschreitung“ bedeutet, dass die Verbindung nicht hergestellt werden konnte oder dass innerhalb der konfigurierten Frist keine Antwort empfangen wurde.

Wenn das Ergebnis „Erfolg“ ist, hängt das Ergebnis von der Anzahl der zurückgegebenen Parameter ab:

* ungültig, wenn die Abfrage keine Werte zurückgibt
* Der Wert der Abfrage gibt einen einzelnen Parameter zurück
* Eine Tabelle, wenn die Abfrage mehrere Parameter zurückgibt

Wenn der Status „Fehler“ ist, ist das Ergebnis ein Objekt, das die folgenden Eigenschaften enthält:

* Meldung: Die Fehlerbeschreibungsmeldung.
* Objekt : Ein XML-Objekt, das die Details des Fehlers enthält.

Beispiel:

```javascript
http.complete = function(result, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + result[0])
}
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
