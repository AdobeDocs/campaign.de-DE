---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 20%
---
# setContentType

Ändert den Dokumenttyp der Antwort.

```text
setContentType (name)
```

## Parameter

**name** MIME-Typ des Dokuments.

## Rückgabewert

Keine.

## Bemerkungen

Beispiel:

```javascript
      response.setContentType("text/html;charset=ISO-8859-1")
```

## Funktionen

**Methode der Klasse:** [HttpServletResponse](c-httpservletresponse.md)

**Verfügbar in:**

* JSSP
* WEBAPP
