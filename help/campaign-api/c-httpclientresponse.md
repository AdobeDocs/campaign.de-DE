---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 12%
---
# HttpClientResponse (Klasse)

Ein -Objekt, das die Antwort auf eine HTTP-Abfrage darstellt.

Kann nur nach Ausführung einer HTTP-Abfrage durch die `response`-Eigenschaft abgerufen werden.

## Eigenschaften

| Eigenschaft | Beschreibung |
| --- | --- |
| [body](p-httpclientresponse-body.md) | Der Hauptteil der HTTP-Antwort in Form eines MemoryBuffer-Objekts. |
| [code](p-httpclientresponse-code.md) | Der Rückgabecode der HTTP-Antwort in Form einer JavaScript-Ganzzahl. |
| [codePage](p-httpclientresponse-codepage.md) | Der Wert von codePage der Antwort. Wird zum Decodieren des Bodys der HTTP-Antwort verwendet. |
| [Kopfzeile](p-httpclientresponse-header.md) | Ein -Objekt, das alle HTTP-Kopfzeilen enthält. |
| [Kopfzeilen](p-httpclientresponse-headers.md) | Die Liste der Header für die HTTP-Antwort gruppiert nach Namen. |
| [message](p-httpclientresponse-message.md) | Die von der HTTP-Antwort übertragene Nachricht. |

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
