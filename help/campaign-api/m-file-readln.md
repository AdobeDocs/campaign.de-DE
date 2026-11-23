---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 30%
---
# vorlesen

Liest eine Zeile der Textdatei.

```text
readln ()
```

## Parameter

Keine.

## Rückgabewert

Die Zeichenfolge, die die nächste Zeile der Datei enthält, oder ⌐null, wenn das Ende der Datei erreicht wurde.

## Bemerkungen

Beispiel:

```javascript
var f = new File("c:/dummy.xml")
f.open("r", File.CODEPAGE_UTF8)
var line
while( line = f.readln() )
  logInfo(line)
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
