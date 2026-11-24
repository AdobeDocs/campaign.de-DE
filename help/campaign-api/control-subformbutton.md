---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 2%
---
# SubFormButton

Schaltfläche zum Öffnen eines Unterformulars.

![SubFormButton-Steuerelement](assets/button.f0aea09a.png)

## Eigenschaften

**backColor - Zeichenfolge** Hintergrundfarbe (btnshadow, weiß).

**border - string** Ändert den Stil des Kontrollentwurfs (solid, double, inset, outset, none).

**disableReadOnly - Zeichenfolge** Verhindert die Übertragung der „read-only“-Eigenschaft auf das Teilformular.

**font-size - integer** Ändert die Schriftgröße.

**img - Zeichenfolge** Zugehöriges Bild.

**label - Zeichenfolge** Beschriftung der Schaltfläche.

**nolabel - Zeichenfolge** Ermöglicht die Ausrichtung der Steuerung an der Titelspalte.

**prebuildSubForm - Zeichenfolge** Initialisiert das Teilformular bei der Erstellung des Steuerelements. Diese Option ist standardmäßig aktiviert, kann jedoch deaktiviert werden, um die erste Anzeige zu beschleunigen.

**erforderlich - boolesch** Das Feld ist obligatorisch.

## Bemerkungen

Beispiel:

```xml
      <input type="subformbutton" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
