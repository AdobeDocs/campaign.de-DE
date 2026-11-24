---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 12%
---
# Schema

Gibt den Namen des verwendeten Protokolls aus (HTTP, HTTPS usw.) , um auf diese Seite zuzugreifen.

```text
scheme
```

## Bemerkungen

Beispiel: Das Schema der folgenden URL:

```javascript
      http://adobe.com/de:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

Gibt die folgende Zeichenfolge zurück:

```javascript
http
```

## Funktionen

**Eigenschaft der Klasse:** [HttpServletRequest](c-httpservletrequest.md)

**Schreibgeschützt:**

Ja

**Verfügbar in:**

* JSSP
* WEBAPP
