---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 39%
---
# DeclareTableSpaces

Deklariert die Optionen in der Adobe Campaign-Datenbank, die den Gebrauch spezifischer Tablespaces in der über das externe Konto zugänglichen Remote-Datenbank ermöglichen.

```text
DeclareTableSpaces ( String extAccountId, String tableSpace, String tableSpaceIndex )
```

## Parameter

**extAccountId** Interner Name oder Primärschlüssel des externen Kontos

**tableSpace** Tablespace-Name für Remote-Arbeitstabellen

**tableSpaceIndex** Name des für Indizes zu verwendenden Tablespaces

## Rückgabewert(e)

Keine.

## Funktionen

**Schema:** [nms:extAccount](s-nms-extaccount.md)

**static:**

Ja
