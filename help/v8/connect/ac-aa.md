---
solution: Campaign Classic
product: campaign
title: Arbeiten mit Kampagne und Adobe Analytics
description: Erfahren Sie, wie Sie mit Kampagne und Adobe Analytics arbeiten können
feature: Übersicht
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
translation-type: tm+mt
source-git-commit: c2d066ca2f935455861c3d6747c9805c847f2e0d
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 22%

---

# Arbeiten mit Kampagne und Adobe Analytics

## Experience Cloud Triggers

Sie können Experience Cloud-Trigger verwenden, um Daten mithilfe der Pipeline zwischen Adobe Campaign und Adobe Analytics zu verbinden. Die Pipeline ruft Benutzeraktionen oder Trigger von Ihrer Website ab. Ein Beispiel für einen Auslöser ist ein Warenkorbabbruch. Trigger werden in Adobe Campaign verarbeitet, um in nahezu Echtzeit E-Mails zu senden.

:language_ballon: Als Benutzer mit Managed Cloud Services [wenden Sie sich an die Adobe](../start/support.md#support), um Experience Cloud-Trigger mit Kampagne zu implementieren.

## Der Data Connector von Adobe Analytics

SO AKTUALISIEREN SIE DIE NEUE INTEGRATION

Sie können auch Adobe Analytics Data Connectors konfigurieren, um Kampagne und Analytics zu integrieren.

Data Connector (früher Adobe Genesis genannt) ermöglicht es Adobe Campaign und Adobe Analytics, über das **Webanalyseschnittstellen**-Paket zu interagieren. Diese Integration verwendet Daten aus Analytics für die Kampagne als Segmente im Zusammenhang mit dem Benutzerverhalten nach einer E-Mail. Umgekehrt sendet es Indikatoren und Attribute von E-Mail-Kampagnen, die von Adobe Campaign an Adobe Analytics - Data Connector gesendet werden.

Dank dieser Integrationen kann Adobe Campaign Daten zum Verhalten von Besuchern für eine oder mehrere Sites nach einer Marketing-Kampagne wiederherstellen und (nach der Analyse) Remarketing-Kampagnen mit der Ansicht ausführen, diese in Käufer umzuwandeln. Umgekehrt ermöglichen die Webanalysetools Adobe Campaign, Indikatoren und Kampagnen-Attribute an ihre Plattformen weiterzuleiten.

Der Aktionsradius der verschiedenen Tools gestaltet sich wie folgt:

* Adobe Analytics:

   * markiert die mit Adobe Campaign ausgeführten E-Mail-Kampagnen
   * speichert das Verhalten der Empfänger auf der Site, die sie nach dem Klicken auf die Kampagnen-E-Mail durchsucht haben, in Segmentform. Segmente beziehen sich auf verlassene Produkte (angezeigt, aber nicht zum Einkaufswagen hinzugefügt oder gekauft), Käufe oder Warenkorbabbrüche.

* Adobe Campaign:

   * sendet die Indikatoren und Attribute der Kampagne an den Connector, welcher sie an das Web-Analytics-Tool übermittelt
   * ruft Segmente ab und analysiert sie
   * löst eine Remarketing-Kampagne aus

SIEHE https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html?lang=en#technical-workflows-of-web-analytics-processes

:language_ballon: Als Benutzer von Managed Cloud Services [wenden Sie sich an die Adobe](../start/support.md#support), um Adobe Analytics Data Connector mit der Kampagne zu integrieren.

