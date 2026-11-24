---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 5%
---
# getAsModel

```text
XML parentOut = getAsModel ( String refIdName, Number refIdValue, XML selection, XML parentIn )
```

## Parameter

**refIdName** Attribut, das die Kennung der zuzuordnenden Entität enthält (z. B. „delivery-id„)

**refIdValue** Kennung der zuzuordnenden Entität (Wert aus „refIdName„)

**selection** Element mit den ausgewählten Vorlagenkennungen

**parentIn** Element mit den vorhandenen Testadressen

## Rückgabewert(e)

**parentOut** Gibt das Element mit den hinzugefügten neuen Vorlagen zurück.

## Funktionen

**Schema:** [nms:seedMember](s-nms-seedmember.md)

**static:**

Ja
