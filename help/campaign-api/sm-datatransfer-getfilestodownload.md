---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 28%
---
# GetFilesToDownload

Auflistung der auf dem Server befindlichen Dateien für diese Übertragung

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number jobId )
```

## Parameter

**jobId** Übertragungskennung

## Rückgabewert(e)

**filesToDownload** Gibt die Liste der Dateien zurück, die als Element heruntergeladen werden können \[dataTransfer/properties/filesToDownload\]

**filesNotToDownload** Gibt die Liste der Dateien zurück, die nicht als Element heruntergeladen werden können \[dataTransfer/properties/filesNotToDownload\]

## Funktionen

**Schema:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**static:**

Ja
