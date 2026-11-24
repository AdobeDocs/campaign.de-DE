---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 9%
---
# öffnen

Öffnet die Datei im Lese- oder Schreibmodus.

```text
open ( [mode ] [, codepage ])
```

## Parameter

**mode** Dateiöffnungsmodus. Der Modus kann einer von mehreren Werten sein:

* „r“ - Öffnet die Datei im schreibgeschützten Modus. Dieser Modus ist der Standardmodus.
* „w“ - Öffnet die Datei im Schreibmodus.
* „a“ - Öffnet die Datei im &#39;append&#39;-Modus, die in die Datei geschriebenen Daten werden am Ende angehängt.

**codepage** Die Dateicodierung. Die Kodierung kann einer der folgenden Werte sein:

* File.CODEPAGE\_CURRENT - Dies ist die Standard-Codepage.
* file.CODEPAGE\_OEM
* file.CODEPAGE\_MAC
* file.CODEPAGE\_THREAD
* file.CODEPAGE\_LATIN1
* FILE.CODEPAGE\_LATIN2
* FILE.CODEPAGE\_ISOLATIN1
* FILE.CODEPAGE\_ISOLATIN2
* FILE.CODEPAGE\_OEMLATIN1
* FILE.CODEPAGE\_OEMLATIN2
* FILE.CODEPAGE\_UTF7
* FILE.CODEPAGE\_UTF8
* FILE.CODEPAGE\_ISOLATIN9
* file.CODEPAGE\_OEMUS
* FILE.CODEPAGE\_SHIFTJIS
* file.CODEPAGE\_BIG5
* FILE.CODEPAGE\_CHINESE
* FILE.CODEPAGE\_EUKOREAN
* file.CODEPAGE\_UTF16LE
* FILE.CODEPAGE\_UTF16BE

## Rückgabewert

Keine.

## Bemerkungen

Wenn die Datei nicht geöffnet werden kann, wird eine Ausnahme ausgelöst.

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
