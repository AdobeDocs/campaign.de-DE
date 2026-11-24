---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 16%
---
# Cookies

Gibt die Cookies der Abfrage zurück.

```text
cookies
```

## Bemerkungen

Die -Cookie-Eigenschaft gibt ein -Objekt mit einem entsprechenden Cookie für jede seiner Eigenschaften zurück. Beispiel:

```javascript
var cookies = request.cookies
for(var name in cookies)
{
var value = cookies[name].value
document.write(name + " : " + value + "<br>")
}
```

## Funktionen

**Eigenschaft der Klasse:** [HttpServletRequest](c-httpservletrequest.md)

**Schreibgeschützt:**

Ja

**Verfügbar in:**

* JSSP
* WEBAPP
