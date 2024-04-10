---
title: Einstellungen für Transaktionsnachrichten in Campaign
description: Einstellungen für Transaktionsnachrichten in Campaign
feature: Transactional Messaging
role: Admin, Developer
level: Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 97%

---

# Einstellungen für Transaktionsnachrichten {#mc-settings}

Das Campaign-Modul „Transaktionsnachricht (Message Center)“ wurde zum Verwalten von Trigger-Nachrichten entwickelt. Weitere Informationen zu Transaktionsnachrichten finden Sie in [diesem Abschnitt](../send/transactional.md).

[Diese Seite](../architecture/architecture.md#transac-msg-archi) hilft Ihnen, die Architektur der Transaktionsnachrichten zu verstehen.


>[!NOTE]
>
>Als Benutzer von Managed Cloud Service [Kontakt Adobe](../start/campaign-faq.md#support) , um Campaign-Transaktionsnachrichten in Ihrer Umgebung zu installieren und zu konfigurieren.

## Definieren von Berechtigungen {#mc-permissions}

Wenden Sie sich an Ihren Adobe Transition Manager, um neue Benutzerinnen und Benutzer für Ausführungsinstanzen Ihres Message Centers zu erstellen, die auf Adobe Cloud gehostet werden. Benutzende des Message Centers sind spezifische Benutzende, die spezielle Berechtigungen für den Zugriff auf die Ordner „Echtzeit-Ereignisse“ (nmsRtEvent) benötigen.

## Schemaerweiterungen  {#mc-schema-ext}

Alle Schemaerweiterungen, die von [technischen Workflows des Message Center-Moduls](#technical-workflows) in Kontroll- oder Ausführungsinstanzen verwendet werden, müssen in den anderen vom Transaktionsnachrichten-Modul von Adobe Campaign verwendeten Instanzen dupliziert werden.

## Push-Benachrichtigungen zu Transaktionen versenden {#mc-transactional-push}

In Kombination mit dem [Mobile-App-Kanal-Modul](../send/push.md) können Sie Transaktionsnachrichten über Benachrichtigungen auf Mobilgeräten pushen.

Um Push-Benachrichtigungen zu Transaktionen zu senden, müssen Sie die folgenden Konfigurationen vornehmen:

1. Installieren Sie das Package **Mobile App Channel** in den Kontroll- und Ausführungsinstanzen.

   >[!CAUTION]
   >
   >Prüfen Sie Ihre Lizenzvereinbarung, bevor Sie ein neues integriertes Campaign-Paket installieren.

1. Replizieren Sie den Service **Mobile App** und die zugehörigen Mobile Apps in den Ausführungsinstanzen.

Das Ereignis muss darüber hinaus folgende Elemente enthalten:

* Die Kennung des Mobilgeräts: **registrationId** für Android und **deviceToken** für iOS. Diese Kennung ist die „Adresse“, an die die Benachrichtigung gesendet wird.
* Den Link zu der Mobile App oder dem Integrationsschlüssel (**uuid**), der den Abruf der App-spezifischen Verbindungsinformationen erlaubt.
* Den Kanal, über den die Benachrichtigung gesendet wird (**wishedChannel**): 41 für iOS und 42 für Android.
* Alle anderen Personalisierungsdaten.

Nachfolgend finden Sie ein Beispiel für eine Ereigniskonfiguration zum Senden von Transaktions-Push-Benachrichtigungen:

```xml
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation="none" uuid="com.adobe.NeoMiles"/>
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

## Ereignisse bereinigen {#purge-events}

Sie können die Einstellungen des Bereitstellungsassistenten anpassen, um zu konfigurieren, wie lange die Daten in der Datenbank gespeichert werden.

Die Ereignislöschung wird automatisch vom technischen Workflow **Datenbankbereinigung** durchgeführt. Dieser Workflow löscht die in den Ausführungsinstanzen empfangenen und gespeicherten Ereignisse sowie die in einer Kontrollinstanz archivierten Ereignisse.

Verwenden Sie die Pfeile, um die Bereinigungsparameter für die **Ereignisse** (in einer Ausführungsinstanz) und **Archivierte Ereignisse** (in einer Kontrollinstanz) zu ändern.


## Technische Workflows {#technical-workflows}

Sie müssen sicherstellen, dass die technischen Workflows für Ihre Kontroll- und Ausführungsinstanzen gestartet wurden, bevor Transaktionsnachrichtenvorlagen bereitgestellt werden.

Diese Workflows können Sie dann über den Ordner **Administration > Betreibung > Message Center** aufrufen.

### Workflows der Kontrollinstanz {#control-instance-workflows}

In der Kontrollinstanz müssen Sie für jedes externe Konto der **[!UICONTROL Message-Center-Ausführungsinstanz]** einen Archivierungs-Workflow erstellen. Klicken Sie auf die Schaltfläche **[!UICONTROL Archivierungs-Workflow erstellen]**, um den Workflow zu erstellen und zu starten.

### Workflows der Ausführungsinstanz {#execution-instance-workflows}

In der/den Ausführungsinstanz(en) müssen die folgenden technischen Workflows gestartet werden:

* **[!UICONTROL Batch-Ereignisse verarbeiten]** (interner Name **[!UICONTROL batchEventsProcessing]** ): Mit diesem Workflow schlüsseln Sie Batch-Ereignisse in einer Warteschlange auf, bevor sie mit einer Nachrichtenvorlage verknüpft werden.
* **[!UICONTROL Echtzeitereignisse verarbeiten]** (interner Name **[!UICONTROL rtEventsProcessing]**): Mit diesem Workflow schlüsseln Sie Echtzeitereignisse in einer Warteschlange auf, bevor sie mit einer Nachrichtenvorlage verknüpft werden.
* **[!UICONTROL Ereignisstatus aktualisieren]**(interner Name: **[!UICONTROL updateEventStatus]**): Mit diesem Workflow weisen Sie dem Ereignis einen Status zu.

  Mögliche Ereignisstatus sind:

   * **[!UICONTROL Ausstehend]**: Das Ereignis befindet sich in der Warteschlange und wurde noch keiner Nachrichtenvorlage zugeteilt.
   * **[!UICONTROL Versand ausstehend]**: Das Ereignis befindet sich in der Warteschlange, wurde einer Nachrichtenvorlage zugeordnet und wird vom Versand verarbeitet.
   * **[!UICONTROL Gesendet]**: Dieser Status wird aus den Versandlogs übernommen. Er bedeutet, dass die Nachricht gesendet wurde.
   * **[!UICONTROL Vom Versand ignoriert]**: Der Versand konnte nicht erfolgen, z. B. aufgrund einer Quarantäne (Status wird den Versandlogs entnommen).
   * **[!UICONTROL Versandfehler]**: Der Versand ist fehlgeschlagen (Status wird den Versandlogs entnommen).
   * **[!UICONTROL Ereignis wurde nicht berücksichtigt]**: Das Ereignis konnte keiner Nachrichtenvorlage zugeordnet werden. Das Ereignis wird nicht erneut verarbeitet.
