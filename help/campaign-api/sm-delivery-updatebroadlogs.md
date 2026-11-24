---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 31%
---
# UpdateBroadlogs

Aktualisiert den Status der Versandlogs, verarbeitet die Fehler und aktualisiert den Versandzähler.

```text
UpdateBroadLogs ( Number deliveryId, XML logs, Boolean deliveryMustExist )
```

## Parameter

**deliveryId** Versandkennung

**logs** Sammlung der zu :broadLog nms: Datensätze (@id, @status, @eventDate und @lastModified müssen angegeben werden)

**deliveryMustExist** Gibt an, ob ein Fehler bei einer ungültigen Versandkennung ausgelöst werden soll.

## Rückgabewert(e)

Keine.

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja
