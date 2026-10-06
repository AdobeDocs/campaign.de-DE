---
product: campaign
title: Technote - Asymmetrische Ver- und Entschlüsselung in Adobe Campaign
description: Technische Anmerkung - Asymmetrische Verschlüsselung und Entschlüsselung in Adobe Campaign
hide: true
exl-id: 6ee8b05b-2a46-4adf-a036-82fdd4809d0d
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 10%
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

**Zusätzliche Ressourcen**

* [Erste Schritte mit  [!DNL Campaign] -APIs](https://experienceleague.adobe.com/de/docs/campaign/campaign-v8/developer/api){target="_blank"}
* [Campaign - JSAPI-Dokumentation](https://experienceleague.adobe.com/de/tools/campaign-api){target="_blank"}
