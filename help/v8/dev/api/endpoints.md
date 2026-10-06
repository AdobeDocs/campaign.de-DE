---
title: Endpunkte
description: Erfahren Sie mehr über die API-Endpunkte.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
TQID: 'https://experienceleague.adobe.com/1ajh28ZpUsuyTh-qHnto3GsH4J25WSsyK7TqTjlhHfg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
    internal-label: REST API
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 100%
---
# Endpunkte {#endpoints}

Die verfügbaren Endpunkte für die Adobe Campaign REST-API:

* **/profileAndServices**: zur Interaktion mit vordefinierten Feldern. Erweiterte Felder können bei diesem Endpunkt nicht aufgerufen werden.
* **/profileAndServicesExt**: zur Interaktion mit benutzerdefinierten Feldern, die bei der benutzerdefinierten Ressourcenerweiterung von Profil oder Dienste hinzugefügt werden. Weiterführende Informationen zu benutzerdefinierten Ressourcen finden Sie in [diesem Abschnitt](custom-resources.md).
* **/&lt;transactionalAPI>**: zur Interaktion mit der API für Transaktionsnachrichten (der Name des API-Endpunkts für Transaktionsnachrichten hängt von der Konfiguration Ihrer Instanz ab). Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](managing-transactional-messages.md).
* **/workflow/execute**: zur Interaktion mit Workflows. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](controlling-a-workflow.md).

Standardmäßig stehen für die APIs **profileAndServices** und **profileAndServicesExt** folgende Hauptressourcen zur Verfügung:

* **/profile**: zur Interaktion mit Profilen aus der Campaign-Datenbank. Um einem Dienst Profile hinzuzufügen, verwenden Sie den Endpunkt **/service**. Weitere Informationen zu Profilen in Campaign finden Sie in der [Campaign-Dokumentation](https://helpx.adobe.com/de/campaign/standard/audiences/using/about-profiles.html).
* **/service**: zum Verwalten von Anmeldediensten. Weitere Informationen zu Diensten in Campaign finden Sie in der [Campaign-Dokumentation](https://helpx.adobe.com/de/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Alle anderen Ressourcen, die erweitert oder erstellt wurden, stehen nur über die API **ProfileAndServicesExt** zur Verfügung. Sie müssen mit der **Profil**-Ressource verknüpft sein, um aufgerufen werden zu können.
