---
title: Versandstatus
description: Erfahren Sie mehr über die Status, die in Ihrem Versand-Dashboard verfügbar sind
feature: Monitoring, Deliverability
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 71%

---

# Versandstatus {#delivery-statuses}

Nachdem ein Versand ausgeführt wurde, zeigt das Versand-Dashboard einen Status an, mit dem Sie überwachen können, ob der Versand erfolgreich war. Die möglichen Status werden im folgenden Abschnitt beschrieben.

![](assets/delivery-status.png)

Weitere Informationen zu den verschiedenen fehlgeschlagenen Sendungen und deren Behebung finden Sie unter [&#x200B; zu fehlgeschlagenen Sendungen &#x200B;](delivery-failures.md).

**Verwandte Themen:**

* [Senden und Überwachen Ihrer E-Mails](send.md)
* [Ursachen für das Fehlschlagen von Sendungen](delivery-failures.md)
* [Erste Schritte mit der Zustellbarkeit](about-deliverability.md)

## Liste der Versandstatus {#list-delivery-statuses}

<table> 
 <thead> 
  <tr> 
   <th> Status<br /> </th> 
   <th> Definitionen und Lösungen<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Gesendet<br /> </td> 
   <td> Gesendet: Der Versand wurde korrekt an den E-Mail-Provider durchgeführt (aber der Empfänger hat sie nicht unbedingt erhalten).<br /> </td> 
  </tr> 
  <tr> 
   <td> Ignoriert<br /> </td> 
   <td> Der Versand wurde aufgrund eines Fehlers in der Adresse des Empfängers nicht an diesen geschickt. Die Adresse war entweder auf einer Blockierungsliste, unter Quarantäne gestellt, nicht angegeben oder ein Duplikat. <br /> </td> 
  </tr> 
  <tr> 
   <td> Fehlgeschlagen<br /> </td> 
   <td> Der Versand hat den Empfänger nicht erreicht, weil die Adresse ungültig oder der Posteingang voll war. Die Ursache kann auch ein Problem mit Gestaltungsbausteinen sein, da diese Fehler hervorrufen können, wenn die Schemata nicht mit dem Versand-Mapping übereinstimmen. Weitere Informationen finden Sie unter <a href="delivery-failures.md" target="_blank">Ursachen von fehlgeschlagenen Sendungen</a><br /> </td> 
  </tr>
  <tr> 
   <td> Ausstehend<br /> </td> 
   <td> Die Nachrichten sind versandbereit und werden vom Versand-Server (MTA) verarbeitet. Siehe <a href="#pending-status" target="_blank">Status „Ausstehend“</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nicht anwendbar<br /> </td> 
   <td> Der Versandserver (MTA) hat den Versand zwar berücksichtigt, aber nicht verarbeitet.<br /> </td> 
  </tr>  
  <tr> 
   <td> Versand abgebrochen<br /> </td> 
   <td> Ein Benutzer hat den Vorgang abgebrochen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Vom Dienstleister berücksichtigt<br /> </td> 
   <td> Bei SMS-Sendungen erhielt der SMS-Dienstleister den Versand.<br /> Bei E-Mail-Sendungen wurde die Nachricht erfolgreich von Campaign an den MTA (Mail Transfer Agent) weitergeleitet.</td> 
  </tr> 
  <tr> 
   <td> Auf Mobiltelefon erhalten<br /> </td> 
   <td> Der Empfänger hat die SMS auf seinem Mobilgerät erhalten.<br /> </td> 
  </tr>
  <tr> 
   <td> Dem Dienstleister übermittelt<br /> </td> 
   <td> Der Versand wurde dem SMS-Dienstleister übermittelt, aber noch nicht von ihm empfangen.<br />
   </td> 
  </tr> 
  <tr> 
   <td> Vorbereitet<br /> </td> 
   <td> Hierbei handelt es sich um einen Zwischenstatus, der ausschließlich für externe Connectoren (z. B. Mobile-Kanal) verwendet wird. Er folgt dem Status 'Ausstehend' und ist der externe Connector, der den folgenden Status bestimmt.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Weitere Informationen zur Optimierung der Zustellbarkeit von mit Adobe Campaign gesendeten E-Mails finden Sie in [diesem Abschnitt](about-deliverability.md). Weitere Informationen zur Zustellbarkeit finden Sie im [Adobe-Handbuch mit den Best Practices zur Zustellbarkeit](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=de).

## Status &quot;Ausstehend&quot; {#pending-status}

Nach der Bestätigung des Versands ist dessen Status **[!UICONTROL Ausstehend]**. Das bedeutet, dass im Ausführungsprozess auf die Verfügbarkeit von Ressourcen gewartet wird.

Der Status **[!UICONTROL Ausstehend]** kann bedeuten, dass der Versand terminiert wurde und bis zum entsprechenden Datum in der Warteschlange bleibt. Weitere Informationen hierzu finden Sie im Abschnitt [Versand planen](configure-and-send.md#schedule-delivery-sending) .

Wenn der Versand nicht durchgeführt wird und sein Status **[!UICONTROL Ausstehend]** bleibt, kann dies folgende Gründe haben:

* **Zu viele Kampagnen gleichzeitig ausgeführt**

  Der Grenzwert gleichzeitiger Kampagnen wird in der Option **[!UICONTROL NmsOperation_LimitConcurrency]** definiert. Der Standardwert ist 10.

  Als Managed Cloud Services-Anwender können Sie mit Adobe zusammenarbeiten, um dieses Limit bei Bedarf anzupassen. Weitere Informationen zu Optionen finden Sie in der Dokumentation zu [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options.html?lang=de){target="_blank"}.

* **Probleme mit der Ressourcenverfügbarkeit**

  Möglicherweise wartet der MTA (Message Transfer Agent) darauf, dass Ressourcen verfügbar werden, bevor die Verarbeitung Ihres Versands beginnt.

>[!NOTE]
>
>Als Campaign v8 Managed Cloud Services-Anwender wird die MTA-Infrastruktur von Adobe überwacht und verwaltet. Wenn Sie anhaltende Probleme mit ausstehenden Sendungen haben, wenden Sie sich an die Adobe-Kundenunterstützung.

**Verwandte Themen:**

* [Senden und Überwachen Ihrer E-Mails](send.md#email-monitoring)
* [Ursachen für das Fehlschlagen von Sendungen](delivery-failures.md)
* [Campaign-Umgebung überwachen](../start/monitor.md#monitor-deliveries)

