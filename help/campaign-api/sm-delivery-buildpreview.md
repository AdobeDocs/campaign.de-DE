---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 34%
---
# BuildPreview

Erstellt die Vorschau eines Versandinhalts oder einer Ausgabedateizeile (im externen Modus).

```text
[ XML preview, XML queryResult ] = delivery.BuildPreview ( XML params ) const
```

## Parameter

**params** Empfängerfilterbedingung (@filter = &#39;@id = 5673&#39;), Inhaltskennung (@content = &#39;html&#39;, &#39;text&#39;, &#39;sms&#39;, &#39;webContent1&#39;, &#39;outputFile&#39;…), @targetPart = 1345686…

## Rückgabewert(e)

**preview** Gibt alle Parameter der generierten Vorschau zurück.

**queryResult** Gibt die zur Berechnung der Vorschau geladenen Daten zurück.

## Funktionen

**Schema:** [nms:delivery](s-nms-delivery.md)

**static:**

Nein

**const:**

Ja

**Nur Schlüssel:**

Nein
