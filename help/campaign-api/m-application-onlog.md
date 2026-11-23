---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 9%
---
# onLog

Fügt eine Abfangfunktion für die in das Protokoll geschriebenen Nachrichten hinzu oder löscht sie.

```text
onLog ( [function ])
```

## Parameter

**function** Die hinzuzufügende Abfangfunktion. Wenn dieser Parameter ausgelassen wird, wird die zuletzt hinzugefügte Funktion gelöscht.

## Rückgabewert

Keine.

## Bemerkungen

Die zuletzt hinzugefügte Funktion wird zuerst aufgerufen. Die Funktion akzeptiert ein -Objekt mit den folgenden Eigenschaften als Argument:

* type (Number) - Der Nachrichtentyp (0=Fehler, 1=Warnung, 2=Information, 3=Status, 4=Verbose)
* code (Number) - Der Fehler-Code (0, wenn es sich nicht um einen Fehler handelt)
* object (Zeichenfolge) - Mit der Nachricht verknüpftes Objekt (nicht verwendet)
* message (String) - Die Nachricht

Die Funktion muss einen booleschen Wert zurückgeben. Der Wert „true“ verhindert, dass folgende Abfangfunktionen die Nachricht empfangen. Die Funktion ist vor einem erneuten Eintritt geschützt: Sie fängt keine Nachrichten ab, die sie an das Journal selbst geschrieben hat. Beispiel:

```javascript
var file = new File("c:/temp/log.txt")
file.open("w")

// Add a new log handler
application.onLog(function(log) {
  file.writeln(log.type.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the log handler
application.onLog()

// This message won't be caught
logInfo("Finished.")

file.close()
```

## Funktionen

**Methode der Klasse:** [Application](c-application.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
