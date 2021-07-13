---
product: Adobe Campaign
title: Verbinden von Campaign mit Ihren Lösungen
description: Erfahren Sie, wie Sie Campaign mit Ihren Lösungen verbinden.
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 82%

---

# Verbinden von Campaign mit Ihren Lösungen {#gs-ac-connectors}

Sie können Ihre Campaign-Instanz mit Adobe Experience Cloud-Lösungen verbinden, um Funktionen zu kombinieren.

Adobe Campaign verfügt über mehrere Connectoren, über die Sie mit externen Programmen kommunizieren, eine Verbindung zu Datenbank-Engines herstellen sowie Daten freigeben und synchronisieren können.

## Adobe-Lösungen nutzen {#gs-ac-integration}

Modernisieren Sie Ihre Implementierung und nutzen Sie alle Adobe Experience Cloud-Funktionen.

?? Als Benutzer von Managed Cloud Services kontaktieren Sie [Adobe](../start/campaign-faq.md#support), um Campaign mit Adobe Experience Cloud-Diensten und -Lösungen zu verbinden.

Campaign v8 kann eine Verbindung herstellen mit:


* [Real-Time CDP von Adobe Experience Cloud](../connect/ac-rtcdp.md)
* [Adobe Journey Orchestration](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/acc-action.html?lang=de).

   Siehe das Anwendungsbeispiel [hier](https://experienceleague.adobe.com/docs/journeys/using/use-cases-journeys/campaign-classic-use-case.html?lang=de).

* [Adobe Analytics](../connect/ac-aa.md)
* [Adobe Experience Manager](../connect/ac-aem.md)
* [Adobe Experience Cloud Triggers](../connect/ac-triggers.md)
* [Adobe Target](../connect/ac-at.md)

Sie können Ihre **Audiences** und **Assets** über Experience Cloud-Lösungen hinweg auch mit Funktionen zum Freigeben von Assets und Audiences kombinieren.

↗️ Weitere Informationen zu **Zielgruppenfreigabe** zwischen Campaign- und Experience Cloud-Lösungen finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/audience-sharing/sharing-audiences-with-adobe-experience-cloud.html?lang=de#integrating-with-adobe-experience-cloud)

↗️ Weitere Informationen zu **Asset-Freigabe** zwischen Campaign- und Experience Cloud-Lösungen finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/asset-sharing/sharing-assets-with-adobe-experience-cloud.html?lang=de#integrating-with-adobe-experience-cloud) .

## CRM-Connectoren{#gs-crm-connectors}

Sie können Ihre Adobe Campaign-Plattform mit Ihren **CRM-Systemen von Drittanbietern** verbinden und Daten synchronisieren: Kontakte, Konten, Käufe usw.

Aktivieren Sie Ihre CRM-Daten für kanalübergreifende Kommunikation: Erfahren Sie, wie Sie Kontakte von Ihrem CRM-System an Adobe Campaign weitergeben und wiederum Kampagnendaten von Adobe Campaign mit Ihrem CRM-System teilen können.
CRM-Connectoren ermöglichen eine schnelle und einfache Datenintegration: Adobe Campaign bietet einen dedizierten Assistenten zur Erfassung und Auswahl aus den im CRM verfügbaren Tabellen. Damit ist eine bidirektionale Synchronisation gewährleistet, die sicherstellt, dass die Daten in den Systemen jederzeit aktuell sind.

?? Informationen zur Integration von Campaign mit Microsoft Dynamics 365 und Salesforce.com finden Sie auf [dieser Seite](crm.md)

## Federated Data Access (FDA){#gs-fda}

Verwenden Sie den FDA-Connector (Federated Data Access), um Campaign mit einer oder mehreren **externen Datenbanken** zu verbinden und darin gespeicherte Informationen zu verarbeiten, ohne die Daten in Ihrer Campaign Cloud-Datenbank zu beeinflussen.

?? Weiterführende Informationen finden Sie auf [dieser Seite](fda.md)


<!-- 
 ## Integrate with social media

Use the **Managing social networks (Social Marketing)** option to interact with customers and prospects via Twitter.

* Send messages - Use Adobe Campaign Social Marketing to send messages on Twitter. Adobe Campaign lets you post messages directly to your twitter account. You can also send direct messages to all your followers.

* Collect new contacts - Adobe Campaign Social Marketing also makes it easy to acquire new contacts via Facebook: contact users and ask them if they want to share their profile information. If they accept, Adobe Campaign automatically recovers the data, which enables you to carry out targeting campaigns and, when possible, to implement cross-channel strategies.

💡 Learn how to set up and use Campaign Social Marketing in [this section](../connect/ac-tw.md) -->