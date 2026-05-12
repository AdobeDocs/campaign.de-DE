---
product: campaign
title: Angebote pro Segment
description: Angebote pro Segment
feature: Workflows, Targeting Activity, Interaction
role: User
version: Campaign v8, Campaign Classic v7
exl-id: e2216dfd-1ef8-4747-b716-576fd6498fa6
TQID: https://experienceleague.adobe.com/rcPG-VXEtEll374z7DpQTQOcZ3MXauiZwPTwByTUSEk
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 163
ht-degree: 80%

---

# Angebote pro Segment{#offers-by-cell}



Mithilfe der Aktivität **[!UICONTROL Angebote pro Segment]** lässt sich die eingehende Population (die beispielsweise aus einer Abfrage hervorgeht) in mehrere Zielgruppen aufspalten, um so je Segment spezifische Angebote zu unterbreiten.

Diese Aktivität kann nur mit **Interaktion** verwendet werden. Weitere Informationen zur Angebotsverwaltung finden Sie in [diesem Abschnitt](../../v8/interaction/interaction.md).

Gehen Sie dazu wie folgt vor:

1. Platzieren Sie im Anschluss an die Abfrage der Zielpopulation eine Aktivität **[!UICONTROL Angebote pro Segment]** und öffnen Sie sie zur weiteren Bearbeitung.
1. Wählen Sie auf der Registerkarte **[!UICONTROL Allgemein]** die Platzierung, über die Sie Angebote unterbreiten möchten.
1. Definieren Sie nun auf der Registerkarte **[!UICONTROL Segmente]** über die Schaltfläche **[!UICONTROL Hinzufügen]** die verschiedenen Segmente:

   * Konfigurieren Sie anhand der verfügbaren Filter und Begrenzungen die Population des Segments.
   * Wählen Sie als Nächstes das Angebot aus, das Sie der Untergruppe unterbreiten möchten. Die verfügbaren Angebote sind diejenigen, die für die Platzierung infrage kommen, die im vorherigen Schritt ausgewählt wurde.

     ![](assets/int_offer_per_cell1.png)

1. Konfigurieren Sie dann eine Versandaktivität, die dem von Ihnen gewählten Kanal entspricht. Siehe [Kanalübergreifender Versand](cross-channel-deliveries.md).
