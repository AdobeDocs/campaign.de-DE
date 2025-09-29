---
product: campaign
title: Technote - Asymmetrische Ver- und Entschlüsselung in Adobe Campaign
description: Technische Anmerkung - Asymmetrische Verschlüsselung und Entschlüsselung in Adobe Campaign
hide: true
hidefromtoc: true
source-git-commit: d80d81bf8c25c467c909c9ccac7c31e6963409f0
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 0%

---

# Technote: Asymmetrische Ver- und Entschlüsselung in Adobe Campaign {#asymetric-encryption}

Die Kryptographie mit öffentlichem Schlüssel oder asymmetrische Kryptographie ist das Feld kryptographischer Systeme, die Paare verwandter Schlüssel verwenden. Jedes Schlüsselpaar besteht aus einem &quot;**Schlüssel“** einem entsprechenden **privaten Schlüssel**.

* Der **öffentliche Schlüssel** wird offen freigegeben und zum Verschlüsseln von Daten verwendet.

* Der **private Schlüssel** wird geheim gehalten und zum Entschlüsseln von Daten verwendet.

Dieser Ansatz stellt sicher, dass eine Person, die den öffentlichen Schlüssel hat, die Nachricht nicht ohne den privaten Schlüssel entschlüsseln kann. Es bietet wichtige Sicherheitsfunktionen wie Vertraulichkeit, Authentifizierung und Integrität.

Ab Adobe Campaign v8.8.3 werden zwei neue JavaScript-Funktionen für die Ver- und Entschlüsselung hinzugefügt:

* Verschlüsselung mit öffentlichem Schlüssel: `rsaPublicEncrypt(data, base64EncodedPublicKey, useOAEPpadding)`

* Entschlüsselung mit privatem Schlüssel: `rsaPrivateDecrypt(encryptedData, base64EncodedPrivateKey, useOAEPpadding)`


Beispiel:

```Java
// Encryption with PKCS#1 v1.5 padding (default)
var encrypted = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t..." // Base64 encoded public key
);
 
// Encryption with OAEP padding
var encryptedOAEP = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t...", // Base64 encoded public key
    true
);
 
// Decryption
var decrypted = rsaPrivateDecrypt(
    encrypted,
    "LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVkt..." // Base64 encoded private key
);
```

