---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 21%
---
# Parameter

Gibt die Abfrageparameter zurück.

```text
parameters
```

## Bemerkungen

Die Eigenschaft „parameters“ gibt ein Objekt mit Eigenschaften zurück, die mit einem Parameter der Abfrage übereinstimmen. Beispiel:

```javascript
var parameters = request.parameters
for(var name in parameters)
{
var value = parameters[name]
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
