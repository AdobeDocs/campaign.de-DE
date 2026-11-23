---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 40%
---
# Auflistungen

Gibt die Tabelle zurück, die die Liste der in [&#x200B; Schema &#x200B;](c-enumeration.md) Auflistungen enthält.

```text
enumerations
```

## Bemerkungen

Beispiel:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var e in schema.enumerations)
{
  logInfo(e.name)
}
```

## Funktionen

**Eigenschaft der Klasse:** [Schema](c-schema.md)

**Schreibgeschützt:**

Ja

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
