---
solution: Campaign v8
product: Adobe Campaign
title: Mit Campaign und Adobe Analytics arbeiten
description: Erfahren Sie, wie Sie mit Campaign und Adobe Analytics arbeiten
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 4ae0c968bd68d76d7ceffb91023d5426d6a810ea
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 64%

---

# Mit Campaign und Adobe Analytics arbeiten


## Adobe Analytics Connector

Sie können Adobe Analytics Connectors zur Integration von Campaign und Analytics konfigurieren.

Mit Adobe Analytics Connector können Adobe Campaign und Adobe Analytics über das Add-on **Web Analytics Connectors** interagieren. Diese Integration gibt die Daten von Analytics an Campaign als Segmente weiter, die sich auf das Benutzerverhalten nach einer E-Mail beziehen. Umgekehrt sendet es Indikatoren und Attribute von E-Mail-Kampagnen, die von Adobe Campaign bereitgestellt werden, an Adobe Analytics Data Connector.

Mit Adobe Analytics Connector kann Adobe Campaign die Internetzielgruppe (Web Analytics) messen. Dank dieser Integrationen kann Adobe Campaign Daten über das Besucherverhalten für eine oder mehrere Websites nach einer Marketing-Kampagne wiederherstellen und (nach der Analyse) Remarketing-Kampagnen mit dem Ziel durchführen, sie in Käufer zu konvertieren. Umgekehrt ermöglichen die Web-Analyse-Tools von Adobe Campaign die Weiterleitung von Indikatoren und Kampagnenattributen an ihre Plattformen.

Der Aktionsradius der verschiedenen Tools gestaltet sich wie folgt:

* **Adobe Analytics**

   * markiert die mit Adobe Campaign ausgeführten E-Mail-Kampagnen
   * speichert das Verhalten der Empfänger auf der Website, die sie nach dem Klicken auf die Kampagnen-E-Mail besucht haben, in der Form von Segmenten. Die Segmente beziehen sich auf abgebrochene Produkte (angesehen, aber nicht in den Warenkorb gelegt oder gekauft), Käufe oder Warenkorbabbrüche.

* **Adobe Campaign**

   * sendet die Indikatoren und Attribute der Kampagne an den Connector, der sie an das Web-Analytics-Tool übermittelt
   * ruft Segmente ab und analysiert sie
   * löst eine Remarketing-Kampagne aus

Weitere Informationen zu Adobe Campaign und Adobe Analytics finden Sie auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html) .

[!DNL :speech_balloon:]  Wenden Sie sich als Managed Cloud Services-Benutzer  [an ](../start/campaign-faq.md#support) Adobe, um den Adobe Analytics Data Connector in Campaign zu integrieren.


## Experience Cloud Triggers

Sie können Experience Cloud Triggers verwenden, um Daten mithilfe der Pipeline zwischen Adobe Campaign und Adobe Analytics zu verbinden. Die Pipeline ruft die Aktionen oder Trigger des Benutzers von Ihrer Website ab. Ein Beispiel für einen Auslöser ist ein Warenkorbabbruch. Trigger werden in Adobe Campaign verarbeitet, um in nahezu Echtzeit E-Mails zu senden.

Weitere Informationen zu Adobe Campaign- und Experience Cloud-Triggern finden Sie auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en).

[!DNL :speech_balloon:]  Als Benutzer von Managed Cloud Services  [kontaktieren Sie ](../start/campaign-faq.md#support) Adobe, um Experience Cloud-Trigger in Campaign zu implementieren.
