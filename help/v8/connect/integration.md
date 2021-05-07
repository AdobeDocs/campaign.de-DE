---
solution: Campaign
product: Adobe Campaign
title: Erste Schritte mit Marketing-Kampagnen
description: Erste Schritte mit Marketing-Kampagnen
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 6%

---

# Kampagne und andere Lösungen verbinden {#gs-ac-connectors}

Sie können Ihre Kampagne-Instanz mit Adobe Experience Cloud-Lösungen verbinden, um Funktionen zu kombinieren.

Adobe Campaign verfügt über mehrere Connectors, mit denen Sie mit externen Anwendungen kommunizieren, eine Verbindung zu Datenbankmaschinen herstellen, Daten freigeben und synchronisieren können.

## Nutzen Sie Adoben-Lösungen {#gs-ac-integration}

Modernisieren Sie Ihre Implementierung und nutzen Sie alle Adobe Experience Cloud-Funktionen.

:language_ballon: Als Benutzer von Managed Cloud Services [wenden Sie sich an die Adobe](../start/support.md#support), um die Kampagne mit Adobe Experience Cloud-Diensten und -Lösungen zu verbinden. Sie müssen Adobe Identity Management Service (IMS) implementieren. [Mehr dazu](../start/connect.md#connect-ims)

Kampagne v8 kann eine Verbindung herstellen mit:

* [Adobe Journey Orchestration](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/acc-action.html?lang=en)

* [Echtzeit-CDP](../connect/ac-rtcdp.md)

* [Adobe Analytics Data Connector](../connect/ac-aa.md)

* [Adobe Experience Manager](../connect/ac-aem.md)

* [Adobe Target](../connect/ac-at.md)

Sie können Ihre **Audiencen** und **Assets** auch über Experience Cloud-Lösungen mit Funktionen zum Freigeben von Assets und zur Freigabe von Audiencen kombinieren.

:arrow_upper_right: Weitere Informationen zum Freigeben von Audiencen zwischen Kampagnen- und Experience Cloud-Lösungen finden Sie in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/audience-sharing/sharing-audiences-with-adobe-experience-cloud.html?lang=en#integrating-with-adobe-experience-cloud)****

:arrow_upper_right: Weitere Informationen zu **Asset Sharing** zwischen Kampagne- und Experience Cloud-Lösungen finden Sie in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/asset-sharing/sharing-assets-with-adobe-experience-cloud.html?lang=en#integrating-with-adobe-experience-cloud)

## CRM-Connectoren{#gs-crm-connectors}

Sie können Ihre Adobe Campaign-Plattform mit Ihren **CRM-Drittanbietersystemen** verbinden und Daten synchronisieren: Kontakte, Konten, Käufe usw.

Aktivieren Sie Ihre CRM-Daten bei der Kommunikation über Kanal hinweg: Erfahren Sie, wie Sie Kontakte von Ihrem CRM-System an Adobe Campaign weitergeben und Daten zur Kampagne von Adobe Campaign an Ihr CRM-System weitergeben können.
CRM-Connectors ermöglichen eine schnelle und einfache Datenintegration: Adobe Campaign bietet einen engagierten Assistenten zur Erfassung und Auswahl aus den im CRM verfügbaren Tabellen. Dadurch wird eine bidirektionale Synchronisierung gewährleistet, um sicherzustellen, dass die Daten jederzeit auf dem gesamten System auf dem neuesten Stand sind.

:bulb: Erfahren Sie, wie Sie Kampagne mit Microsoft Dynamics 365 und Salesforce.com in [dieser Seite ](crm.md) integrieren.


## Federated Data Access (FDA){#gs-fda}

Verwenden Sie den FDA Connector (Federated Data Access), um eine oder mehrere **externe Datenbanken** zu verbinden und darin gespeicherte Informationen zu verarbeiten, ohne dass sich dies auf Ihre Kampagne Cloud-Datenbankdaten auswirkt.

:bulb: Weitere Informationen finden Sie auf [dieser Seite](fda.md)


<!-- 
 ## Integrate with social media

Use the **Managing social networks (Social Marketing)** option to interact with customers and prospects via Twitter.

* Send messages - Use Adobe Campaign Social Marketing to send messages on Twitter. Adobe Campaign lets you post messages directly to your twitter account. You can also send direct messages to all your followers.

* Collect new contacts - Adobe Campaign Social Marketing also makes it easy to acquire new contacts via Facebook: contact users and ask them if they want to share their profile information. If they accept, Adobe Campaign automatically recovers the data, which enables you to carry out targeting campaigns and, when possible, to implement cross-channel strategies.

:bulb: Learn how to set up and use Campaign Social Marketing in [this section](../connect/ac-tw.md) -->