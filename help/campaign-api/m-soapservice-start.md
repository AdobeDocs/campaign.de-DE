---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 15%
---
# Start

Startet eine Abfrage im asynchronen Modus.

```text
start (context, name, ...)
```

## Parameter

**context** Jeder Benutzerparameter, der an die Funktion [complete](p-soapservice-complete.md) weitergeleitet wird.

**name** Name der aufzurufenden Methode.

**…** Funktionsparameter.

## Rückgabewert

Die erstellte Abfrage. Dieses Objekt hat keine Eigenschaften oder Funktionen. Es ist nützlich für die [wait](m-soapservice-wait.md)-Funktion, mit der Sie bis zum Ende eines Vorgangs warten können.

## Bemerkungen

Die Service-Verbindung muss asynchron sein. Wenn die Verbindung blockiert, wird eine Ausnahme ausgelöst. Abfragen können nicht ausgeführt werden, wenn derzeit eine andere Abfrage für die Verbindung ausgeführt wird. In diesem Fall wird eine Ausnahme ausgelöst.

## Funktionen

**Methode der Klasse:** [SoapService](c-soapservice.md)

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
