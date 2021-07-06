---
product: Adobe Campaign
title: Campaign Interaction-Benutzer
description: Erstellen von Angebotsverwaltungs-Benutzern
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Live-/Design-Umgebung {#live-design-environments}

Interaction arbeitet mit zwei Angebotsumgebungstypen:

* **[!UICONTROL Design-Umgebungen]**, in denen Angebote erstellt und geändert werden können. Vor Validierung der Angebote oder etwaiger Änderungen stehen sie nicht zur Unterbreitung zur Verfügung.
* **[!UICONTROL Live-Umgebungen]**, in denen die validierten Angebote zur Unterbreitung zur Verfügung stehen. Die hier enthaltenen Angebote sind schreibgeschützt.

![](assets/offer_environments_overview_001.png)

Jeder **[!UICONTROL Design-Umgebung]** entspricht eine **[!UICONTROL Live-Umgebung]**. Nach Erstellung eines Angebots unterlaufen sein Inhalt und die konfigurierten Eignungsregeln einen Validierungszyklus, nach dessen erfolgreichem Abschluss das Angebot automatisch für die **[!UICONTROL Live-Umgebung]** freigegeben wird. Nun kann es in Sendungen verwendet werden.

Standardmäßig verfügt Campaign über eine **[!UICONTROL Design]**-Umgebung und eine **[!UICONTROL Live]**-Umgebung, die mit der Design-Umgebung verknüpft ist. Beide Umgebungen sind für die [integrierte Empfängertabelle](../dev/datamodel.md#ootb-profiles) vorkonfiguriert.

>[!NOTE]
>
>Um die Empfängertabelle auszuwählen, müssen Sie den Zielgruppen-Mapping-Assistenten zur Erstellung der Umgebungen verwenden. [Weitere Informationen](#creating-an-offer-environment).

![](assets/offer_environments_overview_002.png)

Versandverantwortliche können nur die **[!UICONTROL Live]**-Umgebung anzeigen und Angebote bereitstellen. Angebotsverantwortliche können die **[!UICONTROL Design]**-Umgebung anzeigen und nutzen und die **[!UICONTROL Live]**-Umgebung anzeigen. [Weitere Informationen](interaction-operators.md)

## Erstellen einer Angebotsumgebung {#creating-an-offer-environment}

Campaign verfügt standardmäßig über eine integrierte Umgebung, in der die Empfängertabelle (identifizierte Angebote) ausgewählt werden kann. Gehen Sie wie folgt vor, um eine andere Tabelle auszuwählen:

1. Navigieren Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Kampagnenverwaltung]** > **[!UICONTROL Zielgruppen-Mappings]**, klicken Sie mit der rechten Maustaste auf das gewünschte Zielgruppen-Mapping und wählen Sie **[!UICONTROL Aktionen]** > **[!UICONTROL Optionen der Zielgruppendimension ändern]** aus.

   ![](assets/offer_env_anonymous_001.png)

1. Klicken Sie auf **[!UICONTROL Weiter]**, wählen Sie die Option **[!UICONTROL Speicherschema für Vorschläge erzeugen]** und klicken Sie auf **[!UICONTROL Speichern]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >Falls die Option bereits ausgewählt war, muss sie zunächst deaktiviert und dann erneut aktiviert werden.

1. Adobe Campaign erstellt nun die beiden dem zuvor ausgewählten Zielgruppen-Mapping entsprechenden Umgebungen (**[!UICONTROL Design-Umgebung]** und **[!UICONTROL Live-Umgebung]**). Beide Umgebungen sind mit den gewünschten Zielgruppeninformationen vorkonfiguriert.
