---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 4%
---
# Notebook

Liste der Registerkarten zur Anzeige mehrerer Seiten.

![Notebook-Steuerung](assets/notebook.3b531a46.png)

## Eigenschaften

**backColor - Zeichenfolge** Hintergrundfarbe (btnshadow, weiß).

**name - Zeichenfolge** Container-ID.

**padding-left - integer** Leerzeichen in Pixel links vom Container.

**padding-right - integer** Leerzeichen in Pixel rechts neben dem Container.

**padding-top - integer** Leerzeichen in Pixel über dem Container.

**padding-bottom - integer** Leerzeichen in Pixel unter dem Container

**padding - integer** Leerzeichen in Pixel um den Container.

**readOnly - Boolesch** Erzwingt die schreibgeschützte Steuerung und alle untergeordneten Elemente.

**style - string** flat \| down \| up (Standard).

## Bemerkungen

Jedes Unterelement stellt eine Seite dar. Beispiele:

```xml
      <container colspan="2" style="down" type="notebook">
   <container label="Products">
     ...
   </container>

   <container colcount="3" xpath="link">
     ...
   </container>

   <container xpath="linkCollection">
     ...
   </container>
 </container>
```
