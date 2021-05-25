---
solution: Campaign v8
product: Adobe Campaign
title: Einstellungen für Transaktionsnachrichten in Campaign
description: Einstellungen für Transaktionsnachrichten in Campaign
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 7%

---

# Einstellungen für Transaktionsnachrichten

:Sprache_Ballon: Als Benutzer von Managed Cloud Services kontaktieren Sie [Adobe](../start/campaign-faq.md#support), um Campaign-Transaktionsnachrichten in Ihrer Umgebung zu installieren und zu konfigurieren.

:bulb: Die Funktionen für Transaktionsnachrichten werden in [diesem Abschnitt](../send/transactional.md) beschrieben.

:bulb: Verstehen Sie die Architektur von Transaktionsnachrichten in [dieser Seite](../dev/architecture.md).

## Berechtigungen definieren

Um neue Benutzer für in der Adobe Cloud gehostete Message-Center-Ausführungsinstanzen zu erstellen, müssen Sie sich an die Adobe-Kundenunterstützung wenden. Message Center-Benutzer sind bestimmte Benutzer, die spezielle Berechtigungen für den Zugriff auf die Ordner &quot;Echtzeit-Ereignisse&quot;(nmsRtEvent) benötigen.

## Schemaerweiterungen

Alle Schemaerweiterungen, die für die von **Message Center technischen Workflows** verwendeten Schemas in Kontroll- oder Ausführungsinstanzen vorgenommen werden, müssen in den anderen vom Adobe Campaign-Transaktionsnachrichtenmodul verwendeten Instanzen dupliziert werden.

:arrow_upper_right: Weitere Informationen zu technischen Workflows für Message Center finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/instance-configuration/technical-workflows.html?lang=en#control-instance-workflows) .

## Transaktions-Push-Benachrichtigungen senden

In Kombination mit dem Mobile-App-Kanal-Modul ermöglichen Transaktionsnachrichten die Übertragung von Transaktionsnachrichten über Benachrichtigungen auf Mobilgeräte.

:arrow_upper_right: Der Mobile-App-Kanal wird in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages) beschrieben.

Um Transaktions-Push-Benachrichtigungen zu senden, müssen Sie die folgenden Konfigurationen durchführen:

1. Installieren Sie das Package **Mobile App Channel** in den Kontroll- und Ausführungsinstanzen.

   >[!CAUTION]
   >
   >Prüfen Sie Ihren Lizenzvertrag, bevor Sie ein neues natives Campaign-Package installieren.

1. Replizieren Sie den Dienst **Mobile App** und die zugehörigen Mobile Apps auf den Ausführungsinstanzen.

Damit Campaign Transaktions-Push-Benachrichtigungen senden kann, muss das Ereignis die folgenden Elemente enthalten:

* Die Mobilgeräte-ID: **registrationId** für Android und **deviceToken** für iOS. Diese ID stellt die &quot;Adresse&quot;dar, an die die Benachrichtigung gesendet wird.
* Die Verknüpfung zur Mobile App oder zum Integrationsschlüssel (**uuid**), mit der Sie anwendungsspezifische Verbindungsinformationen abrufen können.
* Der Kanal, an den die Benachrichtigung gesendet wird (**wishedChannel**): 41 für iOS und 42 für Android.
* Andere Daten, die für die Personalisierung verwendet werden sollen.

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

