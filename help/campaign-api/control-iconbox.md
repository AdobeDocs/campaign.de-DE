---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 4%
---
# Iconbox

Liste der Symbole, die die Auswahl mehrerer Seiten ermöglichen.

![Iconbox-Steuerelement](assets/iconbox.05daa4bf.png)

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

Jedes Container-Unterelement stellt eine Seite dar. Beispiel:

```xml
<container name="iconbox" type="iconbox">
   <container colcount="3" label="Header">
     ...
   </container>
   <container img="ncm:ctprop.bmp" label="Intro">
     ...
   </container>
   <container img="ncm:subsection.bmp" label="Event">
     ...
   </container>
   <container img="ncm:book.bmp" label="Selection">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Services">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Mail footer ">
     ...
   </container>
 </container>
```
