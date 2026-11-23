---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 3%
---
# spawnWithParameters

Erstellt eine auf einer Vorlage basierende Workflow-Instanz und ruft die Methode [StartWithParameters](sm-workflow-startwithparameters.md) für diese Instanz auf.

```text
Number instanceId = SpawnWithParameters ( String workflowId, XML parameters )
```

## Parameter

**workflowId** Kennung oder interner Name der Workflow-Vorlage.

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

**instanceId** Kennung der aus der Vorlage erstellten Instanz.

## Bemerkungen

Der Befehl wird asynchron ausgeführt und hat keine sofortige Auswirkung nach der Rückgabe der Methode. Der Workflow wird mit dem Konto des aufrufenden Benutzers gestartet, es sei denn, in der Tabelle der Workflow-Logins ist eine bestimmte Anmeldung mit der Vorlage verknüpft. In diesem Fall wird diese Anmeldung verwendet.

## Funktionen

**Schema:** [xtk:workflow](s-xtk-workflow.md)

**static:**

Ja
