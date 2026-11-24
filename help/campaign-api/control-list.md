---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 2%
---
# Liste

Speicherliste.

## Eigenschaften

**backColor - Zeichenfolge** Hintergrundfarbe (btnshadow, weiß).

**border - string** Ändert den Stil des Kontrollentwurfs (solid, double, inset, outset, none).

**editierbar - boolesch** Autorisiert die Listenbearbeitung.

**font-size - integer** Ändert die Schriftgröße.

**form - Zeichenfolge** Das Bearbeitungsformular.

**img - Zeichenfolge** Bild für jede Zeile.

**label - Zeichenfolge** Zugeordnete Bezeichnung.

**nolabel - Boolesch** Keine Beschriftung.

**notitle - boolesch** Spaltentitel werden nicht angezeigt.

**noToolbar - boolean** Blendet die Symbolleiste aus.

**ordered - boolean** Autorisiert die Listenplanung.

**readOnly - boolean** Erzwingt, dass das Steuerelement schreibgeschützt ist.

**toobarAlign - Zeichenfolge** horizontal \| vertikal.

**toobarCaption - Zeichenfolge** Die Bezeichnung wird in der Symbolleiste angezeigt.

**zoom - Boolesch** Zeigt das Bearbeitungsformular an.

**zoomOnAdd - Boolesch** Öffnet ein Formular, wenn eine Zeile hinzugefügt wird.

**xpathIndex - xpath** Der Index der Auswahl wird an dem durch diesen Pfad angegebenen Speicherort gespeichert.

**xpathSelection - xpath** Der Knoten, unter dem der XPATH-Pfad gespeichert wird, um zum ausgewählten Element zu gelangen.

## Bemerkungen

Beispiel 1:

```xml
      <input type="list" xpath="dataTransferStep" nolabel="true" editable="false"
       zoom="true" form="xtk:exportSource" zoomOnAdd="true" img="xtk:script.bmp">
  <input xpath="@name" colSize="15"/>
  <input xpath="@active" editable="true" colSize="15"/>
</input>
```

Beispiel 2:

```xml
<input type="list" xpath="operator" zoom="true">
  <input xpath="@name" colSize="15"/>
  <form>
    <input xpath="@name"/>
  </form>
</input>
```
