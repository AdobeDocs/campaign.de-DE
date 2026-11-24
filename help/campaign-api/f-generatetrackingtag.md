---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%
---
# generateTrackingTag

Erzeugt automatisch ein JavaScript-Tag für das Webtracking.

```text
generateTrackingTag (request [, tagid ] [, folder ])
```

## Parameter

**request** Das HttpServletRequest-Objekt

**tagid** Eine Zeichenfolge, die den Namen der personalisierten Tag-ID darstellt. Wenn es leer ist, generiert die Funktion das -Tag basierend auf dem Pfadnamen.

**Ordner** Eine Zeichenfolge, die den internen Namen eines Ordners darstellt. Wenn es leer ist, wird das Tag im Standardverzeichnis erstellt, d. h. „Webtracking-Tags“.

## Rückgabewert

Eine Zeichenfolge, die den einzuschließenden JavaScript-Code enthält.

## Bemerkungen

Das generierte Tag basiert auf dem Namen der Web-App, der HTML-Seite, dem Controller oder allgemein auf dem Pfadnamen, wenn die Tag-ID nicht eingegeben wird. Der letzte Parameter gibt den Tag-Zielordner an. Um die Funktion aufzurufen, übergeben Sie das Anfrageobjekt als Argument. Beachten Sie die Verwendung von &lt;%==, da die Funktion HTML-Code generiert. Beispiel:

```xml
              <%== generateTrackingTag(request, request.getParameter('art'), request.getParameter('cat')) %>
```

## Funktionen

**Verfügbar in:**

* JSSP
* WEBAPP
