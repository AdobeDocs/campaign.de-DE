---
title: Abrufen von Abonnements
description: Erfahren Sie, wie Sie mit APIs Abonnements abrufen können
role: Developer
level: Experienced
exl-id: 6d935074-3196-45c5-97cd-ccb7c80bbba8
TQID: https://experienceleague.adobe.com/PxFql-omcIMizY-oMBl75gfo2UmmLTanrhQqw5te--A
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 200
ht-degree: 100%

---

# Abrufen von Abonnements mit APIs {#retrieving-subscriptions-api}

## Abrufen der Profile, die einen Dienst abonniert haben

Dies ist ein zweistufiges Verfahren.

1. Rufen Sie die Anmeldungs-URL für den gewünschten Dienst ab.
1. Führen Sie eine GET-Anfrage für die Anmeldungs-URL aus. Es wird eine Liste der Anmeldungen für den Dienst mit jedem zugehörigen Profil zurückgegeben.

>[!CAUTION]
>
>Die REST-API gibt die Eigenschaft &quot;href&quot; zurück; diese enthält die zu verwendende URL. <b>Nutzen Sie stets die in der Antwort enthaltene URL, um die nachfolgende API-Anfrage zu erstellen</b>.

<br/>

***Beispielanfrage***

Führen Sie eine GET-Anfrage aus, um den Dienst abzurufen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Es wird die Anmeldungs-URL für den Dienst zurückgegeben.

```
  {
    ...
    "messageType": "email",
    "name": "SVC1",
    "subscriptions": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
    },
    ...
  },
```

Führen Sie eine GET-Anfrage für die Anmeldungs-URL aus.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Eine Liste der Anmeldungen für den Dienst mit jedem zugehörigen Profil wird angezeigt.

```
  {
    ...
    "service": ...,
    "serviceName": "SVC3",
    "subscriber": {
        "PKey": "<PKEY>",
        "email": "",
        "firstName": "John",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
        "lastName": "Doe",
    },
  }
```

## Abrufen der Dienste, die ein Profil abonniert hat

Dies ist ein zweistufiges Verfahren.

1. Rufen Sie die Anmeldungs-URL für ein bestimmtes Profil ab.
1. Führen Sie eine GET-Anfrage für die URL aus. Es wird eine Liste der Anmeldungen für das Profil mit jedem zugehörigen Dienst zurückgegeben.

<br/>

***Beispielanfrage***

Führen Sie eine GET-Anfrage aus, um das Profil abzurufen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Gibt die Anmeldungs-URL für das Profil zurück.

```
  {
    ...
    "postalAddress":...,
    "preferredLanguage": "none",
    "subscriptions": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions/"
    },
    ...
  }
```

Führen Sie eine GET-Anfrage für die Anmeldungs-URL aus.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Es wird eine Liste der Dienste zurückgegeben, die das Profil abonniert hat.

```
  {
    ...
    "PKey": "<PKEY>",
    "created": "2017-03-03 10:54:00.363Z",
    "service": {
      "PKey": "<PKEY>",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
      "label": "Sport Newsletter",
      "name": "SVC1",
      "title": "Sport Newsletter (SVC1)"
    },
    ...
  }
```
