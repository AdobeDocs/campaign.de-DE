---
solution: Campaign v8
product: Adobe Campaign
title: Campaign und Adobe Analytics verwenden
description: Erfahren Sie, wie Sie mit Campaign und Adobe Analytics arbeiten.
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 4ae0c968bd68d76d7ceffb91023d5426d6a810ea
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 20%

---

# Campaign und Adobe Analytics verwenden


## Adobe Analytics Connector

Sie können Adobe Analytics Connectors zur Integration von Campaign und Analytics konfigurieren.

Mit Adobe Analytics Connector können Adobe Campaign und Adobe Analytics über das Add-on **Web Analytics Connectors** interagieren. Diese Integration teilt Daten aus Analytics in Campaign als Segmente im Zusammenhang mit dem Benutzerverhalten nach einer E-Mail. Umgekehrt werden Indikatoren und Attribute von E-Mail-Kampagnen gesendet, die von Adobe Campaign an Adobe Analytics - Data Connector bereitgestellt werden.

Mit Adobe Analytics Connector kann Adobe Campaign die Internetzielgruppe (Web Analytics) messen. Dank dieser Integrationen kann Adobe Campaign Daten zum Besucherverhalten für eine oder mehrere Sites im Anschluss an eine Marketingkampagne abrufen und (nach der Analyse) Remarketing-Kampagnen durchführen, um sie in Käufer zu konvertieren. Umgekehrt ermöglichen die Webanalysetools es Adobe Campaign, Indikatoren und Kampagnenattribute an ihre Plattformen weiterzuleiten.

Der Aktionsradius der verschiedenen Tools gestaltet sich wie folgt:

* **Adobe Analytics**

   * markiert die mit Adobe Campaign ausgeführten E-Mail-Kampagnen
   * speichert das Empfängerverhalten in Form von Segmenten auf der Site, die nach dem Kampagnen-E-Mail-Klick durchsucht wurde. Segmente beziehen sich auf verlassene Produkte (angezeigt, aber nicht zum Warenkorb hinzugefügt oder gekauft), Käufe oder Warenkorbabbrüche.

* **Adobe Campaign**

   * sendet die Indikatoren und Attribute der Kampagne an den Connector, welcher sie an das Web-Analytics-Tool übermittelt
   * ruft Segmente ab und analysiert sie
   * löst eine Remarketing-Kampagne aus

Weitere Informationen zu Adobe Campaign und Adobe Analytics finden Sie auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html) .

[!DNL :speech_balloon:]  Wenden Sie sich als Managed Cloud Services-Benutzer  [an ](../start/campaign-faq.md#support) Adobe, um den Adobe Analytics Data Connector in Campaign zu integrieren.


## Experience Cloud Triggers

Sie können Experience Cloud-Trigger verwenden, um mithilfe der Pipeline Daten zwischen Adobe Campaign und Adobe Analytics zu verbinden. Die Pipeline ruft die Aktionen oder Trigger des Benutzers von Ihrer Website ab. Ein Beispiel für einen Auslöser ist ein Warenkorbabbruch. Trigger werden in Adobe Campaign verarbeitet, um in nahezu Echtzeit E-Mails zu senden.

Weitere Informationen zu Adobe Campaign- und Experience Cloud-Triggern finden Sie auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en).

[!DNL :speech_balloon:]  Als Benutzer von Managed Cloud Services  [kontaktieren Sie ](../start/campaign-faq.md#support) Adobe, um Experience Cloud-Trigger in Campaign zu implementieren.
