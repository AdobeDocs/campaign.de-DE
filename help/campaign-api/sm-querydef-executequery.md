---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 39%
---
# ExecuteQuery

Abrufen von Daten mittels einer Abfrage

```text
XML output = queryDef.ExecuteQuery () const
```

## Parameter

Keine.

## Rückgabewert(e)

**Ausgabe** XML-Ausgabedokument

## Bemerkungen

Die Abfrage unterstützt vier Arten von Vorgängen:

* auswählen
* Abrufen
* getIfExists
* count

## Beispiel

```javascript
var query = NLWS.xtkQueryDef.create(
  {queryDef: {schema: "xtk:workflow", operation: "select", 
    select: {
        node: [{expr: "@id"},
               {expr: "@label"},
               {expr: "@internalName"}] 
    }, 
    where: {
      condition: [{expr: "[folder/@name]='nmsTechnicalWorkflow'"},
                  {expr: "@production = 1"}]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }})

var res = query.ExecuteQuery()

var workflows = res.getElementsByTagName("workflow")
for each (var w in workflows)
  logInfo(w.getAttribute("internalName"))
        
```

## Funktionen

**Schema:** [xtk:queryDef](s-xtk-querydef.md)

**static:**

Nein

**const:**

Ja

**Nur Schlüssel:**

Nein
