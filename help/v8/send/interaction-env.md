---
product: Adobe Campaign
title: Campaign Interaction-Benutzer
description: Erstellen von Angebotsmanagement-Operatoren
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 37%

---

# Live- und Design-Umgebungen{#live-design-environments}

Interaction arbeitet mit zwei Angebotsumgebungstypen:

* **[!UICONTROL Design-Umgebungen]**, in denen Angebote erstellt und geändert werden können. Vor Validierung der Angebote oder etwaiger Änderungen stehen sie nicht zur Unterbreitung zur Verfügung.
* **[!UICONTROL Live-Umgebungen]**, in denen die validierten Angebote zur Unterbreitung zur Verfügung stehen. Die hier enthaltenen Angebote sind schreibgeschützt.

![](assets/offer_environments_overview_001.png)

Jeder **[!UICONTROL Design-Umgebung]** entspricht eine **[!UICONTROL Live-Umgebung]**. Nach Erstellung eines Angebots unterlaufen sein Inhalt und die konfigurierten Eignungsregeln einen Validierungszyklus, nach dessen erfolgreichem Abschluss das Angebot automatisch für die **[!UICONTROL Live-Umgebung]** freigegeben wird. Nun kann es in Sendungen verwendet werden.

Standardmäßig ist Campaign mit einer **[!UICONTROL Design]**-Umgebung und einer **[!UICONTROL Live]**-Umgebung ausgestattet, die damit verknüpft ist. Beide Umgebungen sind so vorkonfiguriert, dass sie auf die [integrierte Empfängertabelle](../dev/datamodel.md#ootb-profiles) abzielen.

>[!NOTE]
>
>Um die Empfängertabelle auszuwählen, müssen Sie den Assistenten zur Zielgruppenzuordnung verwenden, um die Umgebungen zu erstellen. [Weitere Informationen](#creating-an-offer-environment).

![](assets/offer_environments_overview_002.png)

Versandverantwortliche können nur die Umgebung **[!UICONTROL Live]** anzeigen und Angebote nutzen, um sie bereitzustellen. Angebotsverantwortliche Benutzer können die Umgebung **[!UICONTROL Design]** anzeigen und die Umgebung **[!UICONTROL Live]** anzeigen. [Mehr dazu](interaction-operators.md)

## Erstellen einer Angebotsumgebung {#creating-an-offer-environment}

Campaign verfügt standardmäßig über eine integrierte Umgebung, in der die Empfängertabelle (identifizierte Angebote) ausgewählt werden kann. Gehen Sie wie folgt vor, um eine andere Tabelle auszuwählen:

1. Navigieren Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Kampagnenverwaltung]** > **[!UICONTROL Zielgruppen-Mappings]**, klicken Sie mit der rechten Maustaste auf das gewünschte Zielgruppen-Mapping und wählen Sie **[!UICONTROL Aktionen]** > **[!UICONTROL Ändern Sie die Optionen der Zielgruppendimension]** aus.

   ![](assets/offer_env_anonymous_001.png)

1. Klicken Sie auf **[!UICONTROL Weiter]**, wählen Sie die Option **[!UICONTROL Speicherschema für Vorschläge erstellen]** und klicken Sie auf **[!UICONTROL Speichern]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >Wenn die Option bereits aktiviert ist, deaktivieren Sie sie und aktivieren Sie sie erneut.

1. Adobe Campaign erstellt zwei Umgebungen - **[!UICONTROL Design]** und **[!UICONTROL Live]** - mit Targeting-Informationen aus dem zuvor aktivierten Zielgruppen-Mapping. Die Umgebung ist mit den Targeting-Informationen vorkonfiguriert.
