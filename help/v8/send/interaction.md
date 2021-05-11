---
solution: Campaign
product: Adobe Campaign
title: Interaktion mit Kampagnen - Angebot-Management
description: Erste Schritte mit der Angebot-Verwaltung
feature: Übersicht
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 3783cb5ed3085b988f573fbf15858377b2bb2e05
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 15%

---

# Angebote in Interaction{#interaction-and-offer-management}

Kampagne wird mit dem Modul **Interaktion** geliefert, mit dem Sie während einer Interaktion mit einem bestimmten Ansprechpartner (Kunde oder Zielgruppe) in Echtzeit reagieren können, indem Sie sie zu einem oder mehreren angepassten Angeboten machen. Dies können beispielsweise einfache Kommunikationsmeldungen, spezielle Angebot auf einem oder mehreren Produkten oder Dienste sein.

Sie können einen Angebotskatalog erstellen, der mit Ihren ausgehenden Kanälen (E-Mail, Direktnachricht, SMS) kommuniziert, um das beste Angebot auszuwählen, das Sie in einem bestimmten Kontext an einen Ansprechpartner senden können. Die beste Angebot-Auswahl für einen Empfänger basiert auf **Eignungsregeln**. Die Auswahl eines Angebots aus einem Satz relevanter Angebot wird anhand von Prioritätsregeln festgelegt. Angebot-Unterbreitungsregeln berücksichtigen den Verlauf des Kontakts und helfen zu vermeiden, dass sie das gleiche Angebot mehrere Male erhalten.

Neben der Verwaltung des Angebotskatalogs bietet Interaction die Möglichkeit, Eignungsregeln und ihnen zugeordnete Anwendungsthemen zu definieren. Der Inhalt der Angebote kann je nach Kanal mithilfe der verschiedenen Darstellungen personalisiert werden. Das Simulationsmodul erlaubt es Ihnen zudem, vor Unterbreitung eines Angebots seine voraussichtliche Wirkung einzuschätzen.

## Erste Schritte mit Angeboten

Die wichtigsten Schritte zum Beginn sind unten aufgeführt.

### Plattform konfigurieren

Bevor Sie beginnen, sollten Sie als Kampagne **Administrator** sicherstellen, dass Sie die folgenden Aufgaben in den Design-Umgebung ausgeführt haben:

1. Erstellen Sie Profil für Benutzer. [Weitere Informationen](interaction-operators.md).
1. (Optional) Erstellen Sie für jede Zielgruppendimension eine Angebot-Umgebung. [Mehr dazu](interaction-env.md)
1. Erstellen Sie Typologieregeln für jede Umgebung. [Weitere Informationen](interaction-offer.md#offer-presentation).
1. Erstellen Sie Platzierungen für jede Umgebung und konfigurieren Sie Renderfunktionen. [mehr dazu](interaction-offer-spaces.md).
Wenn eine Platzierung in einem Einzelmodus-Kanal als identifiziert definiert wurde, müssen ihre erweiterten Parameter angegeben werden.

### Angebotskatalog {#managing-the-offer-catalog-} erstellen und veröffentlichen

Als **Angebot-Manager** müssen Sie die folgenden Aufgaben ausführen:

1. Erstellen Sie Angebot-Kategorien in Design-Umgebung. [Weitere Informationen](interaction-offer-catalog.md#creating-offer-categories).
1. Erstellen Sie Angebote in Design-Umgebung. [Weitere Informationen](interaction-offer.md).
1. Genehmigen und veröffentlichen Sie Angebote an einem oder mehreren Stellen, um sie auf Live-Umgebung für den Versand-Manager verfügbar zu machen. [Weitere Informationen](interaction-offer.md#approve-offers).

### Nutzen Sie den Angebotskatalog {#using-the-offer-catalog-}

Als **Versand-Manager** müssen Sie die folgenden Aufgaben ausführen:

1. Kampagne erstellen.
1. Verweisen Sie auf ein Angebot in der Kampagne oder im Versand. [Weitere Informationen](interaction-send-offers.md).


## Konzepte und Terminologie

Entdecken Sie Angebot-spezifische Begriffe und entsprechende Anleitungen, bevor Sie beginnen.

* **Zu den** Umgebungen gehören ein Angebotskatalog und Platzierungen (Haken). Sie müssen eine Umgebung nach Zielgruppendimension erstellen.
Es gibt zwei Arten von Umgebung:

   * **Design-Umgebung**: Angebot werden in der Design-Umgebung sowie in Typologieregeln erstellt. Typologieregeln bestimmen die Angebot, die einer Zielperson präsentiert (oder nicht) werden sollen. Die Tabelle der Personen, die von den Angeboten als Ziel ausgewählt werden, und die Tabelle zum Speichern aller Angebotsvorschlag werden ebenfalls in dieser Umgebung definiert. Der Knoten **[!UICONTROL Design-Umgebung]** enthält Unterordner für Platzierungen, vordefinierte Filter und Angebot-Kategorien. Für jede **[!UICONTROL Design-Umgebung]** gibt es eine entsprechende schreibgeschützte **[!UICONTROL Live-Umgebung]**, die aus derselben **[!UICONTROL Design-Umgebung]** generiert wurde.
   * **Live-Umgebung**: Umgebung, die mit einer  **[!UICONTROL Design-]** Umgebung verknüpft ist und schreibgeschützte Angebot enthält, deren Inhalt und Berechtigung über die  **[!UICONTROL Design-Umgebung]** genehmigt wurden. Sie sind auszuwählen, damit sie in eine Nachricht eingefügt werden können.

* Die **Platzierung** ist ein Speicherort (Ordner), der den Speicherort des Angebots definiert. Beim Erstellen einer Platzierung können Sie den Kanal angeben, den Inhalt des Angebots mithilfe von Renderfunktionen erstellen, die Reihenfolge der Angebot und den zugehörigen Modus angeben: Einheitenmodus und/oder Stapelmodus (Standard). Die Platzierung ist die Schnittstelle zwischen dem Kanal und der Angebot-Engine.
* Der **Angebotskatalog** ist ein Satz von Angeboten, die in Adobe Campaign definiert sind und die während einer Interaktion ausgewählt werden können. Der Katalog ist hierarchisch mit jedem Knoten organisiert, der einer Kategorie entspricht.
* Eine **Kategorie** ist ein mit dem Angebotskatalog verknüpfter Ordner in einer Umgebung, die Angebot nach Art, Berechtigungsdatum und Anwendungsdesign organisiert. Eine Kategorie kann untergeordnete Kategorien enthalten, die alle Eigenschaften der übergeordneten Kategorie übernehmen. Eignungsregeln können für eine Kategorie definiert werden, um sie für mehrere Angebot freizugeben.
* **Anwendungsthemen** sind in der Kategorie definierte Suchbegriffe, mit denen Sie Angebot filtern können, wenn sie angezeigt werden, indem Sie die Auswahl der Angebot auf eine oder zwei Kategorien beschränken.
* **Förderfähigkeitsregeln** sind Beschränkungen, die auf eine Umgebung, Kategorie oder ein Angebot angewendet werden, die sich auf die Gültigkeitsdauer, Zielgruppe und Gewichtung beziehen. Damit können Sie sicherstellen, dass ein Angebot mit dem Targeting-Kontakt übereinstimmt.

   Auf Umgebungsniveau enthalten die Eignungsregeln die Unterbreitungsregeln, die auf Angebote und Zielpersonen angewendet werden.

   Auf Kategorieniveau ermöglichen es die Eignungsregeln, die Gültigkeit von Kategorien zeitlich zu begrenzen sowie Anwendungsthemen und Kriterien der Zielgruppenbestimmung zu definieren. Außerdem kann den Kategorien für einen bestimmten Zeitraum ein erhöhter Gewichtsfaktor zugewiesen werden. Kategorien vereinfachen die Angebotsverwaltung, da die auf diesem Niveau erstellten Regeln automatisch auf alle enthaltenen Angebote angewendet werden.

   Auf Angebotsniveau lassen sich mithilfe der Eignungsregeln die Gültigkeit von Angeboten zeitlich begrenzen sowie Kriterien der Zielgruppenbestimmung definieren.

* Die Aktion **Arbitrage** dient zur Auswahl der Angebot, die auf einer Umgebung angezeigt werden (förderfähige Angebot). Die Schiedsgerichtsbarkeit ordnet die Angebote nach Priorität nach den in den Kategorien, Angeboten und Angebot festgelegten Kriterien an.
* Eine **Ausgehende Interaktion** ruft die Interaktions-Engine von einer Kontakt-Liste auf (zum Senden von E-Mails, Direktversand usw.). Für jeden Kontakt gelten dieselben Regeln und Prozesse. Diese Art der Interaktion wird im Allgemeinen im Stapelmodus verarbeitet.
* Im Stapelmodus **können Sie das beste Angebot für eine Kontaktsammlung auswählen.** Auf alle Kontakte der Gruppe werden Regeln für die Förderfähigkeit/Priorisierung angewendet. Dieser Modus wird im Allgemeinen für ausgehende Interaktionen verwendet.
* Mit dem Einheitsmodus **können Sie einen einzelnen Kontakt gleichzeitig verarbeiten.** Dieser Modus wird im Allgemeinen für Transaktionsnachrichten verwendet.
* **Förderfähige** Angebote sind Angebot, die die im Vorfeld definierten Einschränkungen erfüllen und einer Zielgruppe konsistent angeboten werden können.
* **Präsentationsregeln** sind Typologieregeln, auf die in der Angebot-Umgebung verwiesen wird. Diese ermöglichen es Ihnen, einige Angebot auszuschließen, indem Sie den Angebotsverlauf berücksichtigen.
* **** Weichtare-Formeln, mit denen Sie die Relevanz eines Angebots genau berechnen können, um das relevanteste Angebot auszuwählen. Gewichtungen werden in den Angeboten definiert. Förderfähige Angebot werden in absteigender Reihenfolge der Gewichtung berücksichtigt.
* **Die** Renderfunktion ist in der Platzierung definiert, um ihre Angebotsdarstellung basierend auf den im Angebot definierten Attributen zu erstellen. Es gibt drei verschiedene Renderfunktionsmodi: HTML, XML und Text.
* **Angebot** Propositionation ist das Ergebnis der Aktion, die darin besteht, einem Kontakt an einem bestimmten Ort ein oder mehrere Angebot zu präsentieren (z.B. Banner auf einer Website, E-Mail oder SMS). Dieses Ergebnis wird in der Tabelle &quot;Angebotsvorschlag&quot;gespeichert. Es ist jedoch nicht zwingend erforderlich, die Vorschläge zu speichern.
* **** Simulationist ein Modul, mit dem Sie die Präsentation des Angebots auf den zielgerichteten Empfängern testen können, bevor Sie die Angebot senden.
* Die **Vorschau** des Angebots zeigt das Angebot so an, wie es in seinem Ordner angezeigt wird. Sie können über das Fenster &quot;Angebot-Einstellungen&quot;oder das Profil &quot;Kontakt&quot;darauf zugreifen.
* **Vordefinierte** Filterregeln können Angebot-Parameter (z. B. einen Angebot-Code) berücksichtigen. Sie können nach dem Erstellen von Angeboten wiederverwendet werden.
* Eine **Angebotsdarstellung** ist eine vom Kanal zum Anzeigen des Angebots verwendete Information. Angebotsdarstellung kann aus der Renderfunktion des Bereichs erstellt werden, auf dem das Angebot dargestellt oder direkt in die Schnittstelle eingegeben wird (z. B. im HTML-Block). Ein Angebot kann durch Leerzeichen dargestellt werden.

