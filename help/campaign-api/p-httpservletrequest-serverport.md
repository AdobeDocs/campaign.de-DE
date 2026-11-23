---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 11%
---
# serverPort

Gibt die Port-Nummer für die Verbindung zum Server aus

```text
serverPort
```

## Bemerkungen

Beispiel: Der serverPort der folgenden URL:

```javascript
http://adobe.com:8080/nms/test.jst
```

Gibt die folgende Zeichenfolge zurück:

```javascript
8080
```

ServerPort der folgenden URL:

```javascript
http://adobe.com/nms/test.jst
```

Gibt die folgende Zeichenfolge zurück:

```javascript
80
```

## Funktionen

**Eigenschaft der Klasse:** [HttpServletRequest](c-httpservletrequest.md)

**Schreibgeschützt:**

Ja

**Verfügbar in:**

* JSSP
* WEBAPP
