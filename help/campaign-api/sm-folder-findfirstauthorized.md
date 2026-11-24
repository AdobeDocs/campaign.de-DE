---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 28%
---
# FindFirstAuthorized

Findet den ersten Ordner, der für den aktuellen Benutzer zugänglich ist und der die &#39;folderFilter&#39;-Bedingung erfüllt.

```text
XML folderEntity = FindFirstAuthorized ( String folderFilter, Boolean writeAccess, Number orgUnit )
```

## Parameter

**folderFilter** Ordner filtern

**writeAccess** Der zurückgegebene Ordner muss schreibbar sein

**orgUnit** Der ausgegebene Ordner muss mit der angegebenen Organisationseinheit kompatibel sein

## Rückgabewert(e)

**folderEntity** Gibt die verknüpfte Ordnerentität zurück (Null, wenn kein Ordner gefunden wird)

## Funktionen

**Schema:** [xtk:folder](s-xtk-folder.md)

**static:**

Ja
