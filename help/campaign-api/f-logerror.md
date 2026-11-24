---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 20%
---
# logError

Fügt eine Fehlermeldung zum Protokoll der Workflow-Instanz hinzu und unterbricht die Ausführung des Skripts.

```text
logError (message)
```

## Parameter

**message** Die Nachricht, die dem Protokoll hinzugefügt werden soll.

## Rückgabewert

Keine.

## Bemerkungen

Die laufende Aufgabe verhält sich so, als wäre ein Fehler aufgetreten: Ein Fehler wird gekennzeichnet und der Workflow wird ausgesetzt. Diese Funktion ist daher nützlich, um explizit einen Fehler in einem Workflow auszulösen und ihn auszusetzen.

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
