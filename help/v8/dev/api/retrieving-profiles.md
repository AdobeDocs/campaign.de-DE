---
title: Abrufen von Profilen
description: Erfahren Sie, wie Sie mit APIs Profile abrufen können
role: Developer
level: Experienced
exl-id: 19679804-f728-49fa-b26e-8f31b67c29bf
TQID: 'https://experienceleague.adobe.com/pL6dAoJZ-Qb-aP2BWZKTxsYMTpQEM9EZoU3REWE0OoI'
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
source-wordcount: '235'
ht-degree: 100%
---
# Abrufen von Profilen mit APIs {#retrieving-profiles}

Profile lassen sich mit einer **GET**-Anfrage abrufen.

Anschließend können Sie die Suche mithilfe von Filtern, Reihenfolge und Paginierung verfeinern. Weiterführende Informationen dazu finden Sie im Abschnitt [Zusätzliche Vorgänge](sorting.md).

Darüber hinaus können Sie mit Campaign Standard-APIs nach Profilen suchen, die auf einem der folgenden Felder basieren: E-Mail, Vorname, Nachname oder ein benutzerdefiniertes Feld. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](#searching-field).

<br/>

***Beispielanfragen***

* Beispielhafte GET-Anfrage zum Abrufen aller Profile.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
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
              "firstName": "John",
              "lastName":"Doe",
              "birthDate": "1980-10-24",
              ...
          },
          ...
  }
  ```

* Beispielhafte GET-Anfrage zum Abrufen der ersten 10 E-Mail-Werte.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Antwort auf die Anfrage. Der Knoten &quot;Nächste&quot; gibt die URL zurück, mit der Sie auf die nächsten 10 E-Mail-Werte zugreifen können.

  ```
  {
  "content": [
      "amy.dakota@mail.com",
      "kristen.smith@mail.com",
      "omalley@mail.com",
      "xander.harrys@mail.com",
      "jane.summer@mail.com",
      "gloria.boston@mail.com",
      "edward.snow@mail.com",
      "dorian.simons@mail.com",
      "peter.paolini@mail.com",
      "mingam+test08@adobe.com"
  ],
  "next": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
      lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
  }
  }
  ```

## Anhand eines Felds nach Profilen suchen {#searching-field}

Mit dem Parameter **[!UICONTROL filterType]** können Sie Profile anhand eines dieser Felder abrufen: E-Mail, Vorname, Nachname oder ein beliebiges benutzerdefiniertes Feld, das den erweiterten Filtern beim Erweitern der Profilressource hinzugefügt wurde.

>[!NOTE]
>
>Bei der Suche wird zwischen Groß- und Kleinschreibung unterschieden, und es wird nur nach Präfixen gesucht. Sie können beispielsweise nicht anhand der letzten Buchstaben des Nachnamens nach einem Profil suchen.

***Beispielanfragen***

* Beispielanfrage zum Filtern von Profilen anhand des Vornamens.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John&filterType=firstName \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* Beispielanfrage zum Filtern von Profilen anhand des Nachnamens.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Miller&filterType=lastName \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* Beispielanfrage zum Filtern von Profilen anhand der E-Mail.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John%40gmail.com&filterType=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* Beispielanfrage zum Filtern von Profilen anhand des benutzerdefinierten Felds &quot;Hobby&quot;.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byText?cusHobby=Dancing&filterType=Hobby \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```
