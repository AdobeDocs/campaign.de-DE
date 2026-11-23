---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 6%
---
# Weiterleiten

Leitet die Abfrage zu einer anderen Seite um, ohne den Client zu verwenden.

```text
forward (location)
```

## Parameter

**location** Die Umleitungs-URL.

## Rückgabewert

Keine.

## Bemerkungen

Mit der Weiterleitung können Sie einen vorbereitenden Prozess durchführen, bevor Sie die Abfrage an eine andere Ressource übertragen, wodurch der Inhalt der Antwort generiert wird. Vor einem Weiterleitungsaufruf müssen keine Daten als Antwort an den Client zurückgegeben worden sein, da andernfalls ein Fehler ausgegeben wird.

## Funktionen

**Methode der Klasse:** [HttpServletRequest](c-httpservletrequest.md)

**Verfügbar in:**

* JSSP
* WEBAPP
