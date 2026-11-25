---
title: Vordefinierte Filter für Campaign Interaction-Angebote
description: Erfahren Sie, wie Sie vordefinierte Filter erstellen
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 092262c7-768c-4e86-9b2b-c52516f6a030
TQID: 'https://experienceleague.adobe.com/XWkWbgrMASz-9FfrXC23tTwiw54oQH5U4iWM9fa2FDQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 60%
---
# Erstellen vordefinierter Filter{#creating-pre-defined-filters}

Erstellen Sie vordefinierte Filter, um Eignungsregeln für die Zielpopulation zu definieren, die bei der Erstellung von Angeboten einfach wiederverwendet werden können. Vordefinierte Filter sind für jede Umgebung spezifisch und berücksichtigen die Angebotsparameter.

>[!NOTE]
>
>Die Web-Benutzeroberfläche von Adobe Campaign bietet eine benutzerfreundliche Oberfläche, mit der Sie vordefinierte Filter mühelos verwalten und an Ihre spezifischen Anforderungen anpassen können. Sie können Filter einmal erstellen und für die zukünftige Verwendung speichern. Weitere Informationen zu vordefinierten Filtern für die Web-Benutzeroberfläche finden Sie in der [Dokumentation zur Campaign Web-Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/campaign-web/v8/start/predefined-filters){target=_blank}.


Gehen Sie wie folgt vor, um einen Filter zu erstellen:

1. Markieren Sie im Ordner **[!UICONTROL Administration]** der jeweiligen Umgebung den Knoten **[!UICONTROL Vordefinierte Angebotsfilter]**.

   ![Angebote - Design-Baumstruktur mit dem Knoten Vordefinierte Angebotsfilter unter „Administration“ &#x200B;](assets/offer_filter_create_005.png)

1. Klicken Sie auf **[!UICONTROL Neu]**.

   ![Liste der vordefinierten Angebotsfilter mit hervorgehobener Schaltfläche „Neu“ und aufgelistetem Altersfilter](assets/offer_filter_create_001.png)

1. Benennen Sie den Filter.

   ![Dialogfeld „Anwendungsfilter“ mit dem auf „E-Mail-Kanal“ gesetzten Feld „Bezeichnung“](assets/offer_filter_create_002.png)

1. Wählen Sie nun das Feld aus, auf das sich die Filterbedingung beziehen soll.

   ![Wählen Sie ein Ausdrucksdialogfeld mit dem aus den Empfängerfeldern ausgewählten E-Mail-Feld aus](assets/offer_filter_create_003.png)

1. Geben Sie den Operator und gegebenenfalls einen Wert an und speichern Sie die Abfrage.

   ![Filterbedingung im E-Mail-Ausdruck, für den der Operator auf gesetzt ist, ist nicht leer](assets/offer_filter_create_004.png)

1. Durch Klick auf die Registerkarte **[!UICONTROL Vorschau]** können Sie das Ergebnis des Filters prüfen.

   ![Registerkarte Vorschau des E-Mail-Kanal-Filters, in der die Empfänger aufgelistet sind, die dem Filter entsprechen](assets/offer_filter_create_006.png)
