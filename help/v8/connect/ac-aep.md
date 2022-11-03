---
title: Verwenden von Campaign und Adobe Experience Platform
description: Informationen zur Verwendung von Campaign und Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
source-git-commit: 9bea7904ea4507083d2cf45193877e7a2539d0c7
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 54%

---

# Verwenden von Campaign und Adobe Experience Platform

Die Adobe Campaign Managed Cloud Service Destination- und Source-Connectoren ermöglichen eine nahtlose Integration zwischen Adobe Campaign und Adobe Experience Platform.

* Verwendung **Adobe Campaign Managed Cloud Services** Zielverbindung zum Senden von Experience Platform-Segmenten zur Aktivierung an Adobe Campaign,

   ![](assets/aep-destination.png)

* Verwendung **Adobe Campaign Managed Cloud Services** Quellverbindung zum Senden von Adobe Campaign-Versand- und Trackinglogs an Adobe Experience Platform.

   ![](assets/aep-logs.png)

Die Schritte zum Konfigurieren dieser Integration in Adobe Experience Platform lauten wie folgt:

1. Konfigurieren Sie eine neue Adobe Campaign Managed Cloud Services Destination-Verbindung, um ein Segment/eine Zielgruppe zu aktivieren und diese Daten an Adobe Campaign zu senden.

   Geben Sie Details zu der zu verwendenden Campaign-Instanz an, wählen Sie Segmente aus, die für das Ziel aktiviert werden sollen, und konfigurieren Sie dann die Attribute, die Sie in Campaign exportieren möchten.

   [Erfahren Sie, wie Sie eine Zielverbindung für Adobe Campaign Managed Cloud Services erstellen](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. Konfigurieren Sie eine neue Adobe Campaign Managed Cloud Services-Quellverbindung, um Campaign-Ereignisse in die Adobe Experience Platform aufzunehmen.

   Geben Sie Details zur Campaign-Instanz und zu dem zu verwendenden Schema an, wählen Sie einen Datensatz aus, in den Daten aufgenommen werden sollen, und konfigurieren Sie die abzurufenden Felder.

   [Erfahren Sie, wie Sie eine Quellverbindung für Adobe Campaign Managed Cloud Services erstellen](https://www.adobe.com/go/sources-campaign-ui-en)
