---
product: campaign
title: Schema-Bearbeitung
description: Erfahren Sie mehr über die Workflow-Aktivität "Schema-Bearbeitung".
feature: Workflows, Targeting Activity
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 16fb1aa5-cf99-4461-a1a4-7a68d97e2a74
TQID: 'https://experienceleague.adobe.com/uHsIfXEPlhLjwbGdRaUagbAhFhZb5JFxGurpSH4c0fI'
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
  - id: ff84ab2f-a7c2-4ced-a3c8-5113f4348d99
    internal-label: Targeting Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 77%
---
# Schema-Bearbeitung{#edit-schema}



Daten können mit der Aktivität **[!UICONTROL Schema bearbeiten]** im Workflow umgewandelt, normalisiert und bei Bedarf angereichert werden. Dies wird in der Regel zum Normalisieren der Datenstruktur gemacht: Sie können die Ausgabespalten umbenennen oder ihren Inhalt verändern, indem Sie beispielsweise die Durchschnittswerte eines Felds oder Aggregats berechnen.

Diese Aktivität verändert nicht die Daten der Arbeitstabelle, sondern nur ihr Schema, d. h. die logische Darstellung der Daten.

![Bearbeiten der Schemaaktivität mit Ausgabespalten und -ausdrücken, einschließlich einer Spalte für den Bestelldurchschnitt, berechnet mit Durchschn](assets/wf_manipulation_box.png)

Im Tab **[!UICONTROL Relationen]** können Sie Beziehungen zu anderen Arbeitstabellen herstellen.

![Registerkarte „Verknüpfungen“ von Schema bearbeiten mit dem Dialogfeld „Verknüpfungsdefinition“, das das Zielschema und die Join-Bedingungen anzeigt](assets/wf_manipulation_box_link_tab.png)

Im unteren Bereich werden die Joinbedingungen definiert, d. h. die Kriterien festgelegt, die die Abstimmung zwischen den Tabellendaten ermöglichen.
