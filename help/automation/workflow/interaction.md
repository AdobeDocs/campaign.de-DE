---
product: campaign
title: Interaction
description: Interaction
feature: Workflows, Interaction
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---


# Interaction{#interaction}



Die folgenden Workflows werden standardmäßig mit dem **Angebotsmodul (Interaction)** installiert.

Weitere Informationen hierzu finden Sie je nach Campaign-Version in den folgenden Abschnitten: 

!

![](assets/do-not-localize/v8.png)[  Dokumentation zu Campaign v8](https://experienceleague.adobe.com/docs/campaign/campaign-v8/send/interaction/interaction.html?lang=de)


<table> 
 <tbody> 
  <tr> 
   <td> <strong>Titel</strong><br /> </td> 
   <td> <strong>Interner Name</strong><br /> </td> 
   <td> <strong>Beschreibung</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Berechnung des full-Aggregats (cube propositionrcp)</span> <br /> </td> 
   <td> <span class="uicontrol">agg_nmspropositionrcp_full</span> <br /> </td> 
   <td> Dieser Workflow aktualisiert das <strong>full</strong>-Aggregat des <strong>Angebotsvorschlag</strong>-Cubes. Es wird standardmäßig täglich um 6 Uhr gestartet. Dieses Aggregat erfasst die folgenden Dimensionen: Kanal, Versand, Marketingangebot und Datum.<br /> Mit dem Cube <strong>Angebotsvorschlag</strong> können anschließend anhand von Angeboten Berichte erstellt werden. Weiterführende Informationen zu Cubes finden Sie hier: <br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">Vollständige Message Center-Aggregatberechnung</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> Dieser Workflow aktualisiert das <strong>vollständige</strong> Aggregat für den <strong>Message Center</strong>-Cube. Es wird standardmäßig jeden Tag um 3 Uhr morgens ausgelöst. Dieses Aggregat erfasst die folgenden Dimensionen: Kanal, Datum, Status und Ereignistyp.<br /> Der <strong>Message Center</strong>-Cube wird dann zur Erstellung von ereignisbasierten Berichten verwendet. Weitere Informationen zu Cubes finden Sie hier:<br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

