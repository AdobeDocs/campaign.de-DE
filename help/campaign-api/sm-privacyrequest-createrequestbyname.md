---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 6%
---
# CreateRequestByName

Erstellen einer neuen Datenschutzanfrage mit dem internen Namespace-Namen

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending Number regulation )
```

## Parameter

**namespaceName** Interner Namespace-Name

**ReconciliationValue** Abstimmwert

**type** Abstimmwert

**confirmDeletePending:** zum Löschen von Daten bestätigen

**regulation** Regelungstyp mit den folgenden Werten:

```xml
           
               <value label="GDPR" name="gdpr" value="1"/>
            <value label="CCPA" name="ccpa" value="2"/>
            <value label="PDPA" name="pdpa" value="3"/>
            <value label="LGPD" name="lgpd" value="4"/>
           
           
```

## Rückgabewert(e)

**id** ID der neu erstellten Anfrage

## Funktionen

**Schema:** [nms:privacyRequest](s-nms-privacyrequest.md)

**static:**

Ja
