---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 29%
---
# CreateRequestByName

Neue DSGVO-Anfrage mit dem internen Namespace-Namen erstellen

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending )
```

## Parameter

**namespaceName** Interner Namespace-Name

**ReconciliationValue** Abstimmwert

**type** Abstimmwert

**confirmDeletePending:** zum Löschen von Daten bestätigen

## Rückgabewert(e)

**id** ID der neu erstellten Anfrage

## Funktionen

**Schema:** [nms:gdprRequest](s-nms-gdprrequest.md)

**static:**

Ja
