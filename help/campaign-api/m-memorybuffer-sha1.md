---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 35%
---
# SHA1

Berechnet die SHA-1-Signatur des MemoryBuffer-Inhalts.

```text
sha1 ()
```

## Parameter

Keine.

## Rückgabewert

Eine Zeichenfolge, die die hexadezimale Darstellung der SHA-1-Signatur ist.

## Bemerkungen

Beispiel:

```javascript
var memBuf = new MemoryBuffer();
memBuf.fromString("Hello world", "utf-8");
logInfo(memBuf.sha1()); // Writes down  => 7b502c3a1f48c8609ae212cdfb639dee39673f5e
```

## Funktionen

**Methode der Klasse:** [MemoryBuffer](c-memorybuffer.md)

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
