---
title: Erstellen eines Service mit APIs
description: Erfahren Sie, wie Sie mit APIs einen Service erstellen können
role: Developer
level: Experienced
exl-id: 91bbce9e-a618-4be2-840b-c7d021271f4e
TQID: 'https://experienceleague.adobe.com/H7TkqYaLkB-3SZeYW4vNif352UNd6EBCP5rFmtq2Hjs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 100%
---
# Erstellen eines Service mit APIs{#creating-a-service-api}

Dienste lassen sich mit einer **POST**-Anfrage für die Dienstressource erstellen.

Wenn Sie den Dienst mit bestimmten Attributen erstellen möchten, fügen Sie sie der Payload hinzu. Andernfalls wird der neue Dienst mit Standardattributen eingerichtet.

<br/>

***Beispielanfrage***

Beispielhafte POST-Anfrage zum Erstellen eines Diensts mit bestimmten Attributen.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label": "My newsletter",
-d "messageType": "email",
-d "name": "email_newsletter",
-d "start": "2019-10-06"
-d }
```

Es wird der neu erstellte Dienst mit den aktualisierten Attributen zurückgegeben.

```
{
    "PKey": "<PKEY>",
    "builtIn": false,
    "created": "2019-09-26 12:00:37.005Z",
    "href": "https://mc.adobe.io/<ORGANIZATION>/profileAndServices/service/@NLscZuVHxdVu9rPftvrMWFfR1zRIxQGswSOmGLrK09JTF_iWhB0JCUHEndA_vvy__k9mzOYa5NVkcWDcrK8qGh0wygahX9kRcD44kiWWSEceShn3",
    "label": "My newsletter",
    ...
}
```
