---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 21%
---
# escapeUrl

Konvertiert einen String zum Einfügen in eine URL.

```text
escapeUrl (value)
```

## Parameter

**value** Zu konvertierender String.

## Rückgabewert

Die Zeichenfolge nach der Konvertierung.

## Bemerkungen

Die Funktion wandelt andere nicht alphanumerische Zeichen als $-\_.\!\*&#39;(),?/:@&amp;= in den entsprechenden Hexadezimalwert um. Die Funktion entspricht der RFC1738-Spezifikation und ermöglicht nur die Codierung von ISO-Latin-Zeichen. Verwenden Sie zum Codieren von UTF-8-Zeichen die JavaScript-Funktion encodeURIComponent() . Beispiel:

```javascript
escapeUrl("a#value!")               // "a%23value!"
escapeUrl("Système d'exploitation") // "Syst%E8me%20d'exploitation"
```

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
