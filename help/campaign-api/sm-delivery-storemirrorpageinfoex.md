---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 22%
---
# StoreMirrorPageInfoEx

Fügt die Informationen bezüglich der Mirrorseitenerzeugung für eine Versandkontingentkollektion hinzu.

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfoEx ( Number deliveryId, Boolean notification, Number partsCount, Number firstPartId, Number notificationId )
```

## Parameter

**deliveryId** Versandkennung

**Benachrichtigung** Ist es eine Benachrichtigung?

**partsCount** Anzahl von Teilen

**firstPartId** Kennung des ersten Teils

**notificationId** Benachrichtigungskennung

## Rückgabewert(e)

**fatalError** Gibt einen Fehlercode zurück, der den Aufrufer daran hindert, erneute Versuche durchzuführen. Andernfalls kann der Fehler vorübergehend sein.

**fatalErrorMsg** Fehlermeldung, die mit dem &#39;fatalError&#39;-Fehlercode verknüpft ist.

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Ja
