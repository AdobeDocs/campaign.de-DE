---
title: Campaign Interaction-Angebotskatalog
description: Erfahren Sie, wie Sie einen Angebotskatalog erstellen
feature: Interaction, Offers
role: Developer
level: Beginner
exl-id: 911096e2-0307-46a8-873c-ee2248b8e3e8
TQID: 'https://experienceleague.adobe.com/mEif2EAPpb8XtjHY-eWxEfnRS-zdx5ezYI1Td9JPbG0'
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
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 68%
---
# Erstellen eines Angebotskatalogs

Als **Angebotsverantwortlicher** sind Sie für die Erstellung des Angebotskatalogs zuständig.

Ein Angebotskatalog ist einer bereits existierenden Umgebung zugeordnet. Angebote in diesem Katalog können nur Platzierungen derselben Umgebung zugeordnet werden.

Vor der Angebotserstellung ist die übergeordnete [Umgebung](interaction-env.md) zu konfigurieren. In der Umgebung werden die für alle enthaltenen, nach Kategorie geordneten Angebote identischen Merkmale (Eignung, Zielgruppe, Unterbreitungsregeln) bestimmt. Sie enthält außerdem die Liste der Platzierungen.

## Angebotskategorien erstellen{#creating-offer-categories}

Angebote sind in Kategorien/Unterkategorien unterteilt. Kategorien werden in der **[!UICONTROL Design]**-Umgebung erstellt und automatisch in der **[!UICONTROL Live]**-Umgebung bereitgestellt, sobald die darin enthaltenen Angebote validiert wurden. Die **[!UICONTROL Design]**-Umgebung enthält eine Standardkategorie für den Empfang aller Angebote. Unterkategorien können erstellt werden, um den Katalogangeboten eine Hierarchie hinzuzufügen.

Für jede Kategorie können Sie eine **Gültigkeit** definieren. Dies ist der Zeitraum, in dem die in der Kategorie enthaltenen Angebote ihrer Zielgruppe unterbreitet werden können. Sie können außerdem die Gewichtung einer Kategorie anpassen, um der Angebotsunterbreitung Priorität einzuräumen.

Gehen Sie wie folgt vor, um eine neue Kategorie zu erstellen:

1. Navigieren Sie zum Ordner **[!UICONTROL Angebotskatalog]**.

   ![Explorer-Baumstruktur mit dem Angebotskatalogordner, der unter Angebote - Design und Umgebung - Empfänger ausgewählt ist](assets/offer_cat_create_001.png)

1. Klicken Sie mit der rechten Maustaste und wählen Sie im Kontextmenü die Option **[!UICONTROL Neuen Angebotskategorie-Ordner erstellen]** aus.

   ![Kontextmenü im Angebotskatalog mit hervorgehobener Option „Neuen Angebotskategorieordner erstellen“](assets/offer_cat_create_002.png)

1. Benennen Sie die Kategorie. Der Titel kann später auch über den **[!UICONTROL Allgemein]**-Tab der Kategorie geändert werden.

   ![Neuer Kategorieordner mit dem Namen Neobank - Persönliches Banking in der Angebotskatalogstruktur, bereit zum Umbenennen](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >Wiederholen Sie diese Schritte gegebenenfalls, bis Sie die gewünschte Anzahl an Kategorien erstellt haben.

   Nun haben Sie je nach Bedarf die Möglichkeit,

   * im Tab **[!UICONTROL Eignung]** Daten für die Verwendung zuzuweisen.

     ![Registerkarte Eignung mit den Feldern Startdatum und Enddatum, öffnen Sie einen Kalender und klicken Sie auf den Link Abfrage bearbeiten für Zielfilter](assets/offer_cat_create_004.png)

   * **[!UICONTROL Bearbeiten Sie die Abfrage]**, um Filter auf die Angebots-Zielgruppe anzuwenden.

   * Eine Zusammenfassung der Eignungsregeln. Um sie anzuzeigen, klicken Sie auf den Link **[!UICONTROL Zeitplan und Eignungsregeln des Angebots]**.

## Hinzufügen einer Ersatzkategorie

Um sicherzustellen, dass alle Empfänger einen Angebotsvorschlag erhalten, können in den Empfehlungen systematisch eine oder mehrere Angebotskategorien hinzugefügt werden.

Diese Fallback-Angebote müssen eine niedrige Gewichtung (aber nicht null) aufweisen, sodass sie nur berücksichtigt werden, wenn kein Angebot mit höherer Gewichtung infrage kommt.

Darüber hinaus darf auf diese Angebote keine Unterbreitungsregel angewendet werden, um sicherzustellen, dass sie immer in die Empfehlungen aufgenommen werden. Wenn also für einen Vorschlag kein Angebot mit höherer Gewichtung verfügbar ist, erhält der Empfänger mindestens ein Angebot aus dieser Kategorie.

Gehen Sie wie folgt vor, um eine Ersatzkategorie in die Empfehlungen aufzunehmen:

1. Navigieren Sie zu Ihrem Angebotskatalog.
1. Klicken Sie auf der Registerkarte **[!UICONTROL Eignung]** auf **[!UICONTROL Diese Kategorie immer in die Empfehlungen einschließen]**.
1. Klicken Sie auf **[!UICONTROL Speichern]**.

   ![Registerkarte „Kategorieeignung“ mit „Diese Kategorie immer in die ausgewählten Empfehlungen einschließen“](assets/offer_cat_default_001.png)
