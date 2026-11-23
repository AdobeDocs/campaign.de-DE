---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 3%
---
# Inhalt auswerten

Wertet den Inhalt eines mit einer Bestellung verknüpften Versands aus Diese Auswertung wird bei der Bestellung unter Verwendung der Benutzerrechte durchgeführt, bevor die lokale Kampagne erstellt wird.

```text
XML result = EvaluateContent ( XML order, Number deliveryId, String contentType, Number seedMemberId )
```

## Parameter

**order** Element mit den Bestellinformationen.

**deliveryId** Kennung des auszuwertenden Versands.

**contentType** Typ des zurückzugebenden Inhalts (HTML oder Text für eine E-Mail; leere Zeichenfolge für andere Kanäle).

**seedMemberId** Kennung der für die Personalisierung des Inhalts verwendeten Testadresse.

## Rückgabewert(e)

**result** Evaluierter Inhalt.

## Funktionen

**Schema:** [nms:localOrder](s-nms-localorder.md)

**static:**

Ja
