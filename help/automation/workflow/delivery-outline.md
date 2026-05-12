---
product: campaign
title: Versandentwurf
description: Erfahren Sie mehr über die Workflow-Aktivität "Versandentwurf".
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 3c06b329-b2d8-4ac8-ab9b-3ab3e525d109
TQID: https://experienceleague.adobe.com/-uyRqPAXzP-l05tmEfq4ZcJizCiGpTfY0qu-6tQ8cU0
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 249
ht-degree: 52%

---

# Versandentwurf{#delivery-outline}

Mit **Versandentwurf** können Sie einen Versandentwurf in einem Kampagnen-Workflow verwenden. Der Versandentwurf muss zuvor in der Kampagne erstellt worden sein.

Zur Konfiguration der Aktivität wählen Sie einfach den gewünschten Versandentwurf sowie das geplante Kontaktdatum aus. Sie können Filterregeln hinzufügen, indem Sie Typologien oder Typologieregeln hinzufügen.

## Anwendungsbeispiel: Einfügung eines Angebots mithilfe eines Versandentwurfs {#example--inserting-an-offer-via-a-delivery-outline}

Die in Kampagnen-Workflows zur Verfügung stehende Aktivität **Versandentwurf** erlaubt es, Angebote zu unterbreiten, die in einem Versandentwurf der aktuellen Kampagne referenziert wurden.

>[!NOTE]
>
>Für das vorliegende Anwendungsbeispiel benötigen Sie das **Interaction**-Package.

1. Platzieren Sie hierfür im Workflow die Versandentwurfsaktivität vor einer Versandaktivität.
1. Geben Sie in der Versandentwurfsaktivität den gewünschten Entwurf an.
1. Füllen Sie die verfügbaren Felder Ihrem Versand entsprechend aus.
1. Sie haben zwei Möglichkeiten:

   * Wenn das Angebotsmodul aufgerufen werden soll, aktivieren Sie das Kontrollkästchen **[!UICONTROL Anzahl der ausgewählten Vorschläge]**. Geben Sie die Platzierung und die Anzahl der Vorschläge an, die im Versand unterbreitet werden sollen.

     Gewichtung und Eignungsregeln der Angebote werden vom Angebotsmodul berücksichtigt.

   * Versand ohne Abfrage an das Angebotsmodul: Alle im Versandentwurf enthaltenen Angebote werden unterbreitet.

   Die Vorschau berücksichtigt die Anzahl der im Versand angegebenen Angebote. Beim Ausführen eines Workflows wird die im Versandentwurf angegebene Zahl berücksichtigt.

   ![](assets/int_compo_offre_wf1.png)
