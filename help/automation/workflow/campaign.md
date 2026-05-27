---
product: campaign
title: Kampagne
description: Campaign
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
topic-tags: technical-workflows
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 100%

---


# Campaign{#campaign}

Die folgenden Workflows werden standardmäßig mit dem Modul **Kampagne** installiert.

>[!CAUTION]
>
>Diese Workflows MÜSSEN gestartet werden, damit die auf Kampagnenebene notwendigen Prozesse ausgeführt werden können.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Titel</strong><br /> </td> 
   <td> <strong>Interner Name</strong><br /> </td> 
   <td> <strong>Beschreibung</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Kostenberechnung</span> <br /> </td> 
   <td> <span class="uicontrol">budgetMgt</span> <br /> </td> 
   <td> Dieser Workflow berechnet Ausgaben- und Kostenzeilen für Pläne, Programme, Kampagnen, Sendungen und Aufgaben.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Lager: Ergänzungen und Meldebestände</span> <br /> </td> 
   <td> <span class="uicontrol">stockMgt</span> <br /> </td> 
   <td> Dieser Workflow startet die Berechnung der Lagerbestände in den Bestellzeilen und verwaltet Warnschwellen.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Bearbeitungsvorgänge bezüglich Kampagnensendungen</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryMgt</span> <br /> </td> 
   <td> Dieser Workflow startet den Versand der validierten Sendungen und die Anschlussvorgänge des Dienstleisters bei externem Versand. Außerdem werden Validierungsbenachrichtigungen und Erinnerungen gesendet.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Kampagnenvorgänge</span> <br /> </td> 
   <td> <span class="uicontrol">operationMgt</span> <br /> </td> 
   <td> Verwaltet Vorgänge in Marketing-Kampagnen (Zielgruppenbestimmung, Dateiextraktion etc.). Erstellt darüber hinaus Workflows für wiederkehrende und periodische Kampagnen.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Bearbeitungsvorgänge bezüglich der Dienstleister</span> <br /> </td> 
   <td> <span class="uicontrol">supplierMgt</span> <br /> </td> 
   <td> Dieser Workflow startet nach erfolgter Versandvalidierung Dienstleistervorgänge (E-Mail an den Router und Anschlussverarbeitung). <br /> </td> 
  </tr> 
 </tbody> 
</table>

