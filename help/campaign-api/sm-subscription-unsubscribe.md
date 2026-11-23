---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 41%
---
# Abmelden

Meldet einen Empfänger von einem Informationsdienst ab

```text
Unsubscribe ( String serviceName, XML recipient )
```

## Parameter

**serviceName** Liste der Namen der Informationsdienste (durch Kommata getrennt)

**recipient** recipient

## Rückgabewert(e)

Keine.

## Beispiel

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Unsubscribe("SVC1", recipient)
        
```

## Funktionen

**Schema:** [nms:subscription](s-nms-subscription.md)

**static:**

Ja
