---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 18%
---
# EvaluateTemplate

Wertet eine JavaScript-Vorlage aus (&lt;%= … %>).

```text
evaluateTemplate (template)
```

## Parameter

**template** Die auszuwertende Vorlage.

## Rückgabewert

Die Zeichenfolge nach dem Ersetzen der Ausdrücke zwischen &lt;% und %>.

## Bemerkungen

Beispiel:

```javascript
      vars.filename = evaluateTemplate(activity.filename)
```

## Funktionen

**Verfügbar in:**

* Workflow
