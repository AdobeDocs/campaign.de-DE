---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 14%
---
# Download

Lädt eine Datei vom Server in eine lokale Datei oder in den Speicher herunter.

```text
download (URL [, append ])
```

## Parameter

**URL** URL der herunterzuladenden Datei.

**append** Wenn die heruntergeladene Datei bereits auf der lokalen Festplatte vorhanden ist, wird sie standardmäßig durch die neue empfangene Datei überschrieben. Wenn der boolesche Wert aktiviert ist, schreibt Adobe Campaign den heruntergeladenen Inhalt zusammen mit dem vorhandenen Inhalt in die Datei mit demselben Namen.

## Rückgabewert

Keine.

## Bemerkungen

Um die Datei in einer lokalen Datei wiederherzustellen, verwenden Sie zunächst die setFile-Methode. Beispiel:

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.download("ftp://ftp.funet.fi/pub/standards/RFC/rfc2068.txt")
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
