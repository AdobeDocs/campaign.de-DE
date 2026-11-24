---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 7%
---
# formatDate

Formatiert ein Datum als Zeichenfolge.

```text
formatDate (date, format [, timeZone ])
```

## Parameter

**date** Das zu konvertierende Datum.

**format** Die Zeichenfolge, die das zu verwendende Format beschreibt. Zur Formatierung der verschiedenen Teile des Datums werden die folgenden Zeichen verwendet:

* J - Jahr
* M - Monat des Jahres (1-12)
* B - Monatsname
* D - Tag des Monats (1-31)
* A - Tagesname
* J - Tag des Jahres (1-366)
* W - Woche des Jahres
* H - Stunde (0-23)
* I - Stunde (1-12)
* n - Minuten (0-59)
* s - Sekunden (0-59)
* P - AM/PM

Sie können eine Zahl vor bestimmten dieser Zeichen angeben. Auf die Zeichen A und B kann ein „l“ folgen, um den vollständigen Namen anstelle der gekürzten Version zu verwenden, oder ein „i“, um den Namen auf Englisch zu verwenden. Beispiele:

* &quot;%4Y/%2M/%2D“ => 2000/01/24.
* &quot;%A %D %B %4Y“ => Mo 24 Jan 2000.
* &quot;%Al %d %Bl %4y“ => Montag, 24. Januar 2000.
* &quot;%02H:%02N:%02S“ zeigt die Stunde, die Minuten und die Sekunden auf zwei Zahlen an.

**timeZone** Zeichenfolge, die der Zeitzone entspricht. Mögliche Werte sind im Auflistungsschema xtk:common:timezone angegeben.

## Rückgabewert

Eine Zeichenfolge, die das Datum im angeforderten Format darstellt.

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
