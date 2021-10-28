---
product: campaign
title: Angebote für anonyme Profile unterbreiten (eingehende Interaktion)
description: Erfahren Sie, wie Sie anonymen Profilen Angebote unterbreiten.
source-git-commit: c19336c84114a0c81563c4d5ae760330d3b284cb
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 68%

---

# Anonyme Interaktionen{#anonymous-interactions}

## Umgebung für anonyme Interaktionen {#environment-for-anonymous-interactions}

Standardmäßig wird Campaign **Interaction** Das -Modul verfügt über eine vorkonfigurierte Umgebung, um die integrierte Empfängertabelle (identifizierte Angebote) auszuwählen. Wenn Sie beispielsweise eine andere Tabelle, eine Besuchertabelle für anonyme Angebote oder eine benutzerdefinierte Empfängertabelle als Ziel auswählen möchten, müssen Sie den Assistenten für das Zielgruppen-Mapping verwenden, um die Umgebung zu erstellen. [Weitere Informationen zu Umgebungen](interaction-env.md).

Bei der Erstellung einer anonymen Umgebung mithilfe des Assistenten ist im Tab **[!UICONTROL Allgemein]** das Feld **[!UICONTROL Für anonyme eingehende Interaktionen reservierte Umgebung]** bereits angekreuzt.

Die **[!UICONTROL Zielgruppendimension]** wird vorausgefüllt und verweist standardmäßig auf die Besuchertabelle.

Auch das Feld **[!UICONTROL Besucherordner]** enthält bereits den Ordner **[!UICONTROL Besucher]**. Dieses Feld dient der Angabe des Speicherorts der Besucherprofile.

![](assets/anonymous_environment_option.png)

>[!NOTE]
>
>Wenn Sie verschiedene Besuchertypen unterscheiden möchten, beispielsweise im Fall von anonymen Angeboten verschiedener Marken, müssen Sie für jede Marke eine Umgebung und einen zugeordneten **[!UICONTROL Besucher]**-Ordner erstellen.

## Angebotskataloge für anonyme Interaktionen {#offer-catalog-for-anonymous-interactions}

Wie bei ausgehenden spielt der Angebotskatalog auch bei eingehenden Interaktionen eine zentrale Rolle. Er enthält alle nach Kategorien geordneten Angebote.

Um Kategorien und Bereiche zu erstellen, gehen Sie genauso vor wie bei identifizierten Besuchern. Siehe [Angebotskategorie erstellen](interaction-offer-catalog.md#creating-offer-categories) und [Angebotsumgebungen](interaction-env.md#creating-an-offer-environment)).

## Anonyme Besucher {#anonymous-visitors}

Anonyme Besucher können beim Webseitenaufruf einem Identifizierungsversuch durch Cookies unterzogen werden. Diese s. g. implizite Erkennung beruht auf dem Navigationsverlauf des Besuchers.

In diesem Schritt werden die von den Cookies abgerufenen Daten mit denen in Ihrer Datenbank verglichen. In einigen Fällen werden Besucher erkannt (sie werden dann implizit identifiziert), in anderen Fällen werden sie nicht erkannt (und bleiben daher anonym).

Kreuzen Sie in der Platzierung das Feld **[!UICONTROL Person implizit über den Navigationsverlauf identifizieren]** an, wenn Sie diese Möglichkeit nutzen wollen.

![](assets/identification_anonymous_visitors.png)

## Umgang mit anonymen, nicht identifizierten Besuchern {#processing-unidentified-anonymous-visitors}

Wenn ein Besucher nicht identifiziert werden konnte, können seine Daten in einer bestimmten Platzierung gespeichert werden. Auf diese Weise können ihm spezifische Angebote unterbreitet werden, die speziell für diesen Besuchertyp definierten Typologieregeln entsprechen.

Für nicht identifizierte Kontakte oder solche, die zwar implizit identifiziert werden können, denen Sie aber keine für bekannte Kontakte erstellten Angebote unterbreiten möchten, haben Sie die Möglichkeit, in eine anonyme Umgebung wechseln.

Kreuzen Sie hierfür das Feld **[!UICONTROL Zu einer anonymen Platzierung wechseln, wenn keine Zielperson identifiziert wurde]** an und geben Sie im Feld **[!UICONTROL Zugeordnete anonyme Platzierung]** die den nicht identifizierten Besuchern vorbehaltene Umgebung an.

![](assets/anonymous_to_anonymous_environment.png)
