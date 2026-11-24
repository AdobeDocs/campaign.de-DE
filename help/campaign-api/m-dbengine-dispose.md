---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 21%
---
# verfügen

Gibt die Verbindung von allen damit verbundenen Ressourcen frei.

```text
dispose ()
```

## Parameter

Keine.

## Rückgabewert

Keine.

## Bemerkungen

Eine mit der Methode [application.getConnection()](m-application-getconnection.md) erstellte Verbindung wird am Ende des Skripts automatisch freigegeben. Der Aufruf dieser Methode ist für Skripte nützlich, die eine lange Lebensdauer haben können.

## Funktionen

**Methode der Klasse:** [DBEngine](c-dbengine.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
