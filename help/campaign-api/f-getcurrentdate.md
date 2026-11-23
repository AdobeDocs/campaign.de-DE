---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 31%
---
# getCurrentDate

Gibt das aktuelle Datum des Datenbank-Servers aus.

```text
getCurrentDate ()
```

## Parameter

Keine.

## Rückgabewert

Das aktuelle Datum des Datenbank-Servers.

## Bemerkungen

Beispiel:

```javascript
      date = formatDate(getCurrentDate(),"%4Y/%2M/%2D %02H:%02N:%02S")
```

Weitere Informationen zur Funktion formatDate() finden Sie unter [formatDate(date, format)](f-formatdate.md)

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
