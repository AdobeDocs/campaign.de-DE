---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 18%
---
# toBase64

Konvertiert den Puffer oder einen Teil des in Base 64 kodierten Strings.

```text
toBase64 ( [start ] [, length ])
```

## Parameter

**start** Anzahl der zu ignorierenden Bytes am Anfang des Puffers. Das erste Byte entspricht dem Wert 0 (Standardwert).

**length** Anzahl der zu konvertierenden Bytes. Standardmäßig werden alle verbleibenden Bytes berücksichtigt.

## Rückgabewert

Der Inhalt des in Base 64 kodierten Puffers.

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
