---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%
---
# HttpServletRequest (Klasse)

Stellt die Abfrage eines Clients dar, der an ein Servlet weitergeleitet wird.

Es gibt nur eine Instanz dieser Adresse, auf die über die `request` zugegriffen werden kann. Variable.

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [getHeader](m-httpservletrequest-getheader.md) | Gibt ein im Abfrage-Header definiertes Attribut zurück. |
| [getParameter](m-httpservletrequest-getparameter.md) | Gibt den Wert eines Abfrageparameters zurück. |
| [getRemoteAddr](m-httpservletrequest-getremoteaddr.md) | Gibt die IP-Adresse des Clients oder den letzten Proxy zurück, der eine Anfrage gesendet hat. |
| [getUTF8Parameter](m-httpservletrequest-getutf8parameter.md) | Gibt den Wert (in UTF-8 codiert) eines Parameters der Abfrage zurück. |
| [getBodyAsString](m-httpservletrequest-getbodyasstring.md) | Gibt den Hauptteil der Abfrage in Form einer Zeichenfolge mit Abfragecodierung zurück. |
| [vorwärts](m-httpservletrequest-forward.md) | Leitet die Abfrage zu einer anderen Seite um, ohne den Client zu verwenden. |

## Eigenschaften

| Eigenschaft | Beschreibung |
| --- | --- |
| [Parameter](p-httpservletrequest-parameters.md) | Gibt die Abfrageparameter zurück. |
| [Cookies](p-httpservletrequest-cookies.md) | Gibt die Cookies der Abfrage zurück. |
| [requestURI](p-httpservletrequest-requesturi.md) | Gibt die URL der Abfrage zurück. |
| [queryString](p-httpservletrequest-querystring.md) | Gibt den Teil der URL der Abfrage zurück, der den Parametern entspricht. |
| [schema](p-httpservletrequest-scheme.md) | Gibt den Namen des verwendeten Protokolls aus (HTTP, HTTPS usw.) , um auf diese Seite zuzugreifen. |
| [serverName](p-httpservletrequest-servername.md) | Gibt den Namen des Abfrage-Servers zurück. |
| [serverPort](p-httpservletrequest-serverport.md) | Gibt die Port-Nummer für die Verbindung zum Server aus |
| [serverURL](p-httpservletrequest-serverurl.md) | Gibt die URL für den Zugriff auf den Server aus. |
| [servletPath](p-httpservletrequest-servletpath.md) | Gibt den Abschnitt der URL der Abfrage zurück, der dem Servlet entspricht. |
| [contextPath](p-httpservletrequest-contextpath.md) | Gibt den dem Kontext entsprechenden Abschnitt der URL der Abfrage zurück. |
| [pathInfo](p-httpservletrequest-pathinfo.md) | Gibt die zusätzlichen Informationen zur URL der Abfrage zurück. |
| [Methode](p-httpservletrequest-method.md) | Gibt eine Zeichenfolge zurück, die die HTTP-Methode zum Aufrufen dieser Abfrage (GET, HEAD, POST usw.) enthält. |

## Funktionen

**Verfügbar in:**

* JSSP
* WEBAPP
