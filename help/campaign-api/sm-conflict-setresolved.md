---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 7%
---
# setResolved

Erklärt eine Entität für konfliktfrei.

```text
SetResolved ( String conflictId )
```

## Parameter

**konfliktId** Konfliktkennung.

## Rückgabewert(e)

Keine.

## Bemerkungen

Wenn alle Konflikte gelöst sind, können Sie mit dieser Methode die Entität an ihren normalen Platz zurückversetzen. Vor dem Aufrufen dieser Methode müssen alle widersprüchlichen Attribute und Elemente aufgelöst werden.

## Funktionen

**Schema:** [xtk:conflict](s-xtk-conflict.md)

**static:**

Ja
