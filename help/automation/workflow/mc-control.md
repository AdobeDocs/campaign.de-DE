---
product: campaign
title: Message Center (Kontrolle)
description: Message Center (Kontrolle)
feature: Workflows
role: User
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 100%

---


# Message Center (Kontrolle){#message-center-control}

Der folgende Workflow ist so geplant, dass er stündlich ausgeführt wird. Er wird standardmäßig mit dem Modul **Message Center – Kontrolle** installiert.


<table> 
 <tbody> 
  <tr> 
   <td> <strong>Titel</strong><br /> </td> 
   <td> <strong>Interner Name</strong><br /> </td> 
   <td> <strong>Beschreibung</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Message Center &lt;external_account_name&gt;<br /> </td> 
   <td> mcSynch_&lt;external_account_name&gt;<br /> </td> 
   <td> Dieser Workflow:<br /> 
    <ul> 
     <li> <p>Ruft die Liste der durch die Aktion(en) verarbeiteten Ereignisse ab.</p> </li> 
     <li> <p>Wird mit der NmsBroadLogMsg-Tabelle synchronisiert, um die Qualifizierung der Versandnachrichten abzurufen.</p> </li> 
     <li> <p>Ruft Ereignis-Versandlogs ab, sobald die Synchronisation mit der NmsBroadLogMsg-Tabelle abgeschlossen ist.</p> </li> 
     <li> <p>Wird mit der NmsTrackingUrl-Tabelle synchronisiert, um das Tracking für die Versand-URLs abzurufen.</p> </li> 
     <li> <p>Ruft Ereignis-Verfolgungs-URLs ab, sobald die Synchronisation mit der NmsTrackingUrl-Tabelle abgeschlossen ist.</p> </li> 
     <li> <p>Ruft alle drei Stunden die E-Mail-Adressen ab, die infolge eines Versands neu in Quarantäne gekommen sind.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

