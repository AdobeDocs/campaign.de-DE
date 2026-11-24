---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# GetFilesToDownload

Gibt die Liste der den Versand betreffenden Dateien aus, die auf dem Server verfügbar sind.

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number deliveryId )
```

## Parameter

**deliveryId** Versandkennung

## Rückgabewert(e)

**filesToDownload** Gibt die Liste der Dateien zurück, die als Element \[properties/filesToDownload\] heruntergeladen werden können

**filesNotToDownload** Gibt die Liste der Dateien zurück, die nicht als Element \[properties/filesNotToDownload\] heruntergeladen werden können

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja
