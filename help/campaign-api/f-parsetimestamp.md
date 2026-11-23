---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 17%
---
# parseTimeStamp

Konvertiert eine Zeichenfolge, die ein Datum enthält, das auf der Grundlage einer vereinfachten Version des ISO 8601-Standards formuliert wurde, in ein Objekt vom Typ Datum .

```text
parseTimeStamp (aString)
```

## Parameter

**aString** Das Datum als Zeichenfolge im ISO 8601-Format.

## Rückgabewert

Ein Objekt vom Typ Datum , das dem als Parameter festgelegten Datum entspricht.

## Bemerkungen

Die Syntax sieht folgendermaßen aus:

```javascript
              date
              time[time-zone]
            
```

oder

```javascript
              dateTtime[time-zone]
            
```

Das Datum muss im folgenden Format angegeben werden:

```javascript
YYYY-MM-DD
```

Aus Kompatibilitätsgründen wird auch das folgende Format akzeptiert:

```javascript
YYYY/MM/DD
```

Die Uhrzeit muss das folgende Format haben:

```javascript
hh:mm:ss
hh:mm:ss.nnn
```

Die Zeitzone muss, falls angegeben, das folgende Format aufweisen:

```javascript
Z
+hh:mm
-hh:mm
+hh
-hh
```

Wenn die Zeitzone nicht angegeben ist, wird das Datum (je nach Kontext) in die aktuelle Zeitzone konvertiert. Beispiele:

```javascript
2005-03-02 00:00:00
2005-03-02
2005-03-02T14:32:26
2005-03-02T14:32:26.0000
2005-03-02T14:32:26.0000000+01:00
2005-03-02T14:32:26+01:00
2005-03-02T14:32:26Z
2005-03-02T14:32:26.0005Z
2005/03/02 14:32:25
```

Wenn das Datumsformat nicht gültig ist, wird eine Ausnahme ausgelöst.

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Versandnachricht
* Typologieregel
* Import
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
