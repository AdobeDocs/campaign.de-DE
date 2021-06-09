---
product: Adobe Campaign
title: Einstellungen für Transaktionsnachrichten in Campaign
description: Einstellungen für Transaktionsnachrichten in Campaign
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: 9cb1b38456601bce21d458fea42a5c112d9fafb4
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 84%

---

# Einstellungen für Transaktionsnachrichten

[!DNL :speech_balloon:] Als Benutzer von Managed Cloud Services  [kontaktieren Sie ](../start/campaign-faq.md#support) Adobe, um Campaign-Transaktionsnachrichten in Ihrer Umgebung zu installieren und zu konfigurieren.

[!DNL :bulb:] In [diesem Abschnitt](../send/transactional.md) sind die Funktionen für Transaktionsnachrichten beschrieben.

[!DNL :bulb:][ Diese Seite](../dev/architecture.md) hilft Ihnen, die Architektur der Transaktionsnachrichten zu verstehen.

## Berechtigungen definieren

Um neue Benutzer für in Adobe Cloud gehostete Message Center-Ausführungsinstanzen zu erstellen, kontaktieren Sie die Adobe-Kundenunterstützung. Message Center-Benutzer benötigen für den Zugriff auf die Ordner &quot;Echtzeit-Ereignisse&quot; (nmsRtEvent) spezifische Berechtigungen.

## Schemaerweiterungen

Alle Erweiterungen von Schemas, die von **technischen Workflows des Message Center-Moduls** in Kontroll- oder Ausführungsinstanzen verwendet werden, müssen in den anderen vom Transaktionsnachrichten-Modul von Adobe Campaign verwendeten Instanzen dupliziert werden.

[!DNL :arrow_upper_right:] Weitere Informationen zu technischen Workflows für Message Center finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html#technical-workflows)

## Push-Benachrichtigungen zu Transaktionen versenden

In Kombination mit dem Mobile-App-Kanal-Modul können Sie über Benachrichtigungen Transaktionsnachrichten an Mobilgeräte senden.

[!DNL :arrow_upper_right:] Der Mobile-App-Kanal wird im  [Campaign Classic v7-Handbuch](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=de#sending-messages) beschrieben.

Um Push-Benachrichtigungen zu Transaktionen zu senden, müssen Sie die folgenden Konfigurationen vornehmen:

1. Installieren Sie das Package **Mobile App Channel** in den Kontroll- und Ausführungsinstanzen.

   >[!CAUTION]
   >
   >Überprüfen Sie Ihre Lizenzvereinbarung, bevor Sie ein neues, in Campaign integriertes Package installieren.

1. Replizieren Sie den Service **Mobile App** und die zugehörigen Mobile Apps in den Ausführungsinstanzen.

Damit Campaign Push-Benachrichtigungen zu Transaktionen senden kann, muss das Ereignis die folgenden Elemente enthalten:

* Die Kennung des Mobilgeräts: **registrationId** für Android und **deviceToken** für iOS. Diese Kennung steht für die &quot;Adresse&quot;, an die die Benachrichtigung gesendet wird.
* Den Link zu der Mobile App oder dem Integrationsschlüssel (**uuid**), der den Abruf der App-spezifischen Verbindungsinformationen erlaubt.
* Den Kanal, über den die Benachrichtigung gesendet wird (**wishedChannel**): 41 für iOS und 42 für Android.
* Andere Daten, die für die Personalisierung genutzt werden sollen.

Beispiel der Verarbeitung eines diese Informationen enthaltenden Ereignisses:

```
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation=”none” uuid="com.adobe.NeoMiles"/>
                <ctx>
                    <deliveryTime>1:30 PM</deliveryTime>
                    <url>http://www.adobe.com</url>
                </ctx>
              </rtEvent>

         </urn:domEvent>
     </urn:PushEvent>           
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

