---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# generateRegisterHookScript

Erzeugt das Erweiterungsscript, das beim &#39;register&#39;-Ereignis von &#39;appSubscriptionRcp&#39; aufgerufen wird.

```text
String JSScriptStr = generateRegisterHookScript ( XML additionalXmlNodes )
```

## Parameter

**additionalXmlNodes** XML-Knoten, die die Verknüpfung zwischen zusätzlichen Parametern und dem Zielzuordnungsfeld enthalten.

## Rückgabewert(e)

**JSScriptStr** JS-Skript, das die Verknüpfung zusätzlicher Parameter mit Feldern im Zielgruppen-Mapping ermöglicht.

## Funktionen

**Schema:** [nms:mobileApp](s-nms-mobileapp.md)

**static:**

Ja
