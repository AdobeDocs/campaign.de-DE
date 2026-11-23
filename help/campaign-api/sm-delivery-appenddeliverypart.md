---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 13%
---
# AppendDeliveryPart

Fügt ein Kontigent zu einem in Vorbereitung befindlichen Versand hinzu

```text
[ Number deliveryPartId, Number fatalError, String fatalErrorMsg ] = AppendDeliveryPart ( XML deliveryPart, Boolean retry )
```

## Parameter

**deliveryPart** Dokument, das das Versandkontingent (oder eine Versandkontingentkollektion) darstellt.

**retry** Gibt an, ob es sich um einen neuen Versuch handelt, dieses Versandteil zu übermitteln.

## Rückgabewert(e)

**deliveryPartId** Kennung des Versandkontingents in der Datenbank (wenn es sich nicht um eine Sammlung handelt)

**fatalError** Gibt einen Fehlercode zurück, der den Aufrufer daran hindert, erneute Versuche durchzuführen. Andernfalls kann der Fehler vorübergehend sein.

**fatalErrorMsg** Fehlermeldung, die mit dem &#39;fatalError&#39;-Fehlercode verknüpft ist.

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja
