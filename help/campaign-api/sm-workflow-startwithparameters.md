---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 5%
---
# startWithParameters

Startet einen Workflow unter Übermittlung von Parametern

```text
StartWithParameters ( String workflowId, XML parameters )
```

## Parameter

**workflowId** Kennung oder interner Name des Workflows.

**parameter** Parameter, die an die Instanz übergeben werden. Diese Parameter werden zu Instanzvariablen des Workflows. Dieses Argument ist ein XML-Element, dessen Name Variablen sein müssen und nur Attribute enthalten darf. Beispiel:

```xml
<variables foo="abc" bar="def">
```

Die JavaScript-Skripte innerhalb des Workflows können auf diese Variablen über das „instance.vars“-Objekt zugreifen:

```javascript
    var foo = instance.vars.foo   // "abc"
    var bar = instance.vars.bar   // "def"
            
```

## Rückgabewert(e)

Keine.

## Bemerkungen

Der Befehl wird asynchron ausgeführt und hat keine sofortige Auswirkung nach der Rückgabe der Methode.

## Funktionen

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**static:**

Ja
