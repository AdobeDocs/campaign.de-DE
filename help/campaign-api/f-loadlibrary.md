---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 16%
---
# loadLibrary

Lädt eine JavaScript-Bibliothek.

```text
loadLibrary (filename [, boolean ])
```

## Parameter

**filename** Der Name der zu ladenden JavaScript-Bibliothek.

**boolean** Aktiviert oder deaktiviert den Lade-Cache. Standardmäßig ist „true“.

> Hinweis: Wenn der Parameter auf „false“ gesetzt ist, muss die Funktion logon() verwendet werden, bevor der loadLibrary-Aufruf als Operator authentifiziert werden kann.

## Rückgabewert

Keine.

## Bemerkungen

Der Cache ist standardmäßig aktiviert. Wenn der Cache deaktiviert ist, wird die Datenbank für jeden Aufruf abgefragt. Mit dieser Abfrage können Sie die neueste Version der Bibliothek laden. Beispiel: loadLibrary(&#39;xtk:shared/nl.js&#39;)

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
