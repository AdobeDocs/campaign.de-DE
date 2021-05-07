---
solution: Campaign
product: Adobe Campaign
title: Einstellungen für Kampagne Transactional Messaging
description: Einstellungen für Kampagne Transactional Messaging
feature: Übersicht
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 7%

---

# Einstellungen für Transaktionsnachrichten

:language_ballon: Als Managed Cloud Services-Benutzer wenden Sie sich an die [Adobe](../start/support.md#support), um Kampagne Transactional Messaging in Ihrer Umgebung zu installieren und zu konfigurieren.

:bulb: Die Funktionen für Transaktionsnachrichten sind in [diesem Abschnitt](../send/transactional.md) beschrieben.

:bulb: Verstehen Sie die transaktionale Messaging-Architektur in [dieser Seite](../dev/architecture.md).

## Berechtigungen definieren

Um neue Benutzer für auf der Adobe Cloud gehostete Message Center-Ausführungsinstanzen zu erstellen, wenden Sie sich an die Kundenunterstützung der Adobe. Message Center-Benutzer sind bestimmte Operatoren, die dedizierte Berechtigungen für den Zugriff auf die Ordner &quot;Echtzeit-Ereignisses&quot;(nmsRtEvent) benötigen.

## Schema-Erweiterungen

Alle Schema-Erweiterungen, die auf den von **Message Center-Technischen Workflows** verwendeten Schemas auf einer der Steuerungen oder Ausführungsinstanzen vorgenommen werden, müssen auf den anderen Instanzen dupliziert werden, die vom Adobe Campaign-Transaktionsmessungsmodul verwendet werden.

:arrow_upper_right: Weitere Informationen zu den Technischen Workflows im Nachrichtencenter finden Sie in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/instance-configuration/technical-workflows.html?lang=en#control-instance-workflows)

## Senden transaktionaler Push-Benachrichtigungen

In Kombination mit dem Mobile App Kanal-Modul können Sie mit Transaktionsnachrichten Transaktionsnachrichten über Benachrichtigungen auf Mobilgeräten weiterleiten.

:arrow_upper_right: Der Mobile App Kanal ist in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages) ausführlich beschrieben.

Um transaktionale Push-Benachrichtigungen zu senden, müssen Sie die folgenden Konfigurationen durchführen:

1. Installieren Sie das Package **Mobile App Channel** in den Kontroll- und Ausführungsinstanzen.

   >[!CAUTION]
   >
   >Überprüfen Sie Ihre Lizenzvereinbarung, bevor Sie ein neues, in die Kampagne integriertes Paket installieren.

1. Replizieren Sie den Dienst **Mobilanwendung** und die zugehörigen Mobilanwendungen auf den Ausführungsinstanzen.

Damit Kampagnen transaktionale Push-Benachrichtigungen senden können, muss das Ereignis die folgenden Elemente enthalten:

* Die Mobilgerät-ID: **registrationId** für Android und **deviceToken** für iOS. Diese ID stellt die &quot;Adresse&quot;dar, an die die Benachrichtigung gesendet wird.
* Der Link zur mobilen Anwendung oder zum Integrationsschlüssel (**uuid**), über den Sie anwendungsspezifische Verbindungsinformationen abrufen können.
* Der Kanal, an den die Benachrichtigung gesendet wird (**wseenChannel**): 41 für iOS und 42 für Android.
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

