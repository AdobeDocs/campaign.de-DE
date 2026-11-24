---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 3%
---
# SubFormLink

Link, der ein Teilformular öffnet.

![SubFormLink-Steuerelement](assets/urlbutton.d1cf6f42.png)

## Eigenschaften

**backColor - Zeichenfolge** Hintergrundfarbe (btnshadow, weiß).

**border - string** Ändert den Stil des Kontrollentwurfs (solid, double, inset, outset, none).

**disableReadOnly - Zeichenfolge** Verhindert die Übertragung der „read-only“-Eigenschaft auf das Teilformular.

**font-size - integer** Ändert die Schriftgröße.

**img - Zeichenfolge** Zugehöriges Bild.

**label - Zeichenfolge** Schaltflächenbezeichnung.

**nolabel - Zeichenfolge** Ermöglicht die Ausrichtung des Steuerelements an der Spalte „label“.

**prebuildSubForm - Zeichenfolge** Initialisiert das Teilformular beim Erstellen des Steuerelements. Diese Option ist standardmäßig aktiviert, kann jedoch deaktiviert werden, um die erste Anzeige zu beschleunigen.

## Bemerkungen

Beispiel:

```xml
      <input type="subformlink" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
