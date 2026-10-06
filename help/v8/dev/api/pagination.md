---
title: Paginierung
description: Erfahren Sie, wie Sie Paginierungsvorgänge durchführen können.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: d6ebce3c-1e84-4b3b-a68d-90df4680af64
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 100%
---
# Paginierung

Standardmäßig werden 25 Ressourcen in eine Liste geladen.

Mit dem Parameter **_lineCount** können Sie die Zahl der in der Antwort aufgelisteten Ressourcen einschränken.  Anschließend können Sie mit dem Knoten **Nächste** die nächsten Ergebnisse anzeigen.

>[!NOTE]
>
>Verwenden Sie stets den URL-Wert, der im Knoten **Nächste** zurückgegeben wird, um eine Paginierungsanfrage auszuführen.
>
>Die Anfrage **_lineStart** wird berechnet und muss stets in der URL, die im Knoten **Nächste** zurückgegeben wird, verwendet werden.

<br/>

***Beispielanfrage***

Beispielhafte GET-Anfrage zum Anzeigen eines Datensatzes der Profilressource

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Antwort auf die Anfrage, wobei der Knoten **Nächste** die Paginierung ausführt.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

Standardmäßig ist der Knoten **Nächste** nicht verfügbar, wenn Tabellen mit einer großen Datenmenge verarbeitet werden. Um die Paginierung auszuführen, müssen Sie den Parameter **_forcePagination=true** zu Ihrer Aufruf-URL hinzufügen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>Die Anzahl der Datensätze, ab der eine Tabelle als groß angesehen wird, wird in der Campaign Standard-Option **XtkBigTableThreshold** definiert. Der Standardwert ist 100.000 Datensätze.
