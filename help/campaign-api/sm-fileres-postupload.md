---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 25%
---
# Nach dem Hochladen

Abschließende Speicherung einer Ressource nach dem Upload auf den Server in Abhängigkeit vom definierten Speichertyp.

```text
fileRes.PostUpload ( XML params )
```

## Parameter

**params** Für eine Speicherung vom Typ „workspace“: @formerFileName enthält den vorherigen Namen im Workspace. Wenn Sie die Entität sofort speichern möchten: @immediateSave muss auf „true“ gesetzt sein

## Rückgabewert(e)

Keine.

## Funktionen

**Schema:** [xtk:fileRes](s-xtk-fileres.md)

**static:**

Nein

**const:**

Nein

**Nur Schlüssel:**

Nein
