---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 31%
---
# RecipientSubscribe

Meldet die ausgewählten Empfänger für eine Liste an Informationsdiensten an oder ab.

```text
XML confirmationIds = RecipientSubscribe ( XML recipientList, XML serviceList, Boolean subscribe, XML sendConfirmation )
```

## Parameter

**recipientList** Empfängerliste

**serviceList** Liste der Dienste

**Abonnieren** Abonnieren/Abmelden

**sendConfirmation** Senden einer Bestätigungsnachricht

## Rückgabewert(e)

**confirmationIds** Liste der Bestätigungs-IDs

## Funktionen

**Schema:** [nms:subscription](s-nms-subscription.md)

**static:**

Ja
