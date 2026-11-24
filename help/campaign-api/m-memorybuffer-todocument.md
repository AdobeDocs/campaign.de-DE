---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 30%
---
# toDocument

Gibt ein XML-Dokument aus dem Textinhalt dieses Puffers zurück.

```text
toDocument ( [codePage ])
```

## Parameter

**codePage** Eine Ganzzahl, die die verwendete Zeichenseite codiert. Standardmäßig ist MemoryBuffer.CODEPAGE\_UTF8 eingestellt.

## Rückgabewert

Ein [DOMDocument](c-domdocument.md)-Objekt.

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
