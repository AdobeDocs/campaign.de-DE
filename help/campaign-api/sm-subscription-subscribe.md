---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 32%
---
# Anmelden

Meldet einen Empfänger für einen Informationsdienst an oder aktualisiert ein Abonnement.

```text
Subscribe ( String serviceName, XML recipient, Boolean create )
```

## Parameter

**serviceName** Liste der Namen der Informationsdienste (durch Kommata getrennt)

**recipient** zu registrierender und optional zu erstellender Empfänger

**erstellen** Empfänger erstellen, wenn er nicht existiert

## Rückgabewert(e)

Keine.

## Beispiel

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Subscribe("SVC1", recipient, false)
        
```

## Funktionen

**Schema:** [nms:subscription](s-nms-subscription.md)

**static:**

Ja
