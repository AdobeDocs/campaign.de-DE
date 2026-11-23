---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 3%
---
# LinkListChoice

Auswahl einer oder mehrerer Entitäten.

## Eigenschaften

**backColor - Zeichenfolge** Hintergrundfarbe (btnshadow, weiß).

**border - string** Ändert den Stil des Kontrollentwurfs (solid, double, inset, outset, none).

**dblClickAction - Zeichenfolge** Name des Formulars, das beim Doppelklick geöffnet werden soll.

**font-size - integer** Ändert die Schriftgröße.

**label - Zeichenfolge** Zugeordnete Bezeichnung.

**multiSelection - Boolesch** Lässt die Mehrfachauswahl zu

**nolabel - Boolesch** Blendet die zugehörige Beschriftung aus.

**readOnly - boolean** Erzwingt, dass das Steuerelement schreibgeschützt ist.

**serialize - boolean** Speichert die letzte Auswahl in der Benutzerkonfiguration.wu

**xpath-link - Zeichenfolge** Link der Liste.

## Bemerkungen

Beispiele:

```xml
      <input xpath="." type="linkListChoice" xpath-link="operator">
  <input xpath="[/]"  label="Operator or named right "/>
  <input xpath="@type"/>
  <input xpath="comment"/>
  <sysFilter>
    <condition expr="@type <> 1"/>
  </sysFilter>
  <orderBy>
    <node expr="@type"/>
  </orderBy>
</input>
```
