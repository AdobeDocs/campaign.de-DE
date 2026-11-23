---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 2%
---
# DiagramEdit

Dieses Steuerelement wird für die Bearbeitung von Diagrammen wie Workflows oder Umfragen verwendet.

![DiagramEdit-Steuerelement](assets/diagramedit.d750db7e.png)

## Eigenschaften

**backColor - Zeichenfolge** Hintergrundfarbe (btnshadow, weiß).

**border - string** Ändert den Stil des Kontrollentwurfs (solid, double, inset, outset, none).

**label - Zeichenfolge** Zugeordnete Bezeichnung.

**nolabel - Boolesch** Zeigt die Bezeichnung als Hilfebubble an.

**readOnly - boolean** Erzwingt, dass das Steuerelement schreibgeschützt ist.

## Bemerkungen

Die Symbolleiste kann personalisiert werden. Jedes Unterelement dieses Steuerelements entspricht zusätzlichen Schaltflächen in der Symbolleiste.

```xml
<input type="diagramEdit" xpath=".">
  <input type="separator"/>
  <input img="xtk:properties.png" label="Properties" resetForm="true" prebuildSubForm="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
  <input type="separator"/>
  <input img="nms:prepare.png" label="Publish" checkModify="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
</input>
```

Weitere Informationen zu den Schaltflächen in der Symbolleiste finden Sie in der Dokumentation zum SubFormButton-Steuerelement.
