---
title: Verwenden von Campaign und Adobe Experience Platform
description: Informationen zur Verwendung von Campaign und Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: f8c4e05ba2fc97d981fb31f9b11c5de1dcc1ff6e
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 58%

---

# Verwenden von Campaign und Adobe Experience Platform

Die Ziel- und Quell-Connectoren für Adobe Campaign Managed Cloud Service ermöglichen eine nahtlose Integration zwischen Adobe Campaign und Adobe Experience Platform.

* Verwenden eines Adobe Campaign Managed Cloud Services **Zielverbindung** , um Experience Platform-Segmente zur Aktivierung an Adobe Campaign zu senden:

  Konfigurieren Sie dazu eine neue Adobe Campaign Managed Cloud Services **Zielverbindung** , um ein Segment/eine Zielgruppe zu aktivieren und diese Daten an Adobe Campaign zu senden. Geben Sie Details zu der zu verwendenden Campaign-Instanz an, wählen Sie Segmente aus, die für das Ziel aktiviert werden sollen, und konfigurieren Sie dann die Attribute, die Sie in Campaign exportieren möchten. [Erfahren Sie, wie Sie eine Zielverbindung für Adobe Campaign Managed Cloud Services erstellen](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

  ![](assets/aep-destination.png){width="800" align="center"}

* Verwenden eines Adobe Campaign Managed Cloud Services **Quellverbindung** , um Adobe Campaign-Versand- und -Trackinglogs an Adobe Experience Platform zu senden:

  Konfigurieren Sie dazu eine neue Adobe Campaign Managed Cloud Services **Quellverbindung** , um Kampagnenereignisse in die Adobe Experience Platform aufzunehmen. Geben Sie Details zur Campaign-Instanz und zu dem zu verwendenden Schema an, wählen Sie einen Datensatz aus, in den Daten aufgenommen werden sollen, und konfigurieren Sie die abzurufenden Felder. [Erfahren Sie, wie Sie eine Quellverbindung für Adobe Campaign Managed Cloud Services erstellen](https://www.adobe.com/go/sources-campaign-ui-en)

  ![](assets/aep-logs.png){width="800" align="center"}
