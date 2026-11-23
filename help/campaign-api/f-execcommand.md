---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 7%
---
# execCommand

> Warnung: Diese Funktion ist für eine On-Premise-Umgebung verfügbar.

Führt einen Befehl aus und erfasst den Fehler-Code und die Standardausgabe.

```text
execCommand (command [, bNoThrow ])
```

## Parameter

**command** Der Befehl, der mit seinen Parametern ausgeführt werden soll.

**bNoThrow** true, um die Ausgabe und den Fehlercode auch dann abzurufen, wenn der Befehl nicht null zurückgibt (standardmäßig „false„).

## Rückgabewert

Gibt eine Tabelle zurück, deren erstes Element dem Rückgabecode des Befehls entspricht (wenn der Rückgabecode von null abweicht, liegt eine Anomalie vor) und das zweite Element eine Zeichenfolge ist, die die erzeugte Standardausgabe enthält.

## Bemerkungen

Ohne die Option nothrow wird eine Ausnahme ausgelöst, wenn der Befehl nicht ausgeführt werden kann oder wenn der Befehl mit einem Fehler ausgeführt wird. Wenn bNoThrow gleich „true“ ist, wird nur dann eine Ausnahme ausgelöst, wenn der Befehl nicht ausgeführt werden kann. Der Operator benötigt „createProcess“-Rechte, um diese Funktion verwenden zu können. Andernfalls wird eine Ausnahme ausgelöst. Abhängig von Ihrer Installation können auf der Blockierungsliste einige Befehle ausgeführt werden. Beispiel: ln, dd, openssl, curl, wget, python, python3, perl, ruby, sh, bash, dash, zsh, base64, nlserver, node, phantomjs, java, awk, nc, telnet, ssh, scp, ftp.

## Beispiel

```text
var result = execCommand('gpg-exec.sh gpg --no-tty --yes -r CampaignOperations@adobe.com --encrypt "file_to_encrypt"', true);
```

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
