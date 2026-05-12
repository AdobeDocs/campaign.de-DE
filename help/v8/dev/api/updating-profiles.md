---
title: Aktualisieren von Profilen
description: Erfahren Sie, wie Sie mit APIs Profile aktualisieren können
role: Developer
level: Experienced
exl-id: fa3796ee-a00c-4d70-bf3d-e8d2099f1116
TQID: https://experienceleague.adobe.com/GJc7tW2XdnidUrVaLIpHl3pdHmE4dNLzhtVoUazhuPQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 96
ht-degree: 100%

---

# Aktualisieren von Profilen mit APIs{#updating-profiles-api}

Das Aktualisieren von Profilen erfolgt über eine **PATCH**-Anfrage.

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. Der erste Schritt besteht aus dem **Abrufen des Profils**.

1. Im zweiten Schritt führen wir eine **PATCH-Anfrage** für das Profil mit den ausgefüllten Informationen in der Payload aus.

1. Um zu überprüfen, ob die PATCH-Anfrage das Profil aktualisiert hat, können wir eine letzte GET-Anfrage ausführen.

<br/>

***Beispielanfrage***

Beispielhafte GET-Anfrage zum Abrufen eines Profils.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Antwort auf die Anfrage.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "Amy",
            "lastName":"Dakota",
            "birthDate": "1980-10-24",
            ...
        }
    ]
}
```

PATCH-Anfrage zum Aktualisieren des Attributs &quot;phone&quot;.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

Es werden der PKEY und die URL zum Abrufen des aktualisierten Profils zurückgegeben.

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```
