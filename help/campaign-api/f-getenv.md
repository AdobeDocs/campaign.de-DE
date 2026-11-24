---
source-git-commit: 77f8182ea5b1fda08206021a164b2e0ff827890a
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 22%
---
# getEnv

>[!WARNING]
>
>Diese Funktion ist für eine On-Premise-Umgebung verfügbar.

>[!NOTE]
>
>Sie können diese Funktion deaktivieren, indem Sie die Option **XtkSecurity\_Disable\_GetSetEnv** an **true** übergeben.

Gibt den Wert einer Umgebungsvariablen zurück.

```text
getEnv (name [, default ])
```

## Parameter

**name** Name der Variablen.

**default** Standardwert, der verwendet wird, wenn die Umgebungsvariable nicht gefunden wird.

## Rückgabewert

Der Wert der Variablen.

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
