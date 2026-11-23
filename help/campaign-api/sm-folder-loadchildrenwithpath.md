---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 22%
---
# LoadChildrenWithPath

Lädt die Liste der untergeordneten Elemente eines Knotens

```text
XML result = LoadChildrenWithPath ( String parentKey, String folderFilter, Boolean writeAccess, String fullName, String path, Boolean sort )
```

## Parameter

**parentKey** Übergeordneter Schlüssel

**folderFilter** Ordner filtern

**writeAccess** Der zurückgegebene Ordner muss schreibbar sein

**fullName** Vollständiger Name des ausgewählten Knotens

**path** Vollständiger Name des ausgewählten Knotens

**sort** Sortieren nach alphabetischer Reihenfolge

## Rückgabewert(e)

**result** Ergebnisdokument

## Funktionen

**Schema:** [xtk:folder](s-xtk-folder.md)

**static:**

Ja
