---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 2%
---
# VPaned

Ordnet mehrere Container horizontal an.

## Eigenschaften

**backColor - Zeichenfolge** Hintergrundfarbe (btnshadow, weiß).

**name - Zeichenfolge** Container-ID.

**padding-left - integer** Leerzeichen in Pixel links vom Container.

**padding-right - integer** Leerzeichen in Pixel rechts neben dem Container.

**padding-top - integer** Leerzeichen in Pixel über dem Container.

**padding-bottom - integer** Leerzeichen in Pixel unter dem Container

**padding - integer** Leerzeichen in Pixel um den Container.

**readOnly - Boolesch** Erzwingt die schreibgeschützte Steuerung und alle untergeordneten Elemente.

## Bemerkungen

Jedes Unterelement muss ein Container sein. Jeder Unter-Container kann den Prozentsatz der Gesamtbreite angeben, den sie mithilfe der width-percent-Eigenschaft verwenden möchten. Beispiel:

```xml
<container type="vpaned">
  <container label="Group 1" width-percent="25"/>
    <input .../>
  </container>
  <container label="Group 2" width-percent="75"/>
    <input .../>
  </container>
</container>
```
