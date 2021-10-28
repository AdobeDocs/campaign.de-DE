---
product: campaign
title: Angebote unterbreiten (eingehende Interaktion)
description: Erfahren Sie, wie Sie das beste Angebot mithilfe des Campaign Interaction-Moduls unterbreiten.
source-git-commit: 9712d72dd08291673490b42967fd469353fca67a
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 20%

---

# Angebot unterbreiten{#interaction-present-offers}

Angebote können in verschiedenen Platzierungen mit [Ein- oder Ausgehender Kanal](interaction-architecture.md#interaction-types). In diesem Kapitel werden einige spezifische Funktionen für eingehende Kanäle beschrieben.

![](assets/inbound-interactions.png)

Damit Angebote vom Angebotsmodul ausgewählt werden können, müssen sie validiert und in einer Live-Umgebung verfügbar sein.

![](../assets/do-not-localize/book.png) Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=de#approving-offer-content)

Im Kontext eines eingehenden Kontakts kann der Benutzer, der die Seite durchsucht, von der Website identifiziert werden oder nicht. Das Angebotsmodul bietet verschiedene Angebote für identifizierte Profile und für anonyme Profile an.

Bevor Sie Angebote in einem eingehenden Kanal unterbreiten können, müssen Sie den Aufruf des Angebotsmoduls konfigurieren, in dem die Angebote unterbreitet werden sollen. In den meisten Fällen handelt es sich bei einer eingehenden Interaktion um die Webseite.

>[!NOTE]
>
>Bei eingehenden Interaktionen muss das Angebotsmodul dahingehend konfiguriert werden, ein oder mehrere Angebote zu unterbreiten und zu aktualisieren.
>
>Außerdem müssen Sie für Ihre Platzierungen den Einzelmodus zulassen. Weitere Informationen hierzu finden Sie auf [dieser Seite](interaction-offer-spaces.md).
