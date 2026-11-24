---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 9%
---
# vollziehen

Führt die HTTP-Abfrage aus.

```text
execute ( [hasProxy ] [, async ] [, reuseaddr ] [, context ] [, timeout ])
```

## Parameter

**hasProxy** Boolescher Wert auf „true“ gesetzt, wenn Sie einen HTTP-Proxy verwenden müssen. Standardmäßig ist dies auf „false“ festgelegt.

**async** Boolescher Wert auf „true“ gesetzt, wenn die Abfrage asynchron ist. Standardmäßig ist dies auf „false“ festgelegt.

**reuseaddr** Boolescher Wert auf „true“ gesetzt, wenn der zugrunde liegende Socket die Wiederverwendung lokaler Adressen ermöglichen soll. Standardmäßig ist dies auf „false“ festgelegt.

**context** Der Kontext ist jedes Objekt, das im Falle einer asynchronen Abfrage an das zweite Argument [complete](p-httpclientrequest-complete.md)-Funktion weitergeleitet wird.Standardmäßig auf null festgelegt.

**timeout** Maximale Wartezeit in Millisekunden bei asynchroner Abfrage. Wenn dieser Parameter nicht definiert ist, beträgt die Wartezeit 5 Minuten.

## Rückgabewert

Keine.

## Bemerkungen

Wenn die HTTP-Verbindung fehlschlägt, wird eine Ausnahme ausgelöst. Die [response](p-httpclientrequest-response.md)-Eigenschaft wird erst nach einem erfolgreichen Aufruf der Execute-Funktion gültig. Beispiel:

```javascript
          
        var http = new HttpClientRequest("http://www.google.com")
        http.method = "GET"
        // Note: Here, http.response == undefined
        http.execute()
        var response = http.response
      
```

## Funktionen

**Methode der Klasse:** [HttpClientRequest](c-httpclientrequest.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
