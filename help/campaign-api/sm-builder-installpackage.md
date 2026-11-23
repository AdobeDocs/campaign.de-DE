---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 21%
---
# Package installieren

Package installieren

```text
InstallPackage ( XML parameters )
```

## Parameter

**parameters** XML-Element, das das zu importierende Paket enthält.

## Rückgabewert(e)

Keine.

## Bemerkungen

Ein von der SpecFile.Generate()-Methode generiertes Paket muss in einem Builder-Element gekapselt sein. Beispiel:

```javascript
var params =
  {builder:
    {package:
      { ... }
    }
  }

NLWS.xtkBuilder.InstallPackage(params)
```

## Funktionen

**Schema:** [xtk:builder](s-xtk-builder.md)

**static:**

Ja
