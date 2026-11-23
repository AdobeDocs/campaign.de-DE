---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 37%
---
# copyTo

Kopiert eine Datei.

```text
copyTo (fileName)
```

## Parameter

**fileName** Name der Zieldatei oder des Zielordners (muss vollständiger Pfad sein).

## Rückgabewert

Keine.

## Bemerkungen

Beispiele:

```javascript
var f = new File("c:/file.txt")
f.copyTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.copyTo("c:/dir/")
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
