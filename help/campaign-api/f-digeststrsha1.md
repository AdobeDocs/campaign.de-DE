---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 21%
---
# digestStrSha1

> Warnung:
>
> Diese Funktion darf nicht verwendet werden, um einen Hash auf der Grundlage von personenbezogenen Daten zu erstellen.

Berechnet den SHA-1-Hash einer Zeichenfolge. Die Zeichenfolge wird vor der Berechnung automatisch in UTF-8 codiert.

```text
digestStrSha1 (string)
```

## Parameter

**string** Die Zeichenfolge, in der der Hash berechnet werden soll.

## Rückgabewert

Der SHA-1-Hash der als Parameter übergebenen Zeichenfolge.

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
