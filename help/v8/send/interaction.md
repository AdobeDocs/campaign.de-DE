---
product: Adobe Campaign
title: Kampagneninteraktion - Angebotsverwaltung
description: Erste Schritte mit dem Angebotsmanagement
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 13%

---

# Angebote in Interaction{#interaction-and-offer-management}

Campaign verfügt über ein Modul **Interaction** , mit dem Sie in Echtzeit auf Interaktionen mit einem bestimmten Kontakt (einem Kunden oder einer Zielgruppe) reagieren können, indem Sie ihm ein oder mehrere angepasste Angebote unterbreiten. Dies können beispielsweise einfache Kommunikationsnachrichten, Sonderangebote für ein oder mehrere Produkte oder Dienste sein.

Sie können einen Angebotskatalog erstellen, der Ihre ausgehenden Kanäle (E-Mail, Briefpost, SMS) anspricht, um das beste Angebot auszuwählen, das einem Kontakt in einem bestimmten Kontext gesendet werden soll. Die beste Angebotsauswahl für einen Empfänger basiert auf **Eignungsregeln**. Die Auswahl eines Angebots aus einem Satz relevanter Angebote wird mithilfe von Prioritätsregeln bestimmt. Die Regeln zur Angebotsunterbreitung berücksichtigen den Verlauf des Kontakts und tragen dazu bei, dass der Kontakt nicht mehrmals dasselbe Angebot erhält.

Neben der Verwaltung des Angebotskatalogs bietet Interaction die Möglichkeit, Eignungsregeln und ihnen zugeordnete Anwendungsthemen zu definieren. Der Inhalt der Angebote kann je nach Kanal mithilfe der verschiedenen Darstellungen personalisiert werden. Das Simulationsmodul erlaubt es Ihnen zudem, vor Unterbreitung eines Angebots seine voraussichtliche Wirkung einzuschätzen.

## Erste Schritte mit Angeboten

Die wichtigsten Schritte zum Starten sind unten aufgeführt.

### Plattform konfigurieren

Stellen Sie vor dem Start als Campaign **Administrator** sicher, dass Sie die folgenden Aufgaben in Design-Umgebungen ausgeführt haben:

1. Erstellen Sie Benutzerprofile. [Mehr dazu](interaction-operators.md)
1. (optional) Erstellen Sie für jede Zielgruppendimension eine Angebotsumgebung. [Mehr dazu](interaction-env.md)
1. Erstellen Sie Typologieregeln für jede Umgebung. [Mehr dazu](interaction-offer.md#offer-presentation)
1. Erstellen Sie für jede Umgebung Angebotsplatzierungen und konfigurieren Sie Rendering-Funktionen. [Erfahren Sie ](interaction-offer-spaces.md)
mehr: Wenn die Platzierung im Identifizierungsmodus von einem einheitlichen Kanal definiert wird, müssen Sie die erweiterten Parameter für diese Platzierung angeben.

### Erstellen und publizieren Sie den Angebotskatalog {#managing-the-offer-catalog-}

Als **Angebotsverantwortlicher** müssen Sie die folgenden Aufgaben ausführen:

1. Erstellen Sie Angebotskategorien in Design-Umgebungen. [Mehr dazu](interaction-offer-catalog.md#creating-offer-categories)
1. Erstellen Sie Angebote in Design-Umgebungen. [Mehr dazu](interaction-offer.md)
1. Validieren und veröffentlichen Sie Angebote auf einem oder mehreren Platzierungen, um sie in Live-Umgebungen für den Versandverantwortlichen verfügbar zu machen. [Mehr dazu](interaction-offer.md#approve-offers)

### Nutzen Sie den Angebotskatalog {#using-the-offer-catalog-}

Als **Versandverantwortlicher** müssen Sie die folgenden Aufgaben ausführen:

1. Kampagne erstellen.
1. Referenzieren Sie ein Angebot in der Kampagne oder im Versand. [Weitere Informationen](interaction-send-offers.md).


## Konzepte und Terminologie

Erfahren Sie mehr über angebotsspezifische Begriffe und entsprechende Anleitungen, bevor Sie beginnen.

* **** Die Umgebung umfasst einen Angebotskatalog und Platzierungen (Hooks). Erstellen Sie eine Umgebung mithilfe einer Zielgruppendimension.
Es gibt zwei Arten von Umgebungen:

   * **Design-Umgebung**: Angebote werden in der Design-Umgebung sowie in den Typologieregeln erstellt. Typologieregeln bestimmen, welche Angebote einer Zielperson unterbreitet werden sollen. Die Tabelle der Kontakte, die in die Angebote eingehen sollen, und die Tabelle zum Speichern aller Angebotsvorschläge werden ebenfalls in dieser Umgebung definiert. Der Knoten **[!UICONTROL Design environment]** enthält Unterordner für die Platzierung, vordefinierte Filter und Angebotskategorien. Für jede **[!UICONTROL Design-Umgebung]** gibt es eine entsprechende schreibgeschützte **[!UICONTROL Live-Umgebung]**, die aus derselben **[!UICONTROL Design-Umgebung]** generiert wird.
   * **Live-Umgebung**: Umgebung, die mit einer  **[!UICONTROL Design-]** Umgebung verknüpft ist, die schreibgeschützte Angebote enthält, deren Inhalt und Eignung in der  **[!UICONTROL Design-Umgebung]** validiert wurden. Sie werden ausgewählt, um sie in eine Nachricht einzufügen.

* Die Platzierung **Platzierung** ist ein Speicherort (Ordner), der den Speicherort definiert, an dem das Angebot angezeigt wird. Bei der Erstellung einer Platzierung können Sie den Kanal angeben, den Inhalt des Angebots mithilfe von Rendering-Funktionen erstellen, die Reihenfolge der Angebote festlegen und dessen Modus festlegen: Einzelmodus und/oder Batch-Modus (Standard). Die Platzierung bildet die Schnittstelle zwischen Kanal und Angebotsmodul.
* Der **Angebotskatalog** ist ein Satz von in Adobe Campaign definierten Angeboten, die während einer Interaktion ausgewählt werden können. Der Katalog ist hierarchisch organisiert, wobei jeder Knoten einer Kategorie entspricht.
* Eine **Kategorie** ist ein mit dem Angebotskatalog in einer Umgebung verknüpfter Ordner, der Angebote nach Art, Eignungsdatum und Anwendungsthema organisiert. Eine Kategorie kann Unterkategorien enthalten, die alle Eigenschaften der übergeordneten Kategorie übernehmen. Eignungsregeln können für eine Kategorie definiert werden, um sie für mehrere Angebote freizugeben.
* **Anwendungsthemen** sind in der Kategorie definierte Suchbegriffe, mit denen Sie Angebote bei ihrer Präsentation filtern können, indem Sie die Angebotsauswahl auf eine oder zwei Kategorien beschränken.
* **Eignungsregeln** sind Begrenzungen, die auf eine Umgebung, eine Kategorie oder ein Angebot angewendet werden, die sich auf den Gültigkeitszeitraum, die Zielgruppe und die Gewichtung beziehen. Damit können Sie sicherstellen, dass ein Angebot mit dem Zielkontakt übereinstimmt.

   Auf Umgebungsniveau enthalten die Eignungsregeln die Unterbreitungsregeln, die auf Angebote und Zielpersonen angewendet werden.

   Auf Kategorieniveau ermöglichen es die Eignungsregeln, die Gültigkeit von Kategorien zeitlich zu begrenzen sowie Anwendungsthemen und Kriterien der Zielgruppenbestimmung zu definieren. Außerdem kann den Kategorien für einen bestimmten Zeitraum ein erhöhter Gewichtsfaktor zugewiesen werden. Kategorien vereinfachen die Angebotsverwaltung, da die auf diesem Niveau erstellten Regeln automatisch auf alle enthaltenen Angebote angewendet werden.

   Auf Angebotsniveau lassen sich mithilfe der Eignungsregeln die Gültigkeit von Angeboten zeitlich begrenzen sowie Kriterien der Zielgruppenbestimmung definieren.

* Die **Arbitrage** ist die Aktion der Auswahl von Angeboten, die in einer Umgebung (förderfähige Angebote) angezeigt werden. Die Arbitrage stuft Angebote nach Priorität nach den in den Kategorien, Angeboten und Kontextangeboten definierten Kriterien ein.
* Eine **Ausgehende Interaktion** ruft die Interaktionsmodul-Engine aus einer Kontaktliste auf (für den Versand von E-Mails, Briefpost usw.). Für jeden Kontakt werden die gleichen Regeln und Prozesse angewendet. Dieser Interaktionstyp wird im Allgemeinen im Batch-Modus verarbeitet.
* Im **Batch-Modus** können Sie das beste Angebot für eine Gruppe von Kontakten auswählen. Eignungs-/Prioritätsregeln werden auf alle Kontakte der Gruppe angewendet. Dieser Modus wird im Allgemeinen für ausgehende Interaktionen verwendet.
* Im **Einzelmodus** können Sie jeweils nur einen Kontakt verarbeiten. Dieser Modus wird im Allgemeinen für Transaktionsnachrichten verwendet.
* **Geeignete** Angebote sind Angebote, die den zuvor definierten Bedingungen entsprechen und somit einer Zielgruppe auf kohärente Weise unterbreitet werden können.
* **Unterbreitungsregeln** sind Typologieregeln, auf die in der Angebotsumgebung verwiesen wird und die es ermöglichen, Angebote auszuschließen, indem der Vorschlagsverlauf berücksichtigt wird.
* **** Weichen Sie Formeln aus, die die exakte Berechnung der Relevanz eines Angebots ermöglichen, um das relevanteste Angebot auszuwählen. Die Gewichtung wird in den Angeboten definiert. Geeignete Angebote werden in absteigender Reihenfolge berücksichtigt.
* **Die Rendering-** Funktion wird in der Platzierung definiert, um die Darstellung der Angebote anhand der im Angebot definierten Attribute zu erstellen. Es gibt drei verschiedene Rendering-Funktionsmodi: HTML, XML und Text.
* **Angebotsvorschläge** sind das Ergebnis der Aktion, die darin besteht, einem Kontakt ein oder mehrere Angebote an einer bestimmten Stelle (z. B. Banner auf einer Website, E-Mail oder SMS) zu unterbreiten. Dieses Ergebnis wird in der Tabelle der Angebotsvorschläge gespeichert. Es ist jedoch nicht erforderlich, die Vorschläge zu speichern.
* **** Simulationist ein Modul, mit dem Sie die Angebotsunterbreitung vor dem tatsächlichen Versand der Angebote bei den Zielgruppenempfängern testen können.
* Die **Vorschau** des Angebots zeigt das Angebot so an, wie es im Ordner angezeigt wird. Der Zugriff erfolgt über das Fenster mit den Angebotseinstellungen oder das Kontaktprofil.
* **Vordefinierte Filter** sind Filterregeln, die Angebotsparameter (z. B. Angebotscode) berücksichtigen können. Sie können nach der Erstellung von Angeboten wiederverwendet werden.
* Eine **Angebotsdarstellung** ist eine Information, die vom Kanal zur Anzeige des Angebots verwendet wird. Die Darstellung von Angeboten kann ausgehend von der Rendering-Funktion der Platzierung erstellt werden, auf der das Angebot dargestellt oder direkt in die Benutzeroberfläche eingegeben wird (z. B. im HTML-Block). Ein Angebot kann durch Leerzeichen dargestellt werden.

