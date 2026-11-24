---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 33%
---
# Dateien existieren

Prüft, ob Dateien bereits auf dem Server (oder in der Ressourcen-Tabelle) existieren.

```text
XML exist = FilesExist ( XML files )
```

## Parameter

**Dateien** Liste der Dateien (@name) und ihrer MD5-Schlüssel (@md5), sowie ein boolescher Wert, der angibt, ob es sich um eine Ressource handeln kann (@checkResource).

## Rückgabewert(e)

**vorhanden** Ergebnisliste (@md5 und @exists)

## Funktionen

**Schema:** [xtk:job](s-xtk-job.md)

**static:**

Ja
