---
product: campaign
title: Filtern doppelter Empfänger
description: Erfahren Sie, wie Sie doppelte Empfänger filtern können
feature: Workflows
role: User
exl-id: cfa1f45c-e1ac-4055-996c-6e8d041889bb
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: ht
source-wordcount: '156'
ht-degree: 100%

---

# Filtern doppelter Empfänger {#filtering-duplicated-recipients}



In diesem Beispiel werden wir Empfänger filtern, die doppelt oder öfter in einem Versand vorkommen, um duplizierte Profile festzustellen.

Gehen Sie wie folgt vor:

1. Ziehen Sie eine **[!UICONTROL Abfrage]** in den Workflow-Arbeitsbereich und öffnen Sie sie.
1. Wählen Sie **[!UICONTROL Abfrage bearbeiten]** aus und wählen Sie für die Zielgruppen- und Filterdimension die Option **[!UICONTROL Empfänger]** aus.

   ![](assets/query_recipients_1.png)

1. Definieren Sie die folgende Filterbedingung für die Empfänger im Versandlog. Wählen Sie in der Spalte **Ausdruck** die Option **Versandlog eines Empfängers (Broadlog)** und in der Spalte **Operator** die Option **wie** aus.

   ![](assets/query_recipients_2.png)

1. Definieren Sie die folgende Filterbedingung für Ihren Versand. Wählen Sie in der Ausdrucksspalte die Option **[!UICONTROL Interner Name]** und in der Operator-Spalte die Option **[!UICONTROL gleich]**.
1. Fügen Sie in der Wertspalte den internen Namen des Versands ein.

   ![](assets/query_recipients_3.png)

1. Wiederholen Sie diesen Vorgang mit einem **[!UICONTROL UND]**-Operator für andere Sendungen.

   ![](assets/query_recipients_4.png)

Ihre ausgehende Transition enthält die duplizierten Empfänger der Sendungen.
