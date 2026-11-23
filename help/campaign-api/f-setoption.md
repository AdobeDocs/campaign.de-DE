---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 12%
---
# setOption

Ändert den Wert einer Option in der Optionstabelle.

```text
setOption (name, value, description )
```

## Parameter

**name** Name der Option.

**value** Wert der Option.

**description** Wert der Beschreibung (optional).

## Rückgabewert

Keine.

## Bemerkungen

Die verschiedenen Datentypen sind:

* Text,
* Ganzzahl,
* Gleitkommazahl,
* Datum + Uhrzeit,
* longText

Beachten Sie, dass der Typ „longText“ und „integer“ nicht über die API erstellt werden können.

Für diese beiden Typen müssen Sie zunächst die Option in der Konsole erstellen und können dann die Werte über die setOption-API verwalten.

**Beispiel:**

```javascript
               //create option of type Date+Time'
               var ourDate = getCurrentDate();
               setOption("testOptionDateTime",ourDate,"option of type Date+Time");
                              
               //create option of type Floating point'
               setOption("testOptionFloat",1,"option of type Floating point");
               
               //create option of type Text'
               setOption("testOptionText","I am a text","option of type Text");               
           
```

Wenn Sie die Beschreibung löschen möchten, müssen Sie die API mit einer leeren Beschreibung aufrufen (setOption(name,value,„)).

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
