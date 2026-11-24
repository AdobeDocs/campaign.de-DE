---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 1%
---
# LinkList

Steuerelement zum Bearbeiten von Sammlungen.

![LinkList-Steuerelement](assets/linklist.8b71bb0e.png)

## Eigenschaften

**addButton - Boolesch** Zeigt die Schaltfläche zum Hinzufügen an. Diese Option ist nur wirksam, wenn die Option hideEditButtons aktiviert ist.

**backColor - Zeichenfolge** Hintergrundfarbe (btnshadow, weiß).

**border - string** Ändert den Stil des Kontrollentwurfs (solid, double, inset, outset, none).

**dblClickAction - Zeichenfolge** Name des Formulars, das beim Doppelklick geöffnet werden soll.

**delButton - boolean** Zeigt die Schaltfläche „Löschen“ an. Diese Option ist nur wirksam, wenn die Schaltfläche „hideEditButtons“ aktiviert ist.

**enumImage - Zeichenfolge** Name der Systemaufzählung, die zum Anzeigen des Bildes jeder Zeile verwendet wird.

**font-size - integer** Ändert die Schriftgröße.

**form - Zeichenfolge** Formular zur Link-Bearbeitung.

**hideEditButtons - boolean** Blendet die Schaltflächen zum Hinzufügen, Löschen und Bearbeiten aus.

**img - Zeichenfolge** Bild.

**label - Zeichenfolge** Zugeordnete Bezeichnung.

**nolabel - Boolesch** Keine Beschriftung vor dem Steuerelement.

**noToolbar - boolean** Blendet die Symbolleiste aus.

**orderBy - Element** Listenplanung.

**readOnly - boolean** Erzwingt, dass das Steuerelement schreibgeschützt ist.

**sysFilter - Element** Listenfilterung.

**toobarAlign - Zeichenfolge** horizontal \| vertikal.

**toobarCaption - Zeichenfolge** Die Bezeichnung wird in der Symbolleiste angezeigt.

**xpath-link - Zeichenfolge** Link der Liste (siehe Beispiel zu Gruppen).

**xpathIndex - Zeichenfolge** Der Auswahlindex wird an dem durch diesen Pfad angegebenen Speicherort gespeichert.

**xpathLinkEdit - Zeichenfolge** Link zur Bearbeitung (siehe Beispiel zu Gruppen).

**zoom - boolesch** Autorisiert die Bearbeitung von Links.

## Bemerkungen

Beispiele:

```xml
      <input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <sysFilter>
    <condition expr="@type=1"/>
  </sysFilter>
</input>

<input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <form label="Add operators">
  <input xpath="." type="linkListChoice" xpath-link="recipient" img="nms:group.bmp">
  <input xpath="@lastName"/>
  <input xpath="@firstName"/>
  </input>
  </form>
</input>

<input type="linklist" xpath="rcpGrpRel" zoom="true" label="Recipients" form="nms:recipient"
       xpath-link="rcpGroup"
       xpathLinkEdit="recipient">
  <input xpath="recipient/@lastName"/>
  <input xpath="recipient/@firstName"/>
  <input xpath="recipient/@email"/>
  <input xpath="recipient/@phone"/>
</input>
```
