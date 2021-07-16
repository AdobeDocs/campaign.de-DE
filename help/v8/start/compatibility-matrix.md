---
product: Adobe Campaign
title: Kompatibilitätsmatrix für Campaign v8
description: Erfahren Sie, welche Systeme und Versionen mit Campaign v8 kompatibel sind
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 610a818c1f5d8a43ea55659a3c5b46676405415d
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 96%

---

# Kompatibilitätsmatrix für Campaign v8

In diesem Dokument werden alle Systeme und Komponenten aufgelistet, die für den aktuellen Build von **Adobe Campaign v8** unterstützt werden. Produkte und Versionen, die nicht in dieser Liste enthalten sind, sind nicht mit Adobe Campaign kompatibel.

>[!CAUTION]
>
>* Sofern nicht anders angegeben, werden alle Nebenversionen unterstützt.
>* Wenn bestimmte Versionen dieser Drittanbietersysteme und -Tools das Ende des Lebenszyklus (End of Life, EOL) erreichen, ist Adobe Campaign nicht mehr mit ihnen kompatibel. Diese Versionen werden daher mit der nächsten Produktversion aus unserer Kompatibilitätsmatrix entfernt. Verwenden Sie, um Probleme zu vermeiden, ausschließlich unterstützte Versionen von Systemen, die in der Kompatibilitätsmatrix aufgeführt sind.


## Client-Konsole{#ClientConsoleoperatingsystems}

>[!CAUTION]
>
> Für die Verwendung der Campaign-Client-Konsole sind die folgenden Betriebssysteme und Browser erforderlich.

### Betriebssysteme

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10 (für japanische Instanzen empfohlen))

### Browser

**Microsoft Internet Explorer** 11

## CRM-Connectoren{#CRMconnectors}

* **Salesforce** Connector-API, Version 49
* **Microsoft Dynamic**-Connector, Web API: Dynamics 365 On-Premise und Online

## Federated Data Access (FDA){#FederatedDataAccessFDA}

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## Mobile SDK{#MobileSDK}

* **Android** 7.x, 8.x, 9.0 mit Campaign Android SDK Build 1.1.1.
* **Apple iOS** 9–14 mit Campaign iOS SDK Build 1.0.26, kompatibel mit 32- und 64-Bit-Versionen.

## Web-Zugriff

Die folgenden Browser sind mit Campaign für Web-Zugriff kompatibel.

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (neueste Versionen)

* **Internet Explorer 11**

## So überprüfen Sie Ihre Campaign-Version  und den Build

Rufen Sie das Menü **Hilfe > Versionsinformationen..** auf, um Ihre Version zu überprüfen.

![](assets/ac-version.png)

Sie erhalten folgende Informationen:

* **Versionsnummer** der Client-Konsole und des Anwendungs-Servers. Im obigen Beispiel wird Version 8.1.5 der Client-Konsole und des Anwendungs-Servers verwendet.
* Die SHA-Nummer zwischen Klammern
* Link zur Adobe-Kundenunterstützung
* Links zur Adobe-Datenschutzrichtlinie sowie zu Nutzungsbedingungen und Bestimmungen zu Cookies.
