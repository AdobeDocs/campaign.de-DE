---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 22%
---
# DigestStrMd5

> Warnung:
>
> Diese Funktion darf nicht verwendet werden, um einen Hash auf der Grundlage von personenbezogenen Daten zu erstellen.

Berechnet die MD5-Hash-Funktion für eine Zeichenfolge. Die Zeichenfolge wird vor der Berechnung automatisch in UTF-8 codiert.

```text
digestStrMd5 (string)
```

## Parameter

**string** Die Zeichenfolge, für die die Hash-Funktion berechnet werden soll.

## Rückgabewert

Der MD5-Hash der als Parameter übergebenen Zeichenfolge.

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
