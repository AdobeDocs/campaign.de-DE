---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 23%
---
# toXML

Gibt ein XML-JavaScript-Objekt zurück, das aus dem Inhalt von „MemoryBuffer[&#x200B; abgerufen &#x200B;](c-memorybuffer.md). Diese Funktion ist veraltet. Verwenden Sie [toDocument()](m-memorybuffer-todocument.md)

```text
toXML ( [codePage ])
```

## Parameter

**codePage** Eine Ganzzahl, die die Seite der verwendeten Zeichen codiert. Standardmäßig ist MemoryBuffer.CODEPAGE\_UTF8.

## Rückgabewert

Der Inhalt eines Stempels in Form eines XML-Objekts.

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
