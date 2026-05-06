---
product: campaign
title: Message Center (Ausführung)
description: Message Center (Ausführung)
feature: Workflows
role: User
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 56%

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
   <td> Mit diesem Workflow können Sie Ereignissen einen Status zuweisen. Folgende Ereignisstatus stehen zur Verfügung:<br /> 
    <ul> 
     <li> <p><strong>Ausstehend</strong>: Das Ereignis befindet sich in einer Warteschlange. Es wurde noch keine Nachrichtenvorlage damit verknüpft.</p> </li> 
     <li> <p><strong>Versand ausstehend</strong>: Das Ereignis befindet sich in der Warteschlange. Ihm wurde eine Nachrichtenvorlage zugeordnet und die Versandverarbeitung ist in Gang.</p> </li> 
     <li> <p><strong>Gesendet</strong>: Dieser Status wird aus den Versandlogs kopiert. Dies bedeutet, dass der Versand durchgeführt wurde.</p> </li> 
     <li> <p><strong>Vom Versand ignoriert</strong> Dieser Status wird aus den Versandlogs kopiert. Dies bedeutet, dass der Versand ignoriert wurde.</p> </li> 
     <li> <p><strong>Versandfehler</strong> Dieser Status wird aus den Versandlogs übernommen. Dies bedeutet, dass der Versand fehlgeschlagen ist.</p> </li> 
     <li> <p><strong>Ereignis wurde nicht </strong>: Das Ereignis konnte keiner Nachrichtenvorlage zugeordnet werden. Das Ereignis wird nicht erneut verarbeitet.</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Verarbeitung der Batch-Ereignisse</span> <br /> </td> 
   <td> <span class="uicontrol">batchEventsProcessing</span> <br /> </td> 
   <td> Dieser Workflow teilt die Batch-Ereignisse in eine Warteschlange ein, bevor ihnen eine Nachrichtenvorlage zugeordnet wird. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Verarbeitung der Echtzeit-Ereignisse</span> <br /> </td> 
   <td> <span class="uicontrol">rtEventsProcessing</span> <br /> </td> 
   <td> Dieser Workflow teilt die Echtzeit-Ereignisse in eine Warteschlange ein, bevor ihnen eine Nachrichtenvorlage zugeordnet wird. <br /> </td> 
  </tr> 
 </tbody> 
</table>

