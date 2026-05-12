---
title: Benutzerdefinierte Ressourcen
description: Erfahren Sie mehr über die Verwaltung benutzerdefinierter Ressourcen mit APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: d7b2231d-46ff-4966-9ea7-27a775e5236b
TQID: https://experienceleague.adobe.com/T-CLyTlNyyuckhraPX-rAU7TOrMfMbcZdrDcneiflg0
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 177
ht-degree: 100%

---

# Benutzerdefinierte Ressourcen {#custom-resources}

Adobe Campaign verfügt über ein vordefiniertes Datenmodell, bei dem Daten über verschiedene Ressourcen definiert werden. Sie können das bereitgestellte Datenmodell anreichern, indem Sie die Ressourcen erweitern, um eigene benutzerdefinierte Felder oder benutzerdefinierte Tabellen hinzuzufügen (z. B. Einkaufs- oder Produkttabellen).

Benutzerdefinierte Ressourcen können über APIs mit dem Endpunkt **/profileAndServicesExt** und dem Namen der benutzerdefinierten Ressource aufgerufen werden.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Verwenden Sie bei Ressourcen, die nicht vordefiniert sind, immer das Präfix <b>&quot;cus&quot;</b> vor dem Namen der Ressource.

Sie können beliebige Aktionen mit benutzerdefinierten Ressourcen ausführen, solange diese mit der Profiltabelle verknüpft sind. Betrachten wir zum Beispiel die folgende Tabellenstruktur:

![Alternativtext](assets/cusresources.png)

In diesem Fall sind alle Ressourcen aus den Tabellen **Transaktion**, **Transaktionsdetails** und **Produkt** verfügbar, solange sie mit der Tabelle **Profil** verknüpft sind.

<br/>

***Beispielanfrage***

Beispielhafte GET-Anfrage zum Aufrufen der erweiterten Ressource profileAndServicesExt.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

Es wird eine Liste aller verknüpften benutzerdefinierten Ressourcen zurückgegeben. Anschließend können Sie die Ressourcen-URLs verwenden, um beliebige in dieser Dokumentation beschriebenen API-Aufgaben zu erledigen.

```
{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}
```
