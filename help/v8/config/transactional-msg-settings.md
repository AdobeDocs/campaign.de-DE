---
title: Einstellungen für Transaktionsnachrichten in Campaign
description: Einstellungen für Transaktionsnachrichten in Campaign
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 74%

---

# Einstellungen für Transaktionsnachrichten

![](../assets/do-not-localize/speech.png) Als Managed Cloud Services-Anwender können Sie [Adobe kontaktieren](../start/campaign-faq.md#support), um Campaign-Transaktionsnachrichten in Ihrer Umgebung zu installieren und zu konfigurieren.

![](../assets/do-not-localize/glass.png) In [diesem Abschnitt](../send/transactional.md) sind die Funktionen für Transaktionsnachrichten beschrieben.

![](../assets/do-not-localize/glass.png)[ Diese Seite](../architecture/architecture.md#transac-msg-archi) hilft Ihnen, die Architektur der Transaktionsnachrichten zu verstehen.

## Berechtigungen definieren

Um neue Benutzer für in Adobe Cloud gehostete Message Center-Ausführungsinstanzen zu erstellen, kontaktieren Sie die Adobe-Kundenunterstützung. Message Center-Benutzer benötigen für den Zugriff auf die Ordner &quot;Echtzeit-Ereignisse&quot; (nmsRtEvent) spezifische Berechtigungen.

## Schemaerweiterungen

Alle Erweiterungen von Schemas, die von **technischen Workflows des Message Center-Moduls** in Kontroll- oder Ausführungsinstanzen verwendet werden, müssen in den anderen vom Transaktionsnachrichten-Modul von Adobe Campaign verwendeten Instanzen dupliziert werden.

![](../assets/do-not-localize/book.png) In der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html?lang=de#technical-workflows) erfahren Sie mehr über die technischen Workflows von Message Center.

## Push-Benachrichtigungen zu Transaktionen versenden

In Kombination mit dem Mobile-App-Kanal-Modul können Sie über Benachrichtigungen Transaktionsnachrichten an Mobilgeräte senden.

![](../assets/do-not-localize/book.png) Der Mobile-App-Kanal wird im Abschnitt [diesem Abschnitt](../send/push.md).

Um Push-Benachrichtigungen zu Transaktionen zu senden, müssen Sie die folgenden Konfigurationen vornehmen:

1. Installieren Sie das Package **Mobile App Channel** in den Kontroll- und Ausführungsinstanzen.

   >[!CAUTION]
   >
   >Prüfen Sie Ihre Lizenzvereinbarung, bevor Sie ein neues integriertes Campaign-Paket installieren.

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

## Schwellenwerte überwachen {#monitor-thresholds}

Sie können die Warnschwellen (orange) und die Warnschwellen (rot) der Indikatoren konfigurieren, die im **Dienstqualität** und **Verarbeitungszeit** Berichte.

Gehen Sie dazu wie folgt vor:

1. Öffnen Sie den Softwareverteilungs-Assistenten im **Ausführungsinstanz** und navigieren Sie zum **[!UICONTROL Message Center]** Seite.
1. Verwenden Sie die Pfeile, um die Schwellenwerte zu ändern.


## Ereignisse bereinigen {#purge-events}

Sie können die Einstellungen des Softwareverteilungs-Assistenten anpassen, um zu konfigurieren, wie lange die Daten in der Datenbank gespeichert werden sollen.

Die Bereinigung der Ereignisse wird automatisch von der **Datenbankbereinigung** technischer Arbeitsablauf. Dieser Workflow löscht die in den Ausführungsinstanzen empfangenen und gespeicherten Ereignisse sowie die in einer Kontrollinstanz archivierten Ereignisse.

Verwenden Sie die Pfeile, um die Bereinigungsparameter für die **Veranstaltungen** (in einer Ausführungsinstanz) und **Ereignisse mit Verlauf** (in einer Kontrollinstanz).


## Technische Workflows {#technical-workflows}

Vor der Bereitstellung von Transaktionsnachrichten-Vorlagen müssen Sie sicherstellen, dass die technischen Workflows in Ihren Kontroll- und Ausführungsinstanzen gestartet wurden.

Diese Workflows können Sie dann über den Ordner **Administration > Betreibung > Message Center** aufrufen.

### Workflows der Kontrollinstanz {#control-instance-workflows}

In der Kontrollinstanz müssen Sie für jeden **[!UICONTROL Message Center Ausführungsinstanz]** externes Konto. Klicken Sie auf die Schaltfläche **[!UICONTROL Archivierungs-Workflow erstellen]**, um den Workflow zu erstellen und zu starten.

### Workflows der Ausführungsinstanz {#execution-instance-workflows}

In der/den Ausführungsinstanz(en) müssen die folgenden technischen Workflows gestartet werden:

* **[!UICONTROL Verarbeitung der Batch-Ereignisse]** (interner Name **[!UICONTROL batchEventsProcessing]**): teilt die Batch-Ereignisse einer Warteschlange zu, bis sie einer Nachrichtenvorlage zugeordnet werden.
* **[!UICONTROL Verarbeitung der Echtzeit-Ereignisse]** (interner Name **[!UICONTROL rtEventsProcessing]**): teilt die Echtzeit-Ereignisse einer Warteschlange zu, bis sie einer Nachrichtenvorlage zugeordnet werden.
* **[!UICONTROL Update des Ereignisstatus]** (interner Name **[!UICONTROL updateEventStatus]**): ordnet jedem Ereignis einen Status zu.

   Mögliche Ereignisstatus sind:

   * **[!UICONTROL Ausstehend]**: Das Ereignis befindet sich in der Warteschlange und wurde noch keiner Nachrichtenvorlage zugeteilt.
   * **[!UICONTROL Versand ausstehend]**: Das Ereignis befindet sich in der Warteschlange, wurde einer Nachrichtenvorlage zugeordnet und wird vom Versand verarbeitet.
   * **[!UICONTROL Gesendet]**: Dieser Status wird aus den Versandlogs übernommen. Er bedeutet, dass die Nachricht gesendet wurde.
   * **[!UICONTROL Vom Versand ignoriert]**: Der Versand konnte nicht erfolgen, z. B. aufgrund einer Quarantäne (Status wird den Versandlogs entnommen).
   * **[!UICONTROL Versandfehler]**: Der Versand ist fehlgeschlagen (Status wird den Versandlogs entnommen).
   * **[!UICONTROL Ereignis wurde nicht berücksichtigt]**: Das Ereignis konnte keiner Vorlage zugeordnet werden. Das Ereignis wird nicht erneut verarbeitet.
