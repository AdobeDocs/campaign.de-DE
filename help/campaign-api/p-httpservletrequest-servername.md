---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 15%
---
# serverName

Gibt den Namen des Abfrage-Servers zurück.

```text
serverName
```

## Bemerkungen

Beispiel: ServerName der folgenden URL:

```javascript
      http://adobe.com:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

Gibt die folgende Zeichenfolge zurück:

```javascript
adobe.com
```

## Funktionen

**Eigenschaft der Klasse:** [HttpServletRequest](c-httpservletrequest.md)

**Schreibgeschützt:**

Ja

**Verfügbar in:**

* JSSP
* WEBAPP
