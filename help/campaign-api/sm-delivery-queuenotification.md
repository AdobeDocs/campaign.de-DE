---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 23%
---
# QueueNotification

Einreihung einer Kreation in die Warteschlange und Unterbreitung einer Benachrichtigung von einer Vorlage ausgehend.

```text
QueueNotification ( String scenarioName, XML target )
```

## Parameter

**scenarioName** Interner Name der Vorlage

**target** Zielpopulation des Versands

## Rückgabewert(e)

Keine.

## Bemerkungen

Diese API kann nur im Rahmen von Web-Anwendungen/Online-Umfragen verwendet werden. Im Gegensatz zu SubmitNotification wird bei QueueNotification ein dedizierter Thread für Benachrichtigungen in der Warteschlange verwendet.

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja
