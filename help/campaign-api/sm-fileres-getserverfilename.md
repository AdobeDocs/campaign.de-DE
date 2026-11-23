---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 51%
---
# GetServerFileName

Gibt den Dateinamen auf dem Server aus, welcher zuvor, wenn nötig, in das Upload-Verzeichnis kopiert wurde.

```text
String serverFileName = fileRes.GetServerFileName ()
```

## Parameter

Keine.

## Rückgabewert(e)

**serverFileName** Vollständiger Name der Datei auf dem Server (leer, wenn die Datei nicht gefunden wurde).

## Beispiel

```javascript
var query = xtk.queryDef.create(
  {queryDef: {schema: "xtk:fileRes", operation: "get", 
    select: {
      node: [
      {expr: "@label"}, 
      {expr: "@originalName"}, 
      {expr: "@storageType"}, 
      {expr: "@fileName"}, 
      {expr: "@md5"}]
    }, 
    where: {
      condition: {expr: "@id = 4216"}
    }
  }})

var fileRes = xtk.fileRes.create(query.ExecuteQuery())
var sFileName = fileRes.GetServerFileName();
        
```

## Funktionen

**Schema:** [xtk:fileRes](s-xtk-fileres.md)

**static:**

Nein

**const:**

Nein

**Nur Schlüssel:**

Nein
