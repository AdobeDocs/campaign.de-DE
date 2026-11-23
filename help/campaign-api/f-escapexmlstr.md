---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 37%
---
# escapeXmlStr

Konvertiert eine Zeichenfolge in das XML-Format.

```text
escapeXmlStr (value)
```

## Parameter

**value** Zu konvertierender String.

## Rückgabewert

Die Zeichenfolge nach der Konvertierung.

## Bemerkungen

Die Funktion wandelt die Zeichen &amp;, &lt;, > und \\&quot; in die entsprechenden Escape-Sequenzen um:

* &Amp;
* &lt; &lt;
* &#x200B;> >
* &quot; &quot;

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
