---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 20%
---
# GetSource

Quellcode der Formularverwaltung

```text
[ String source, XML logs ] = GetSource ( String formId, String target, Boolean compiled, String version )
```

## Parameter

**formId** Formularkennung.

**target** Dokumenttyp, der generiert werden soll.

**compiled** Vollständige Version wiederherstellen

**version** Dokumentversion zum Generieren.

## Rückgabewert(e)

**source** Source-Code.

**logs** Generationsprotokolle.

## Funktionen

**Schema:** [xtk:abstractForm](s-xtk-abstractform.md)

**static:**

Ja
