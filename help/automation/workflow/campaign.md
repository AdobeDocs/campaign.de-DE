---
product: campaign
title: Kampagne
description: Campaign
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
topic-tags: technical-workflows
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
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

