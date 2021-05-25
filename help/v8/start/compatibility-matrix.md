---
solution: Campaign v8
product: Adobe Campaign
title: Kompatibilitätsmatrix von Campaign v8
description: Erfahren Sie mehr über Systeme und Versionen, die mit Campaign v8 kompatibel sind.
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: ffdfc9a2e1bec191b5a3cc7f7b40683b2456bf3e
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 31%

---

# Kompatibilitätsmatrix von Campaign v8

In diesem Dokument werden alle Systeme und Komponenten aufgelistet, die für den aktuellen Build von **Adobe Campaign v8** unterstützt werden. Produkte und Versionen, die nicht in dieser Liste enthalten sind, sind nicht mit Adobe Campaign kompatibel.

>[!CAUTION]
>
>* Sofern nicht anders angegeben, werden alle Nebenversionen unterstützt.
>* Da bestimmte Versionen dieser Drittanbietersysteme und -Tools das Ende der Lebensdauer (End of Life, EOL) erreichen, ist Adobe Campaign nicht mehr mit diesen Versionen kompatibel und sie werden aus dieser Kompatibilitätsmatrix entfernt. Verwenden Sie, um Probleme zu vermeiden, ausschließlich unterstützte Versionen von Systemen, die in der Kompatibilitätsmatrix aufgeführt sind.


## Kompatible Systeme

### Client-Konsole{#ClientConsoleoperatingsystems}

:Warnung: Für die Verwendung der Campaign-Client-Konsole sind die folgenden Betriebssysteme und Browser erforderlich.

**Betriebssysteme**

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10 (empfohlen für japanische Instanzen)

**Browser**

**Microsoft Internet Explorer** 11

### CRM-Connectoren{#CRMconnectors}

* **** Salesforce Connector API Version 49
* **Microsoft** Dynamic Connector, Web API: On-Premise- und Online-Modus von Dynamics 365

### Federated Data Access (FDA){#FederatedDataAccessFDA}

* **Amazon Redshift**
* **[!DNL Snowflake]**

### Mobile SDK{#MobileSDK}

* **Android** 7.x, 8.x, 9.0 mit Mobile SDK Build 1.0.27.
* **Apple iOS** 9 - 14 mit Mobile SDK Build 1.0.26, kompatibel mit 32- und 64-Bit-Versionen.

### Unterstützte Browser {#Browsers}

Die folgenden Browser sind mit Campaign für Web-Zugriff kompatibel.

* **Microsoft Edge**,  **Mozilla Firefox**,  **Google Chrome**,  **Safari**  (neueste Versionen)

* **Internet Explorer 11**

## Überprüfen der Campaign-Version

Verwenden Sie das Menü **Hilfe > Versionsinformationen..** , um Ihre Version zu überprüfen.

![](assets/ac-version.png)

Sie greifen auf die folgenden Informationen zu:

* Die **version**-Nummer Ihrer Client-Konsole und des Anwendungsservers. Im obigen Beispiel ist die Version 8.1.5 sowohl für die Client-Konsole als auch für den Anwendungsserver.
* Die SHA-Nummer zwischen Klammern.
* Link zur Kontaktaufnahme mit der Kundenunterstützung von Adobe.
* Links zu Datenschutzrichtlinien für Adoben, Nutzungsbedingungen und Cookie-Richtlinien.
