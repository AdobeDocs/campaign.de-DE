---
product: campaign
title: Mid-Sourcing-Plattform
description: Mid-Sourcing-Plattform
feature: Workflows
role: User
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
source-git-commit: 8a7bf8408d15e0bd9e1c3e72f7846bf9a79c6885
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 41%
---

# Mid-Sourcing-Plattform{#mid-sourcing-platform}



Der unten beschriebene Workflow wird standardmäßig mit dem Modul **Mid-Sourcing-Plattform** installiert.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Titel</strong><br /> </td> 
   <td> <strong>Interner Name</strong><br /> </td> 
   <td> <strong>Beschreibung</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Versandindikatoren</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryIndicators</span> <br /> </td> 
   <td> Aktualisiert Trackingindikatoren von Sendungen. Dieser Workflow wird standardmäßig stündlich gestartet.<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Die Protokollaufbewahrungsdauer auf dem Mid-Sourcing-Server muss länger sein als die Gültigkeitsdauer des Versands plus der Wert **indicatorsDuration**. Andernfalls verringern sich die Versandindikatoren, wenn alte Protokolle gelöscht werden und die niedrigeren Werte mit der Marketing-Instanz synchronisiert werden. Legen Sie beispielsweise mit einem Gültigkeitszeitraum von 5 Tagen und einer **indicatorDuration** von 30 Tagen den Aufbewahrungszeitraum auf mindestens 36 Tage fest.
