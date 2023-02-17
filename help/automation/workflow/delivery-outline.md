---
product: campaign
title: Versandentwurf
description: Erfahren Sie mehr über die Workflow-Aktivität "Versandentwurf".
feature: Workflows, Targeting Activity
exl-id: 3c06b329-b2d8-4ac8-ab9b-3ab3e525d109
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: ht
source-wordcount: '249'
ht-degree: 100%

---

# Versandentwurf{#delivery-outline}

Die Aktivität **Versandentwurf** ermöglicht die Verwendung von Entwürfen in Kampagnen-Workflows. Der Versandentwurf ist zuvor in der Kampagne zu konfigurieren.

Wählen Sie zur Konfiguration der Aktivität den gewünschten Versandentwurf aus und geben Sie das geplante Kontaktdatum an. Es besteht die Möglichkeit, Filterregeln zu definieren, indem Sie Typologien und Typologieregeln hinzufügen.

## Anwendungsbeispiel: Einfügung eines Angebots mithilfe eines Versandentwurfs {#example--inserting-an-offer-via-a-delivery-outline}

Die in Kampagnen-Workflows zur Verfügung stehende Aktivität **Versandentwurf** erlaubt es, Angebote zu unterbreiten, die in einem Versandentwurf der aktuellen Kampagne referenziert wurden.

>[!NOTE]
>
>Für das vorliegende Anwendungsbeispiel benötigen Sie das **Interaction**-Package.

1. Platzieren Sie hierfür im Workflow die Versandentwurfsaktivität vor einer Versandaktivität.
1. Geben Sie in der Versandentwurfsaktivität den gewünschten Entwurf an.
1. Füllen Sie die verfügbaren Felder Ihrem Versand entsprechend aus.
1. Sie haben zwei Möglichkeiten:

   * Versand mit Abfrage an das Angebotsmodul: Kreuzen Sie in diesem Fall die Option **[!UICONTROL Anzahl der ausgewählten Vorschläge begrenzen]** an. Konfigurieren Sie die Platzierung und die Anzahl an zu unterbreitenden Angeboten.

      Gewichtung und Eignungsregeln der Angebote werden vom Angebotsmodul berücksichtigt.

   * Versand ohne Abfrage an das Angebotsmodul: Alle im Versandentwurf enthaltenen Angebote werden unterbreitet.

   Die Vorschau berücksichtigt die im Versand konfigurierte Anzahl an Angeboten. Bei Ausführung des Workflows hingegen wird die im Versandentwurf konfigurierte Anzahl verwendet.

   ![](assets/int_compo_offre_wf1.png)
