---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%
---
# FinalizeMidPrepreparation

Abschließende Analyse eines Versands im Mid-Sourcing-Modus.

```text
[ Number fatalError, String fatalErrorMsg ] = FinalizeMidPreparation ( Number deliveryId, Number errorCode, XML properties, Boolean retry )
```

## Parameter

**deliveryId** Versandkennung

**errorCode** Fehlercode, der von der Analyse in der Marketing-Datenbank zurückgegeben wird (der Fehlercode auf Methodenebene wird dafür nicht verwendet)

**properties** Zu aktualisierende Versandeigenschaften

**retry** Gibt an, ob es sich um einen erneuten Versuch für den Methodenaufruf handelt.

## Rückgabewert(e)

**fatalError** Gibt einen Fehlercode zurück, der den Aufrufer daran hindert, erneute Versuche durchzuführen. Andernfalls kann der Fehler vorübergehend sein.

**fatalErrorMsg** Fehlermeldung, die mit dem &#39;fatalError&#39;-Fehlercode verknüpft ist.

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja
