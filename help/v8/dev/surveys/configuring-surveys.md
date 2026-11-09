---
product: campaign
title: Online-Umfragen konfigurieren
description: Erfahren Sie, wie Sie Online-Umfragen konfigurieren
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: 387bc362-4064-4181-9385-8e0c3423ba3e
TQID: 'https://experienceleague.adobe.com/1BTkZ--FyHkp7u0eya-lmuELDu8AMmeC96eGsonYcVM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: 71b1c383-45b9-57e0-b8cd-ea2e98a01a26
    internal-label: Surveys
subfeature_v2:
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
source-git-commit: 2ac66c0844ec361de9a1658f666c190fcfac8ffa
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 93%
---
# Online-Umfragen konfigurieren{#configuring-surveys}

>[!AVAILABILITY]
>
>Für Campaign-FFDA[Bereitstellungen sind keine Umfragen &#x200B;](../../architecture/enterprise-deployment.md).



## Eigenschaften der Umfrage {#survey-properties}

Online-Umfragen können vollständig konfiguriert und an Ihre Anforderungen angepasst werden. Die Parameter müssen im Eigenschaftenfenster eingegeben werden.

Die verfügbaren Parameter werden in [diesem Dokument](../web/defining-web-forms-properties.md) erläutert.

![](assets/s_ncs_admin_survey_properties_general.png)

## Speicherung der Umfragedaten {#survey-data-storage}

Standardmäßig werden die Felder des Webformulars in der Empfängertabelle gespeichert. Um eine andere Tabelle zu verwenden, wählen Sie sie im Feld **[!UICONTROL Dokumenttyp]** aus. Mit dem **[!UICONTROL Zoom]**-Symbol können Sie den Inhalt der ausgewählten Tabelle anzeigen.

Die nicht in den Feldern (sondern in lokalen Variablen) gespeicherten Umfrageantworten werden in der Tabelle **Umfrageantworten** gespeichert. Sie können das verwendete Schema im Feld **[!UICONTROL Bibliothek]** ändern. Dieses Feld steht nur für **Umfragen** zur Verfügung.
