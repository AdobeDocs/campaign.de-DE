---
title: Durchführen von Abonnements
description: Erfahren Sie, wie Sie mit APIs Anmeldungen vornehmen können
role: Data Engineer
level: Experienced
exl-id: 64f321a3-436a-4b7c-99d8-0c006203012e
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 100%

---

# Durchführen von Abonnements mit APIs{#performing-subscriptions}

## Methode 1: Anmelden eines Profils für einen Dienst

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

Führen Sie eine POST-Anfrage für die Anmeldungs-URL mit dem gewünschten Primärschlüssel des Diensts in der Payload aus.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"service":{"PKey":"<PKEY>"}}'
```

Es wird das aktualisierte Profil mit dem abgeschlossenen Dienstknoten zurückgegeben.

```
{
  ...
  "service": {
    "PKey": "<PKEY>",
    "title": "Sport Newsletter (SVC1)"
  },
  "serviceName": "",
  "subscriber": ...,
  ...
}
```

## Methode 2: Hinzufügen eines Profils zu den Abonnenten eines Diensts

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

Führen Sie eine POST-Anfrage für die Anmeldungs-URL mit dem gewünschten Primärschlüssel des Profils in der Payload aus.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign//profileAndServices/service/<PKEY>/subscriptions/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"subscriber":{"PKey":"<PKEY>"}}'
```

Es wird der aktualisierte Dienst mit dem abgeschlossenen Abonnentenknoten zurückgegeben.

```
{
  ...
  "service": ...,
  "serviceName": "",
  "subscriber": {
    "PKey": "<PKEY>",
    ...
  },
}
```
