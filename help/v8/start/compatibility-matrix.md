---
title: Kompatibilitätsmatrix für Campaign v8
description: Erfahren Sie, welche Systeme und Versionen mit Campaign v8 kompatibel sind
feature: Release Notes
role: Admin
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: 1857f0f40d554abededfaa0c1e3dec4b57ca23b7
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 99%

---

# Kompatibilitätsmatrix für Campaign v8 {#compat-matrix}

In diesem Dokument werden alle Systeme und Komponenten aufgelistet, die für den aktuellen Build der **Adobe Campaign v8**-Client-Konsole unterstützt werden. Sofern nicht anders angegeben, werden alle Nebenversionen unterstützt. Produkte und Versionen, die nicht in dieser Liste enthalten sind, sind nicht mit Adobe Campaign kompatibel.

Wenn bestimmte Versionen dieser Drittanbietersysteme und -Tools das Ende des Lebenszyklus (End of Life, EOL) erreichen, ist Adobe Campaign nicht mehr mit ihnen kompatibel. Diese Versionen werden daher mit der nächsten Produktversion aus unserer Kompatibilitätsmatrix entfernt. Verwenden Sie, um Probleme zu vermeiden, ausschließlich unterstützte Versionen von Systemen, die in der Kompatibilitätsmatrix aufgeführt sind.

>[!NOTE]
>
>Adobe Campaign Server und die Campaign-Client-Konsole müssen dieselbe Version verwenden. [Erfahren Sie, wie Sie Ihre Version überprüfen](upgrades.md#version).

## Client-Konsole {#ClientConsoleoperatingsystems}

Für die Nutzung der Campaign-Client-Konsole sind die folgenden Betriebssysteme und Browser erforderlich. [Weitere Informationen](connect.md).

### Betriebssysteme {#op-systems}

* **Microsoft Windows Server** 2019, 2016
* **Microsoft Windows** 11, 10

>[!NOTE]
>Die 32-Bit-Version der Client-Konsole wird seit Version 8.5 nicht mehr unterstützt. Ab 8.6. ist die Client-Konsole nur noch in 64 Bit verfügbar. Weitere Informationen zum Upgrade Ihres Systems finden Sie in dieser [Technote](../../technotes/upgrades/console.md).

### Webbrowser {#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, neueste Version. Sie kann von der [Microsoft Developer-Website](http://www.adobe.com/go/acc-ms-webview2-runtime-download_de){target="_blank"} heruntergeladen werden.

## CRM-Connectoren {#CRMconnectors}

Die folgenden CRM-Systeme (Customer Relationship Management) sind mit Adobe Campaign kompatibel. Weitere Informationen zu CRM-Connectoren finden Sie [auf dieser Seite](../connect/crm.md).

* **Salesforce**-Connector-API, Version 49
* **Microsoft Dynamic**-Connector, Web API: Dynamics 365 On-Premise und Online

## Federated Data Access (FDA){#FederatedDataAccessFDA}

Die folgenden externen Datenbanken sind mit dem Adobe Campaign Federated Data Access (FDA)-Modul kompatibel. Weitere Informationen über FDA finden Sie [auf dieser Seite](../connect/fda.md).

* **[!DNL Amazon Redshift]**
* **[!DNL Azure Synapse]**, ab Campaign v8.5
* **[!DNL Databricks]**, ab Campaign v8.7
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## Mobile SDK {#MobileSDK}

Zum Senden von [Push-Benachrichtigungen](../send/push.md) mit Campaign können Sie das Adobe Experience Platform Mobile SDK verwenden, indem Sie die Adobe Campaign-Erweiterung in der Benutzeroberfläche „Datenerfassung“ konfigurieren.

Kompatible Versionen für iOS und Android werden in der [Adobe Developer-Dokumentation](https://developer.adobe.com/client-sdks/home/){target="_blank"} beschrieben.

## Web-Benutzeroberfläche {#web-ui}

Die folgenden Browser sind mit der Campaign Web-Benutzeroberfläche kompatibel. [Auf dieser Seite](campaign-ui.md#ac-web-ui) erfahren Sie mehr über die Campaign Web-Benutzeroberfläche.

* **Microsoft Edge**, **Google Chrome**, **Safari** (neueste Versionen)

## Web-Zugriff {#web-access}

Die folgenden Browser sind mit der Campaign Web-Benutzeroberfläche kompatibel. Weitere Informationen zum Web-basierten Zugriff auf Campaign finden Sie [auf dieser Seite](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (neueste Versionen)

## Zusätzliche Ressourcen {#support}

* [Campaign – Versionsaktualisierungen](upgrades.md)
* [Überprüfen Sie Ihre Campaign-Version](upgrades.md#version)
* [Installieren der Campaign-Client-Konsole](connect.md)
* [Control Panel-Versionen](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=de){target="_blank"}

Abonnieren Sie das [Prioritätsprodukt-Update von Adobe](https://www.adobe.com/de/subscription/priority-product-update.html){target="_blank"}, um über neue Versionen der Experience Cloud-Lösungen informiert zu werden.