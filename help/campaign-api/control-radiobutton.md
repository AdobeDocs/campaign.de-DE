---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 15%
---
# Optionsfeld

Mit einem Optionsfeld können Sie aus verschiedenen Optionen wählen. Die &lt;input>-Tags werden verwendet, um mögliche Optionen aufzuzählen.

![RadioButton-Steuerelement](assets/radio.11bc90a8.png)

## Eigenschaften

**backColor - Zeichenfolge** Hintergrundfarbe (btnshadow, weiß).

**border - string** Ändert den Rahmenstil des Steuerelements (solid, double, inset, outset, none).

**checkedValue - Zeichenfolge** Wert, der mit der Auswahl verknüpft ist.

**font-size - integer** Ändert die Schriftgröße.

**label - Zeichenfolge** Zugeordnete Bezeichnung.

**nolabel - Boolesch** Blendet die zugehörige Beschriftung aus.

**readOnly - boolean** Erzwingt, dass das Steuerelement schreibgeschützt ist.

## Bemerkungen

Beispiel:

```xml
      <input type="RadioButton" xpath="@gender" checkedValue="0" label="Choice 1"/>
<input type="RadioButton" xpath="@gender" checkedValue="1" label="Choice 2"/>
<input type="RadioButton" xpath="@gender" checkedValue="2" label="Choice 3"/>
```
