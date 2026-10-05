---
title: Abrufen von Profilen mit APIs
description: Erfahren Sie mehr über das Erstellen von Profilen mit APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
TQID: 'https://experienceleague.adobe.com/ufHL-Vr8NjFpJVES61uhuTl8Xh3DqUsKmwyDkvm7J-g'
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
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 100%
---
# Erstellen von Profilen mit APIs {#creating-profiles-api}

Profile lassen sich durch Ausführen einer **POST**-Anfrage für die Profilressource erstellen.

>[!CAUTION]
>
>Wenn Sie mit dem erstellten Profil eine <b>orgUnit</b> verknüpfen möchten, müssen Sie die Profilressource mit diesem Feld erweitern und nach der Veröffentlichung der Erweiterung eine POST-Anfrage für den Endpunkt <b>ProfilAndServicesExt</b> ausführen.
>
>Weiterführende Informationen zur Ressourcenerweiterung des Profils finden Sie in der <a href="https://helpx.adobe.com/de/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campaign-Dokumentation</a>.

<br/>

***Beispielanfrage***

Beispielhafte POST-Anfrage zum Erstellen eines Profils mit der E-Mail-Adresse &quot;max.mustermann@mail.com&quot;.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Es wird das neu erstellte Profil mit der E-Mail-Adresse &quot;max.mustermann@mail.com&quot; zurückgegeben.

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
