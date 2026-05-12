---
product: campaign
title: Unterbreiten eines Angebots (eingehende Interaktion)
description: Hier erfahren Sie, wie Sie das beste Angebot mithilfe des Campaign Interaction-Moduls unterbreiten.
feature: Interaction, Offers
role: User, Admin
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
TQID: https://experienceleague.adobe.com/aC-hN1JwwFkuGc6ZNV0M3uHpM7LcXTHpyC9wCbxKziQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 70%

---

# Unterbreiten des besten Angebots{#interaction-present-offers}

Angebote können in verschiedenen Platzierungen über eingehende [ ausgehende Kanäle unterbreitet ](interaction-architecture.md#interaction-types). In diesem Kapitel werden einige spezifische Funktionen für eingehende Kanäle beschrieben.

![](assets/inbound-interactions.png)

Damit Angebote vom Angebotsmodul ausgewählt werden können, müssen sie zuvor genehmigt worden sein und in einer Live-Umgebung verfügbar sein.

Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=de#approving-offer-content){target="_blank"}.

Im Kontext eines eingehenden Kontakts kann der Benutzer, der die Seite durchsucht, von der Website identifiziert werden oder nicht. Das Angebotsmodul bietet für identifizierte Profile und für anonyme Profile verschiedene Angebote an.

Um Angebote auf einem eingehenden Kanal unterbreiten zu können, müssen Sie die Abfrage des Angebotsmoduls so konfigurieren, dass die Angebote unterbreitet werden sollen. In den meisten Fällen für eingehende Interaktionen ist dies die Web-Seite.

>[!NOTE]
>
>Im Falle von eingehenden Interaktionen muss das Angebotsmodul dahingehend konfiguriert werden, ein oder mehrere Angebote zu aktualisieren und vorzuschlagen.
>
>Außerdem müssen Sie für Ihre Platzierungen den Einzelmodus zulassen. Weitere Informationen hierzu finden Sie auf [dieser Seite](interaction-offer-spaces.md).
