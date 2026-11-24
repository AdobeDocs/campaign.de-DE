---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 2%
---
# HPaned

Ordnet mehrere Behälter vertikal an.

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

Jedes Unterelement muss ein Container sein. Jeder der zugehörigen Unter-Container kann den Prozentsatz der Gesamthöhe angeben, den sie dank der height-percent-Eigenschaft verwenden möchten. Beispiel:

```xml
<container type="hpaned">
  <container label="Group 1" height-percent="25"/>
    <input .../>
  </container>
  <container label="Group 2" height-percent="75"/>
    <input .../>
  </container>
</container>
```
