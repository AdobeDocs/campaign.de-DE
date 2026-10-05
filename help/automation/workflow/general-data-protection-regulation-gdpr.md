---
product: campaign
title: Datenschutzbestimmungs-Workflows
description: Erfahren Sie mehr über die Workflows für Datenschutzbestimmungen.
role: User
version: Campaign v8, Campaign Classic v7
feature: Workflows, Privacy
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: a7760dfc-5c44-4d77-bb68-c50b1e265c93
    internal-label: Security and privacy
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ac9c0a9c-8a76-4419-bd64-9c34c5782666
    internal-label: Privacy
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 100%
---

# Datenschutzbestimmung{#general-data-protection-regulation-gdpr}


Die unten aufgeführten Workflows werden standardmäßig mit dem Modul **Datenschutzbestimmung** installiert. Weiterführende Informationen zu diesem Modul finden Sie in [diesem Artikel](https://helpx.adobe.com/de/campaign/kb/acc-privacy.html).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Titel</strong><br /> </td> 
   <td> <strong>Interner Name</strong><br /> </td> 
   <td> <strong>Beschreibung</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Datenschutzanfragen erfassen</span> <br /> </td> 
   <td> <span class="uicontrol">collectPrivacyRequests</span> <br /> </td> 
   <td> Mit diesem Workflow werden die in Adobe Campaign gespeicherten Empfängerdaten abgerufen und im Datenschutzanfrage-Fenster für den Download bereitgestellt.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Datenschutz-Anfragedaten löschen</span> <br /> </td> 
   <td> <span class="uicontrol">deletePrivacyRequestsData</span> <br /> </td> 
   <td> Mit diesem Workflow werden die in Adobe Campaign gespeicherten Empfängerdaten gelöscht.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Bereinigung der Datenschutzanfrage</span> <br /> </td> 
   <td> <span class="uicontrol">cleanupPrivacyRequests</span> <br /> </td> 
   <td> Mit diesem Workflow werden Zugriffsanfragen gelöscht, die älter als 90 Tage sind.<br /> </td> 
  </tr> 
 </tbody> 
</table>

