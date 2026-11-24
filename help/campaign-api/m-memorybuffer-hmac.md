---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 15%
---
# HMAC

Berechnet den MD5-, SHA-1- oder SHA-256-Hash des Puffers.

```text
hmac (key [, algo ])
```

## Parameter

**key** Key, in Form eines Puffers.

**algo** zu verwendender Hash-Typ. Mögliche Werte sind „MD5“, „SHA1“ oder „SHA256“. Sie unterscheiden nicht zwischen Groß- und Kleinschreibung, die Werte können daher in Klein- oder Großbuchstaben eingegeben werden. Standardmäßig ist der Wert „SHA1“ ausgewählt, wenn der Parameter nicht angegeben ist.

## Rückgabewert

Der Hash MD5, SHA-1 oder SHA-256 (je nach ausgewähltem Hash-Typ) des Puffers.

## Funktionen

**Methode der Klasse:** [MemoryBuffer](c-memorybuffer.md)

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
