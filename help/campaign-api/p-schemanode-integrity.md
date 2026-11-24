---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 20%
---
# Unversehrtheit

Gibt den Integritätstyp der Relation zurück.

```text
integrity
```

## Bemerkungen

Die Eigenschaft kann einen der folgenden Werte annehmen:

* schema.INTEGRITY\_NORMAL - Link vom Typ „Normal“.
* schema.INTEGRITY\_DEFINE - Link vom Typ „Definieren“.
* schema.INTEGRITY\_NEUTRAL - Link vom Typ „neutral“.
* schema.INTEGRITY\_USED - Link vom Typ „Verwendet“.
* schema.INTEGRITY\_OWN - Link vom Typ „own“.
* schema.INTEGRITY\_OWNCOPY - Link vom Typ „owncopy“.

## Funktionen

**Eigenschaft der Klasse:** [SchemaNode](c-schemanode.md)

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
