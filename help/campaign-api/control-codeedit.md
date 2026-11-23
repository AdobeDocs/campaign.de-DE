---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 8%
---
# Code bearbeiten

Steuerelement zum Bearbeiten des Quell-Codes.

![CodeEdit-Steuerelement](assets/codeedit.8a744c8b.png)

## Eigenschaften

**backColor - Zeichenfolge** Hintergrundfarbe (btnshadow, weiß).

**border - string** Ändert den Stil des Kontrollentwurfs (solid, double, inset, outset, none).

**contentType - Zeichenfolge** Die Sprache des Quellcodes, die für die syntaktische Farbgestaltung und andere mit der Sprache verknüpfte Optionen verwendet wird. Folgende Sprachen werden unterstützt:

* Standard
* XML
* DTD
* XSL
* HTML
* txt
* Javascript
* SQL

Andere Sprachen können auch hinzugefügt werden, indem die Datei editor.cfg im selben Verzeichnis wie nlclient.exe bearbeitet wird.

**font-size - integer** Ändert die Schriftgröße.

**label - Zeichenfolge** Zugeordnete Bezeichnung.

**nolabel - Boolesch** Blendet die zugehörige Beschriftung aus.

**readOnly - boolean** Erzwingt, dass das Steuerelement schreibgeschützt ist.

**toolbar - boolean** Blendet die Symbolleiste ein oder aus.

**toolbarAlign - Zeichenfolge** Position der Symbolleiste: horizontal oder vertikal.

## Bemerkungen

Beispiel:

```xml
<input xpath="code" nolabel="true" type="CodeEdit"
       contentType="JavaScript" toolbar="true" toolbarAlign="horizontal"/>
```
