---
product: campaign
title: Filtern doppelter Empfänger
description: Erfahren Sie, wie Sie doppelte Empfänger filtern können
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: cfa1f45c-e1ac-4055-996c-6e8d041889bb
TQID: 'https://experienceleague.adobe.com/jwnm0saAGOFD4FjCniKHBm6xDd8H2QggSy3UvrMAb-E'
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
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 72%
---
# Filtern doppelter Empfänger {#filtering-duplicated-recipients}



In diesem Beispiel werden wir Empfänger filtern, die doppelt oder öfter in einem Versand vorkommen, um duplizierte Profile festzustellen.

Gehen Sie wie folgt vor:

1. Ziehen Sie eine **[!UICONTROL Abfrage]** in den Workflow-Arbeitsbereich und öffnen Sie sie.
1. Wählen Sie **[!UICONTROL Abfrage bearbeiten]** aus und wählen Sie für die Zielgruppen- und Filterdimension die Option **[!UICONTROL Empfänger]** aus.

   ![Schritt Zielgruppendimension und Filterdimension der Abfrageaktivität mit ausgewählten Empfängern, hervorgehobene Filterbedingungen.](assets/query_recipients_1.png)

1. Definieren Sie die folgende Filterbedingung für die Empfänger im Versandlog. Wählen Sie in der Spalte **Ausdruck** die Option **Versandlog eines Empfängers (Broadlog)** und in der Spalte **Operator** die Option **wie** aus.

   ![Filterschritt mit der Bedingung Empfänger-Versandlogs (broadLog) und vorhandener Operator wie z. B.](assets/query_recipients_2.png)

1. Definieren Sie die folgende Filterbedingung für Ihren Versand. Wählen Sie in der Ausdrucksspalte die Option **[!UICONTROL Interner Name]** und in der Operator-Spalte die Option **[!UICONTROL gleich]**.
1. Fügen Sie in der Wertspalte den internen Namen des Versands ein.

   ![Filterbedingung für den internen Namen des Versands, gleich dem Wert summer_delivery_sales, unter vorhanden sein, z. B..](assets/query_recipients_3.png)

1. Wiederholen Sie diesen Vorgang mit einem **[!UICONTROL UND]**-Operator für andere Sendungen.

   ![Zwei sind vorhanden, z. B. Bedingungen, die durch Und verbunden sind und auf summer_delivery_sales und summer_delivery_new_collection abzielen.](assets/query_recipients_4.png)

Ihre ausgehende Transition enthält die duplizierten Empfänger der Sendungen.
