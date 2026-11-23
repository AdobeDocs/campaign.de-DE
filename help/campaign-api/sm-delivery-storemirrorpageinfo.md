---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 23%
---
# StoreMirrorPageInfo

Fügt die Informationen bezüglich der Mirrorseitenerzeugung für eine Versandkontingentkollektion hinzu.

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfo ( Number deliveryId, Number partsCount, Number firstPartId, Number lastPartId )
```

## Parameter

**deliveryId** Versandkennung

**partsCount** Anzahl von Teilen

**firstPartId** Kennung des ersten Teils

**lastPartId** Kennung des letzten Kontingents

## Rückgabewert(e)

**fatalError** Gibt einen Fehlercode zurück, der den Aufrufer daran hindert, erneute Versuche durchzuführen. Andernfalls kann der Fehler vorübergehend sein.

**fatalErrorMsg** Fehlermeldung, die mit dem &#39;fatalError&#39;-Fehlercode verknüpft ist.

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja
