---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 20%
---
# verschleiern

Verschleiert eine Ganzzahl in einer Zeichenfolge. Der ursprüngliche Wert kann durch Aufrufen von &quot;[&quot; wiederhergestellt ](f-unobfuscate.md).

```text
obfuscate (value [, size ] [, version ])
```

## Parameter

**value** Die zu verschleiernde Ganzzahl.

**size** Die Größe der aus der Verschleierung resultierenden Zeichenfolge. Eine Ganzzahl zwischen 6 und 10. 6 standardmäßig.

**version** Die anzuwendende Verschleierungsversion. Standardmäßig 0.

## Rückgabewert

Eine Zeichenfolge, die die verschleierte Ganzzahl darstellt.

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
