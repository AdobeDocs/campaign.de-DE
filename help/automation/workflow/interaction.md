---
product: campaign
title: Interaction
description: Interaction
feature: Workflows, Interaction
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: ht
source-wordcount: '135'
ht-degree: 100%

---


# Interaction{#interaction}

Die folgenden Workflows werden standardmäßig mit dem **Angebotsmodul (Interaction)** installiert.

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
   <td> Dieser Workflow aktualisiert das <strong>full</strong>-Aggregat des <strong>Angebotsvorschlag</strong>-Cubes. Es wird standardmäßig täglich um 6 Uhr gestartet. Dieses Aggregat erfasst die folgenden Dimensionen: Kanal, Versand, Marketingangebot und Datum.<br /> Der Cube <strong>Angebotsvorschlag</strong> wird dann zur Erstellung von angebotsbasierten Berichten verwendet.<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">Vollständige Message Center-Aggregatberechnung</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> Dieser Workflow aktualisiert das <strong>vollständige</strong> Aggregat für den <strong>Message Center</strong>-Cube. Er wird standardmäßig jeden Tag um 3 Uhr morgens ausgelöst. Dieses Aggregat erfasst die folgenden Dimensionen: Kanal, Datum, Status und Ereignistyp.<br /> Der <strong>Message Center</strong>-Cube wird dann zur Erstellung von ereignisbasierten Berichten verwendet. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

Erfahren Sie mehr über Cubes und Aggregate in [diesem Abschnitt](../../v8/reporting/gs-cubes.md).

