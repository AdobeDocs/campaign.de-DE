---
title: Kompatibilitätsmatrix für Campaign v8
description: Erfahren Sie, welche Systeme und Versionen mit Campaign v8 kompatibel sind
feature: Release Notes
role: Admin
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: 374c0df2cd95e656cfbaa1fb355bf1f48828dfee
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 65%

---

# Kompatibilitätsmatrix für Campaign v8 {#compat-matrix}

In diesem Dokument werden alle Systeme und Komponenten aufgelistet, die für den aktuellen Build von unterstützt werden. **Adobe Campaign v8** Clientkonsole. Sofern nicht anders angegeben, werden alle Nebenversionen unterstützt. Produkte und Versionen, die nicht in dieser Liste enthalten sind, sind nicht mit Adobe Campaign kompatibel.

Wenn bestimmte Versionen dieser Drittanbietersysteme und -Tools das Ende des Lebenszyklus (End of Life, EOL) erreichen, ist Adobe Campaign nicht mehr mit ihnen kompatibel. Diese Versionen werden daher mit der nächsten Produktversion aus unserer Kompatibilitätsmatrix entfernt. Verwenden Sie, um Probleme zu vermeiden, ausschließlich unterstützte Versionen von Systemen, die in der Kompatibilitätsmatrix aufgeführt sind.

>[!NOTE]
>
>Der Adobe Campaign-Server und die Campaign-Clientkonsole müssen sich auf dieselbe Version befinden. [Erfahren Sie, wie Sie Ihre Version überprüfen](upgrades.md#version).

## Client-Konsole {#ClientConsoleoperatingsystems}

Für die Verwendung der Campaign-Clientkonsole sind die folgenden Betriebssysteme und Browser erforderlich. [Weitere Informationen](connect.md).

### Betriebssysteme{#op-systems}

* **Microsoft Windows Server** 2019, 2016
* **Microsoft Windows** 11, 10

>[!NOTE]
>
>Beachten Sie, dass die 32-Bit-Version der Clientkonsole seit Version 8.5 nicht mehr unterstützt wird. Ab 8.6 ist die Client-Konsole nur noch mit 64 Bit verfügbar. Weitere Informationen zum Upgrade Ihres Systems finden Sie in diesem [Technote](../../technotes/upgrades/console.md).

### Webbrowser {#web-browsers}

* **Microsoft Edge**

* **Microsoft Edge WebView2**, neueste Version. Sie kann von der [Microsoft Developer-Website](http://www.adobe.com/go/acc-ms-webview2-runtime-download_de){target="_blank"} heruntergeladen werden.

## CRM-Connectoren {#CRMconnectors}

Die folgenden CRM-Systeme (Customer Relationship Management) sind mit Adobe Campaign kompatibel. [Weitere Informationen](../connect/crm.md).

* **Salesforce**-Connector-API, Version 49
* **Microsoft Dynamic**-Connector, Web API: Dynamics 365 On-Premise und Online

## Federated Data Access (FDA){#FederatedDataAccessFDA}

Die folgenden externen Datenbanken sind mit dem Adobe Campaign Federated Data Access (FDA)-Modul kompatibel. [Weitere Informationen](../connect/fda.md).

* **[!DNL Amazon Redshift]**
* **[!DNL Azure Synapse]**, ab Campaign v8.5
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## Mobile SDK {#MobileSDK}

Zum Senden von [Push-Benachrichtigungen](../send/push.md) mit Campaign können Sie das Adobe Experience Platform Mobile SDK verwenden, indem Sie die Adobe Campaign-Erweiterung in der Benutzeroberfläche „Datenerfassung“ konfigurieren.

Die kompatiblen Versionen für iOS und Android werden im Abschnitt [Adobe Developer-Dokumentation](https://developer.adobe.com/client-sdks/home/)

## Web-Zugriff {#web-access}

Die folgenden Browser sind mit Campaign für den [Web-Zugriff](connect.md#web-access) kompatibel.

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (neueste Versionen)


## Zusätzliche Ressourcen {#support}

* [Aktualisierungen der Campaign-Version](upgrades.md)
* [Überprüfen der Campaign-Version](upgrades.md#version)
* [Installieren der Campaign-Clientkonsole](connect.md)
* [Control Panel-Versionen](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=de){target="_blank"}.

Um über neue Experience Cloud-Lösungsversionen informiert zu werden, abonnieren Sie die [Adobe Priority Product Update](https://www.adobe.com/de/subscription/priority-product-update.html){target="_blank"}.