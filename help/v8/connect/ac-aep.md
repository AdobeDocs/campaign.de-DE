---
title: Campaign und Adobe Experience Platform verwenden
description: Erfahren Sie, wie Sie mit Campaign und Adobe Experience Platform arbeiten.
feature: Platform Integration
role: Data Engineer
level: Beginner
source-git-commit: 27705fc85794611d1207fe7f3eac3010601b0dc5
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# Campaign und Adobe Experience Platform verwenden

Die Ziel- und Quell-Connectoren für Adobe Campaign Managed Cloud Service ermöglichen eine nahtlose Integration zwischen Adobe Campaign und Adobe Experience Platform:

* Verwendung **Adobe Campaign Managed Cloud Services** Zielverbindung zum Senden von Experience Platform-Segmenten zur Aktivierung an Adobe Campaign;

   ![](assets/aep-destination.png)

* Verwendung **Adobe Campaign Managed Cloud Services** Quellverbindung zum Senden von Adobe Campaign-Versand- und Trackinglogs an Adobe Experience Platform.

   ![](assets/aep-logs.png)

Die Schritte zum Konfigurieren dieser Integration in Adobe Experience Platform lauten wie folgt:

1. Konfigurieren Sie eine neue Adobe Campaign Managed Cloud Services-Zielverbindung, um ein Segment/eine Zielgruppe zu aktivieren und diese Daten an Adobe Campaign zu senden.

   Geben Sie Details zur zu verwendenden Campaign-Instanz an, wählen Sie Segmente aus, die für das Ziel aktiviert werden sollen, und konfigurieren Sie dann die Attribute, die Sie nach Campaign exportieren möchten.

   [Erfahren Sie, wie Sie eine Adobe Campaign Managed Cloud Services-Zielverbindung erstellen](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. Konfigurieren Sie eine neue Adobe Campaign Managed Cloud Services-Quellverbindung, um Campaign-Ereignisse in die Experience Platform von Adobe aufzunehmen.

   Geben Sie Details zur Campaign-Instanz und zum zu verwendenden Schema an, wählen Sie einen Datensatz aus, in den Daten aufgenommen werden sollen, und konfigurieren Sie dann die abzurufenden Felder.

   [Erfahren Sie, wie Sie eine Adobe Campaign Managed Cloud Services-Quellverbindung erstellen](https://www.adobe.com/go/sources-campaign-ui-en)
