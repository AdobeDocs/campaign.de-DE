---
title: Interagieren mit benutzerdefinierten Ressourcen
description: Erfahren Sie mehr über die Verwaltung benutzerdefinierter Ressourcen mit APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 100%

---

# Interagieren mit benutzerdefinierten Ressourcen {#interacting-with-custom-resources}

Über den Endpunkt **/customResources** können Sie die benutzerdefinierten Campaign-Ressourcen in REST verfügbar machen. Auf Grundlage dieser API ist eine Integration zwischen benutzerdefinierten Entitäten und externen Endpunkten möglich.

Der Endpunkt /customResources verhält sich genauso wie der Endpunkt /profileAndServices.

Die benutzerdefinierten Ressourcen, die mit dieser API verfügbar werden, beinhalten:

* alle Entitäten, die nicht unter /profileAndServicesExt verfügbar sind
* alle Entitäten, die nicht mit dem Profil verknüpft sind, und für diese Entitäten auch die untergeordneten und weiter untergeordneten Elemente
* standardmäßig alle Entitäten, die mit nichts verknüpft sind, sowie deren untergeordneten und weiter untergeordneten Elemente.

>[!NOTE]
>Die benutzerdefinierten Ressourcen, die unter /profileAndServicesExt verfügbar sind, werden nicht in der API /customResources bereitgestellt.


Hier ein Beispiel zum Abrufen der Metadaten aus einer benutzerdefinierten Ressource:

```
GET /customResources/resourceType/<customResourceName>
```

Zum Erstellen, Aktualisieren oder Löschen werden GET, POST, PATCH und DELETE verwendet.

```
POST /customResources/<customResourceName>
```
