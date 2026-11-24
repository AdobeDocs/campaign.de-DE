---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 6%
---
# WebPostUpload

Abschließendes Speichern der Ressource nach dem Upload (von einer Web-Seite) auf den Server in Abhängigkeit vom verwendeten Speichertyp. Ruft die Codepage und den Inhaltstyp ab.

```text
fileRes.WebPostUpload ( XML params )
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
