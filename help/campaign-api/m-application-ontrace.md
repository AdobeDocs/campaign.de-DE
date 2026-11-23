---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 14%
---
# onTrace

Fügt eine Abfangfunktion für Ablaufverfolgungsmeldungen hinzu oder löscht sie.

```text
onTrace ( [function ])
```

## Parameter

**function** Die hinzuzufügende Abfangfunktion. Wenn dieser Parameter ausgelassen wird, wird die zuletzt hinzugefügte Funktion gelöscht.

## Rückgabewert

Keine.

## Bemerkungen

Die Funktion akzeptiert ein -Objekt mit den folgenden Eigenschaften als Argument:

* Gravity (String) - Der Schweregrad der Nachricht („error“, „warning“, „info“, „status“, „verbose„)
* type (String) - Der Nachrichtentyp („log“, „wdbc“ usw.)
* message (String) - Die Nachricht

Die Funktion ist gegen erneuten Eintritt geschützt: Sie fängt von ihr selbst erstellte Ablaufverfolgungsmeldungen nicht ab. Beispiel:

```javascript
var file = new File("c:/temp/trace.txt")
file.open("w")

// Add a new trace handler
application.onTrace(function(log) {
  file.writeln(log.gravity.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the trace handler
application.onTrace()

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
