---
product: campaign
title: Message Center (Ausführung)
description: Message Center (Ausführung)
feature: Workflows
role: User
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 100%

---


# Message Center (Ausführung){#message-center-execution}

Die folgenden Workflows werden standardmäßig mit dem Add-on **Message Center – Ausführung** installiert.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Titel</strong><br /> </td> 
   <td> <strong>Interner Name</strong><br /> </td> 
   <td> <strong>Beschreibung</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Update des Ereignisstatus</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> Weist Ereignissen einen Status zu. Folgende Status sind möglich:<br /> 
    <ul> 
     <li> <p><strong>Ausstehend</strong>: Das Ereignis befindet sich in der Warteschlange. Ihm wurde noch keine Nachrichtenvorlage zugeordnet.</p> </li> 
     <li> <p><strong>Versand ausstehend</strong>: Das Ereignis befindet sich in der Warteschlange. Ihm wurde eine Nachrichtenvorlage zugeordnet und die Versandverarbeitung ist in Gang.</p> </li> 
     <li> <p><strong>Gesendet</strong>: Dieser Status wird aus den Versandlogs übernommen. Er bedeutet, dass die Nachricht gesendet wurde.</p> </li> 
     <li> <p><strong>Vom Versand ignoriert</strong>: Dieser Status wird aus den Versandlogs übernommen. Er bedeutet, dass der Versand ignoriert wurde.</p> </li> 
     <li> <p><strong>Versandfehler</strong>: Dieser Status wird aus den Versandlogs übernommen. Er bedeutet, dass der Versand fehlgeschlagen ist.</p> </li> 
     <li> <p><strong>Ereignis wurde nicht berücksichtigt</strong>: Dem Ereignis konnte keine Nachrichtenvorlage zugeordnet werden. Es erfolgt kein weiterer Verarbeitungsversuch.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Verarbeitung der Batch-Ereignisse</span> <br /> </td> 
   <td> <span class="uicontrol">batchEventsProcessing</span> <br /> </td> 
   <td> Teilt die Batch-Ereignisse in eine Warteschlange ein, bevor ihnen eine Nachrichtenvorlage zugeordnet wird. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Verarbeitung der Echtzeit-Ereignisse</span> <br /> </td> 
   <td> <span class="uicontrol">rtEventsProcessing</span> <br /> </td> 
   <td> Teilt die Echtzeit-Ereignisse in eine Warteschlange ein, bevor ihnen eine Nachrichtenvorlage zugeordnet wird. <br /> </td> 
  </tr> 
 </tbody> 
</table>

