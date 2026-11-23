---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 38%
---
# Schreibschrift

Schreibt eine Textzeile in die Datei.

```text
writeln (line)
```

## Parameter

**line** Die zu schreibende Textzeile.

## Rückgabewert

Keine.

## Bemerkungen

Beispiel:

```javascript
var f = new File("c:/file.txt")
f.open("a")
f.writeln("line 1")
f.writeln("line 2")
f.close()
```

## Funktionen

**Methode der Klasse:** [File](c-file.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
