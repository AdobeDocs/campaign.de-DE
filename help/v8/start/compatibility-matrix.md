---
product: Adobe Campaign
title: Kompatibilitätsmatrix für Campaign v8
description: Erfahren Sie, welche Systeme und Versionen mit Campaign v8 kompatibel sind
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 29d6a1545722afa3a07c98de1ab453cdb0a618d2
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 75%

---

# Kompatibilitätsmatrix für Campaign v8

In diesem Dokument werden alle Systeme und Komponenten aufgelistet, die für den aktuellen Build von **Adobe Campaign v8** unterstützt werden. Produkte und Versionen, die nicht in dieser Liste enthalten sind, sind nicht mit Adobe Campaign kompatibel.

>[!CAUTION]
>
>* Sofern nicht anders angegeben, werden alle Nebenversionen unterstützt.
>* Wenn bestimmte Versionen dieser Drittanbietersysteme und -Tools das Ende des Lebenszyklus (End of Life, EOL) erreichen, ist Adobe Campaign nicht mehr mit ihnen kompatibel. Diese Versionen werden daher mit der nächsten Produktversion aus unserer Kompatibilitätsmatrix entfernt. Verwenden Sie, um Probleme zu vermeiden, ausschließlich unterstützte Versionen von Systemen, die in der Kompatibilitätsmatrix aufgeführt sind.


## Kompatible Systeme

### Client-Konsole{#ClientConsoleoperatingsystems}

:Warnung: Für die Verwendung der Campaign-Client-Konsole sind die folgenden Betriebssysteme und Browser erforderlich.

**Betriebssysteme**

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10 (für japanische Instanzen empfohlen))

**Browser**

**Microsoft Internet Explorer** 11

### CRM-Connectoren{#CRMconnectors}

* **Salesforce** Connector-API, Version 49
* **Microsoft Dynamic**-Connector, Web API: Dynamics 365 On-Premise und Online

### Federated Data Access (FDA){#FederatedDataAccessFDA}

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

### Mobile SDK{#MobileSDK}

* **Android** 7.x, 8.x, 9.0 mit Mobile SDK Build 1.1.1.
* **Apple iOS** 9–14 mit Mobile SDK Build 1.0.26, kompatibel mit 32- und 64-Bit-Versionen.

### Unterstützte Browser {#Browsers}

Die folgenden Browser sind mit Campaign für Web-Zugriff kompatibel.

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (neueste Versionen)

* **Internet Explorer 11**

## So überprüfen Sie Ihre Campaign-Version und erstellen

Verwenden Sie das Menü **Hilfe > Versionsinformationen..** , um Ihre Version zu überprüfen.

![](assets/ac-version.png)

Sie greifen auf die folgenden Informationen zu:

* Die **version**-Nummer Ihrer Client-Konsole und des Anwendungsservers. Im obigen Beispiel ist die Version 8.1.5 sowohl für die Client-Konsole als auch für den Anwendungsserver.
* Die SHA-Nummer zwischen Klammern.
* Link zur Kontaktaufnahme mit der Kundenunterstützung von Adobe.
* Links zu Datenschutzrichtlinien für Adoben, Nutzungsbedingungen und Cookie-Richtlinien.
