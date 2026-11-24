---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 36%
---
# fromString

Lädt den Inhalt einer Zeichenfolge in den Puffer.

```text
fromString (string [, codepage ])
```

## Parameter

**string** Die Zeichenfolge.

**codePage** Die Codeseite, die zum Serialisieren der Zeichenfolge im Puffer verwendet wird. Mit diesem optionalen Parameter können Sie die Zeichencodierung angeben. Beispiel:

* ISO-8859-1
* UTF-8
* UTF-16
* US-ASCII
* Shift-JIS
* EUC-KR

## Rückgabewert

Keine.

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
