---
title: Zusätzliche Vorgänge
description: Weitere Informationen zum Ausführen zusätzlicher Vorgänge
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: 7db25b8d-a6f1-4151-bf37-c47e9991ae48
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 98%

---

# Zusätzliche Vorgänge {#additional-operations}

## Sortieren {#sorting}

Die Sortierung ist standardmäßig in aufsteigender Reihenfolge verfügbar. Um in absteigender Reihenfolge zu sortieren, hängen Sie **%20desc** an den Wert des Parameters **_order** an.

Um zu erfahren, ob sich ein Feld sortieren lässt, prüfen Sie den Parameter &quot;sortable&quot; in den Metadaten der Ressource. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](metadata-mechanism.md).

<br/>

***Beispielanfragen***

* Beispielhafte GET-Anfrage zum Abrufen von E-Mails in der Datenbank in alphabetischer Reihenfolge.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Antwort auf die Anfrage

  ```
  {
  "content": [
      "adam@email.com",
      "allison.durance@example.com",
      "amy.dakota@mail.com",
      "andrea.johnson@mail.com",
      ...
  ]
  ...
  }
  ```

* Beispielhafte GET-Anfrage zum Abrufen der E-Mails in der Datenbank in absteigender alphabetischer Reihenfolge.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Antwort auf die Anfrage

  ```
  {
  "content": [
      "tombinder@example.com",
      "tombinder@example.com",
      "timross@example.com",
      "john.smith@example.com",
      ...
  ]
  }
  ```

## Filter {#filtering}

### Abrufen von Filtermetadaten

Für jede Ressource stehen Filter zur Verfügung. Um die mit einer Ressource verknüpften Filter zu ermitteln, müssen Sie eine GET-Anfrage für die Metadaten der Ressource durchführen. Die Anfrage gibt die URL zurück, unter der alle Filter für eine bestimmte Ressource definiert sind. Weiterführende Informationen zu Metadaten finden Sie in [diesem Abschnitt](metadata-mechanism.md).

Um die Metadaten eines Filters und die jeweilige Verwendungsweise zu ermitteln, müssen Sie eine GET-Anfrage für die zuvor zurückgegebene URL durchführen.

<br/>

***Beispielanfrage***

Die folgenden beispielhaften Payloads zeigen, wie die &quot;byText&quot;-Filtermetadaten für die &quot;Profil&quot;-Ressource abgerufen werden. Führen Sie zuerst eine GET-Anfrage für die Metadaten der Ressource &quot;Profil&quot; durch.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Diese gibt die URL zurück, unter der die Filter beschrieben werden.

```
{
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>/filters/"
    }
  }
```

Führen Sie eine GET-Anfrage für die URL aus. Sie erhalten eine Liste der Filter für die Ressource &quot;Profil&quot; mit den jedem Filter zugeordneten Metadaten.

```
{
"birthday": {
        "PKey": "@FL-CbDFXbnHbXcVpeCGWL46VXJLn1LqxLMPagt2vz8sCxQ52lvB15KiUaxXkxJYQw-tZXYrgUWG6K8QcB4gxVY9RKoba5bRFY3294YFshDmorRr8",
        "category": "0150_profile",
        "condition": ...,
        "data": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/birthday?type=$value&precision=$value&operator=$value&day=$value&month=$value&includeStart=$value&endDay=$value&endMonth=$value&includeEnd=$value&relativeValue=$value&nextUnitsValue=$value&previousUnitsValue=$value",
        "formType": "webPage",
        "fragmentName": "",
        "label": "Birthday",
}
```

### Struktur von Filtermetadaten

Jeder Filter weist dieselbe Metadatenstruktur auf:

* Die Felder **@formType** und **@webPage** sind technische Felder.
* Das Feld **Daten** enthält ein Beispiel zur Verwendung des Filters.
* Der Knoten **Metadaten** beschreibt die Filterparameter.
* Der Knoten **Bedingungen** beschreibt, was der Filter tun soll. Die im Metadaten-Knoten beschriebenen Filterparameter dienen zum Erstellen von Filterbedingungen. Wenn **enabledIf** wahr ist, wird für jede Filterbedingung **expr** angewendet.

<br/>

Beispiel für die Metadatenstruktur:

```
"byText": {
        "PKey": "...",
        "category": "99_none",
        "condition": ...,
        "data": "/profileAndServices/profile/byText?text=$value",
        "formType": "none",
        "fragmentName": "",
        "label": "By name or email",
    }
```

### Verwenden von Filtern

Die Filterung wird mit der folgenden Anfrage durchgeführt:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/by<filterName>?<filterParam>=<filterValue>`

Es ist möglich, mehrere Filter in einer einzigen Anfrage zu kombinieren:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/<filter1name>/<filter2name>?<filter1param>=<filter1value>&<filter2param>=<filter2value>`

<br/>

***Beispielanfragen***

* Beispielhafte GET-Anfrage zum Abrufen der &quot;Dienst&quot;-Ressourcen mit dem Typ &quot;email&quot;.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=email \
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
              "created": "2019-09-25 23:20:35.000Z",
              "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/@I_FIiDush4OQPc0mbOVR9USoh36Tt5CsD35lATvQjdWlXrYc0lFkvle2XIwZUbD8GqTVvSp8AfWFUvjkGMe1fPe5nok",
              "label": "Marketing Newsletter",
              "lastModified": "2019-09-25 23:20:35.000Z",
              "limitedDuration": false,
              "messageType": "email",
              "mode": "newsletter",
              ...
          },
          ...
      ],
      ...
  }
  ```

* Beispielhafte GET-Anfrage zum Abrufen der &quot;Profil&quot;-Ressourcen, die in den Feldern &quot;E-Mail&quot; oder &quot;Nachname&quot; die Zeichenfolge &quot;Mustermann&quot; enthalten (der byText-Filter sucht sowohl in den Feldern &quot;E-Mail&quot; als auch &quot;Nachname&quot;).

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Doe \
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
          }
          ...
      ],
      ...
  }
  ```

* Beispielhafte GET-Anfrage zum Abrufen der &quot;Dienst&quot;-Ressourcen mit dem Typ &quot;email&quot; und dem Titel &quot;sport&quot;.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/byText?channel=email&text=sport \
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
              "created": "2019-09-26 09:36:01.014Z",
              "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
              "label": "sport",
              "lastModified": "2019-09-26 09:36:01.014Z",
              "limitedDuration": false,
              "messageType": "email",
              "mode": "newsletter",
              "name": "SVC13",
              ...
          }
      ],
      ...
  }
  ```

### Benutzerdefinierte Filter

Wenn Sie einen benutzerdefinierten Filter verwenden möchten, müssen Sie ihn in der Benutzeroberfläche von Adobe Campaign Standard erstellen und anpassen. Der benutzerdefinierte Filter verhält sich dann genauso wie native Filter:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

Weiterführende Informationen finden Sie in der Campaign Standard-Dokumentation.

* [Filterdefinition konfigurieren](https://helpx.adobe.com/de/campaign/standard/developing/using/configuring-filter-definition.html).
* [Anwendungsbeispiel: Aufrufen einer Ressource mit einem zusammengesetzten Identifizierungsschlüssel](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/adding-or-extending-a-resource/uc-calling-resource-id-key.html?lang=de).

<br/>

***Beispielanfrage***

Beispielhafte GET-Anfrage zum Abrufen der &quot;Profil&quot;-Ressourcen mit Transaktionsbeträgen von 100 $ oder mehr. Beachten Sie, dass der Filter &quot;byAmount&quot; zunächst in der Benutzeroberfläche von Adobe Campaign Standard definiert und mit der benutzerdefinierten Tabelle &quot;Transaction&quot; verknüpft wurde.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byAmount?amount_parameter=100 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!--
Response to the request.

```

{
    "content": [
        {
            "PKey": "<PKEY>",
            "builtIn": false,
            "created": "2019-09-26 09:36:01.014Z",
            "desc": "",
            "end": "",
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
            ...
        }
    ],
}

```

-->

<!-- exemple à vérifier de bout en bout-->

<!--+category = query editor
privacy ?
displayFOrmat ?
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
-->





<!--
 if link ou collection.* resName +
* resTarget tout ca, ca va ensemble : le système de lien, resTarget va donner la ressource targetée par le lien. type
resType = type technique (long..) resType = link alors unbound='false' ou 'true'
If type = enumeration alors champ "values" rajouté et les valeurs sont dans values
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
ail faut que la valeur poster soit conforme ,elle doit valider la dataPolicy . La dataPolicy peut soit controler la valeur (email invalide), soit transformé (cas du smartCase par exemple)
type dans les metadata = type de haut-niveau (nombre, text)
-->

## Zählung {#counting}

Die Adobe Campaign REST-API kann die Anzahl der Datensätze in einer Anfrage zählen. Verwenden Sie dazu die URL, die im Knoten **Zählung** zurückgegeben wird.

<br/>

***Beispielanfrage***

Um alle Dienste zu zählen, deren **messageType**-Wert &quot;sms&quot; ist, führen Sie eine GET-Anfrage mit dem Filter **byChannel** aus.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=sms \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Es werden die Dienste zurückgegeben, die dem Filter entsprechen.

```
{
    "content": [
        {
            ...
            "messageType": "sms",
            "mode": "newsletter",
            "name": "SVC6",
            ...
        },
        ...
    ],
    "count": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/_count?channel=sms&_lineStart=@iKTZ2q3IiSEDqZ5Nw1vdoGnQCqF-8DAUJRaVwR9obqqTxhMy"
    },
    "serverSidePagination": true
}
```

Führen Sie eine GET-Anfrage für die URL des Knotens **Zählung** aus, um die Anzahl der Ergebnisse abzurufen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/_count?channel=sms&_lineStart=@iKTZ2q3IiSEDqZ5Nw1vdoGnQCqF-8DAUJRaVwR9obqqTxhMy \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Es wird die Anzahl der Datensätze zurückgegeben.

```
{
    "count": 26
}
```

## Paginierung {#pagination}

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
