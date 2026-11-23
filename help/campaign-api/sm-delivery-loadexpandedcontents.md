---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 38%
---
# LoadExpandedContents

Lädt eine Komponenten-Liste zur Vorab-Bearbeitung einschließlich der abhängigen Elemente (Gestaltungsbausteine, Optionen, zusätzliche Script-Objekte usw.).

```text
XML material = delivery.LoadExpandedContents ( String ids ) const
```

## Parameter

**ids** Liste der Komponentenkennungen, durch Kommas getrennt (z. B.: „option\|NmsServer\_URL\|text,includeView\|UnsubscriptionLink\|html„)

## Rückgabewert(e)

**material** Gibt den Inhalt als „material“-Element zurück.

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Nein

**const:**

Ja

**Nur Schlüssel:**

Nein
