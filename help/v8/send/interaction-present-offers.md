---
product: campaign
title: Unterbreiten eines Angebots (eingehende Interaktion)
description: Hier erfahren Sie, wie Sie das beste Angebot mithilfe des Campaign Interaction-Moduls unterbreiten.
source-git-commit: 9712d72dd08291673490b42967fd469353fca67a
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 100%

---

# Unterbreiten des besten Angebots{#interaction-present-offers}

Angebote können in verschiedenen Platzierungen über [eingehende oder ausgehende Kanäle](interaction-architecture.md#interaction-types) unterbreitet werden. Dieses Kapitel behandelt einige Besonderheiten von eingehenden Kanälen.

![](assets/inbound-interactions.png)

Damit Angebote vom Angebotsmodul ausgewählt werden können, müssen sie zuvor genehmigt worden sein und in einer Live-Umgebung verfügbar sein.

![](../assets/do-not-localize/book.png) Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=de#approving-offer-content)

Im Kontext eines eingehenden Kontakts kann der Benutzer, der die Seite durchsucht, von der Website identifiziert werden oder nicht. Das Angebotsmodul bietet für identifizierte Profile und für anonyme Profile verschiedene Angebote an.

Um in eingehenden Kanälen Angebote vorschlagen zu können, muss die Abfrage an das Angebotsmodul an der Stelle konfiguriert werden, an der die Angebote unterbreitet werden sollen. Der gängigste Fall einer eingehenden Interaktion ist der Besuch einer Web-Seite.

>[!NOTE]
>
>Im Falle von eingehenden Interaktionen muss das Angebotsmodul dahingehend konfiguriert werden, ein oder mehrere Angebote zu aktualisieren und vorzuschlagen.
>
>Außerdem müssen Sie für Ihre Platzierungen den Einzelmodus zulassen. Weitere Informationen hierzu finden Sie auf [dieser Seite](interaction-offer-spaces.md).
