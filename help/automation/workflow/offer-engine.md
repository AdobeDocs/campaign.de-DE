---
product: campaign
title: Angebotsmodul
description: Angebotsmodul
feature: Workflows, Interaction
role: User, Admin
exl-id: d77858e1-3cd5-4372-b1bc-ea4b518c958d
source-git-commit: 28742db06b9ca78a4e952fcb0e066aa5ec344416
workflow-type: ht
source-wordcount: '140'
ht-degree: 100%

---

# Angebotsmodul{#offer-engine}

Die Aktivität **[!UICONTROL Angebotsmodul]** ermöglicht den Aufruf des Interaction-Angebotsmoduls im Vorfeld eines Versands.

Das Prinzip dieser Aktivität entspricht dem der Anreicherung. Auch hier werden die Daten der Eingangspopulation mit einem vom Modul berechneten Angebot angereichert, bevor die eigentliche Versandaktivität startet.

![](assets/int_offerengine_activity2.png)

Erstellen Sie zunächst Ihre Zielbestimmungsabfrage (siehe diesen [Abschnitt](query.md)). Gehen Sie dann wie folgt vor:

1. Platzieren Sie im Anschluss an die Abfrage ein **[!UICONTROL Angebotsmodul]** und öffnen Sie es zur weiteren Bearbeitung.
1. Konfigurieren Sie die verschiedenen Parameter der Abfrage des Angebotsmoduls (Platzierung, Kategorie oder Themen, Kontaktdatum, Anzahl beizubehaltender Angebote). Das Modul berechnet automatisch die den Parametern entsprechenden Angebote.

   >[!CAUTION]
   >
   >Wenn Sie diese Aktivität nutzen, werden nur die im Versand verwendeten Vorschläge gespeichert.

   ![](assets/int_offerengine_activity1.png)

1. Konfigurieren Sie dann eine Versandaktivität, die dem von Ihnen gewählten Kanal entspricht. Siehe [Kanalübergreifender Versand](cross-channel-deliveries.md).
