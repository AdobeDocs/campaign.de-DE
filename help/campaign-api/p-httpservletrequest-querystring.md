---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 13%
---
# queryString

Gibt den Teil der URL der Abfrage zurück, der den Parametern entspricht.

```text
queryString
```

## Bemerkungen

Beispiel: Die queryString der folgenden URL:

```javascript
      http://adobe.com/nms/test.jst?id=1234&param=dummy#aFragment
```

Gibt die folgende Zeichenfolge zurück:

```javascript
id=1234&param=dummy
```

## Funktionen

**Eigenschaft der Klasse:** [HttpServletRequest](c-httpservletrequest.md)

**Schreibgeschützt:**

Ja

**Verfügbar in:**

* JSSP
* WEBAPP
