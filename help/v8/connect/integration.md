---
solution: Campaign v8
product: Adobe Campaign
title: Erste Schritte mit Marketing-Kampagnen
description: Erste Schritte mit Marketing-Kampagnen
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 6%

---

# Verbinden von Campaign mit Ihren Lösungen{#gs-ac-connectors}

Sie können Ihre Campaign-Instanz mit Adobe Experience Cloud-Lösungen verbinden, um Funktionen zu kombinieren.

Adobe Campaign verfügt über mehrere Connectoren, mit denen Sie mit externen Anwendungen kommunizieren, eine Verbindung zu Datenbank-Engines herstellen, Daten freigeben und synchronisieren können.

## Nutzen Sie Adobe-Lösungen {#gs-ac-integration}

Modernisieren Sie Ihre Implementierung und nutzen Sie alle Adobe Experience Cloud-Funktionen.

:Sprache_Ballon: Als Benutzer von Managed Cloud Services kontaktieren Sie [Adobe](../start/campaign-faq.md#support), um Campaign mit Adobe Experience Cloud-Diensten und -Lösungen zu verbinden. Sie müssen den Adobe Identity Management Service (IMS) implementieren. [Mehr dazu](../start/connect.md#connect-ims)

Campaign v8 kann eine Verbindung mit:

* [Journey Orchestration der Adobe](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/acc-action.html?lang=en)

* [Echtzeit-Kundendatenplattform](../connect/ac-rtcdp.md)

* [Adobe Analytics Data Connector](../connect/ac-aa.md)

* [Adobe Experience Manager](../connect/ac-aem.md)

* [Adobe Target](../connect/ac-at.md)

Sie können Ihre **Zielgruppen** und **Assets** auch über Experience Cloud-Lösungen mit Funktionen zur Asset-Freigabe und Zielgruppenfreigabe kombinieren.

:arrow_upper_right: Weitere Informationen zu **Zielgruppenfreigabe** zwischen Campaign- und Experience Cloud-Lösungen finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/audience-sharing/sharing-audiences-with-adobe-experience-cloud.html?lang=en#integrating-with-adobe-experience-cloud) .

:arrow_upper_right: Weitere Informationen zu **Asset-Freigabe** zwischen Campaign- und Experience Cloud-Lösungen finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/asset-sharing/sharing-assets-with-adobe-experience-cloud.html?lang=en#integrating-with-adobe-experience-cloud) .

## CRM-Connectoren{#gs-crm-connectors}

Sie können Ihre Adobe Campaign-Plattform mit Ihren **CRM-Drittanbietersystemen** verbinden und Daten synchronisieren: Kontakte, Konten, Käufe usw.

Aktivieren Sie Ihre CRM-Daten für die kanalübergreifende Kommunikation: Hier erfahren Sie, wie Sie Kontakte aus Ihrem CRM-System an Adobe Campaign weiterleiten und Kampagnendaten aus Adobe Campaign an Ihr CRM-System weitergeben.
CRM-Connectoren ermöglichen eine schnelle und einfache Datenintegration: Adobe Campaign bietet einen speziellen Assistenten zur Erfassung und Auswahl aus den im CRM-System verfügbaren Tabellen. Dies garantiert eine bidirektionale Synchronisation, um sicherzustellen, dass die Daten in allen Systemen jederzeit auf dem neuesten Stand sind.

:bulb: Informationen zur Integration von Campaign mit Microsoft Dynamics 365 und Salesforce.com finden Sie auf [dieser Seite](crm.md)

## Federated Data Access (FDA){#gs-fda}

Verwenden Sie den FDA-Connector (Federated Data Access), um Campaign mit einer oder mehreren **externen Datenbanken** zu verbinden und darin gespeicherte Informationen zu verarbeiten, ohne die Daten Ihrer Campaign Cloud-Datenbank zu beeinträchtigen.

:bulb: Weitere Informationen finden Sie auf [dieser Seite](fda.md)


<!-- 
 ## Integrate with social media

Use the **Managing social networks (Social Marketing)** option to interact with customers and prospects via Twitter.

* Send messages - Use Adobe Campaign Social Marketing to send messages on Twitter. Adobe Campaign lets you post messages directly to your twitter account. You can also send direct messages to all your followers.

* Collect new contacts - Adobe Campaign Social Marketing also makes it easy to acquire new contacts via Facebook: contact users and ask them if they want to share their profile information. If they accept, Adobe Campaign automatically recovers the data, which enables you to carry out targeting campaigns and, when possible, to implement cross-channel strategies.

:bulb: Learn how to set up and use Campaign Social Marketing in [this section](../connect/ac-tw.md) -->