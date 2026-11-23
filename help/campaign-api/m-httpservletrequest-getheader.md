---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '30'
ht-degree: 20%
---
# getHeader

Gibt ein im Abfrage-Header definiertes Attribut zurück.

```text
getHeader (name)
```

## Parameter

**name** Name des Attributs der Kopfzeile.

## Rückgabewert

Keine.

## Bemerkungen

Beispiel:

```javascript
Host: <%= request.getHeader("host") %>
```

## Funktionen

**Methode der Klasse:** [HttpServletRequest](c-httpservletrequest.md)

**Verfügbar in:**

* JSSP
* WEBAPP
