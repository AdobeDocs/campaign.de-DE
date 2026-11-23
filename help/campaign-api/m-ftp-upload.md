---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 31%
---
# Upload

Herunterladen einer Datei von einer lokalen Datei auf einen FTP-Server.

```text
upload (URL)
```

## Parameter

**URL** Server-URL.

## Rückgabewert

Keine.

## Bemerkungen

Die URL muss mit &quot;ftp:&#39;&quot; beginnen. Beispiel:

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.upload("ftp://ftp.funet.fi/pub/standards/RFC")
```

## Funktionen

**Methode der Klasse:** [FTP](c-ftp.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
