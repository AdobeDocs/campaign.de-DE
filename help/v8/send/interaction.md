---
title: Campaign Interaction-Angebotsverwaltung
description: Erste Schritte mit der Angebotsverwaltung
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4da3e69a-6230-4c94-a6f1-4e8c01e854ba
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '1225'
ht-degree: 100%

---

# Interaction und Angebotsverwaltung{#interaction-and-offer-management}

Campaign verfügt über ein Modul **Interaction**, mit dem Sie in Echtzeit auf Interaktionen mit einem bestimmten Kontakt (einem Kunden oder einer Zielgruppe) reagieren können, indem Sie ihm ein oder mehrere angepasste Angebote unterbreiten. Dies können beispielsweise einfache Kommunikationsnachrichten, Sonderangebote für ein oder mehrere Produkte oder Services sein.

Sie können einen Angebotskatalog erstellen, der mit Ihren ausgehenden Kanälen (E-Mail, Briefpost, SMS) verbunden ist, um das beste Angebot auszuwählen, das einem Kontakt in einem bestimmten Kontext gesendet werden soll. Die Auswahl des besten Angebots für einen Empfänger basiert auf **Eignungsregeln**. Die Auswahl eines Angebots aus einem Paket relevanter Angebote wird mithilfe von Prioritätsregeln bestimmt. Die Regeln zur Angebotsunterbreitung berücksichtigen den Verlauf des Kontakts und helfen zu vermeiden, dass der Kontakt nicht mehrmals dasselbe Angebot erhält.

Neben der Verwaltung des Angebotskatalogs bietet Interaction die Möglichkeit, Eignungsregeln und ihnen zugeordnete Anwendungsthemen zu definieren. Der Inhalt der Angebote kann je nach Kanal mithilfe der verschiedenen Darstellungen personalisiert werden. Das Simulationsmodul erlaubt es Ihnen zudem, vor Unterbreitung eines Angebots seine voraussichtliche Wirkung einzuschätzen.

## Erste Schritte mit Angeboten

Die wichtigsten Schritte zu Beginn sind unten aufgeführt.

### Konfigurieren der Plattform

Stellen Sie vor dem Start als Campaign-**Administrator** sicher, dass Sie die folgenden Aufgaben in Design-Umgebungen ausgeführt haben:

1. Erstellen Sie Benutzerprofile. [Weitere Informationen](interaction-operators.md)
1. (optional) Erstellen Sie für jede Zielgruppendimension eine Angebotsumgebung. [Weitere Informationen](interaction-env.md)
1. Erstellen Sie Typologieregeln für jede Umgebung. [Weitere Informationen](interaction-offer.md#offer-presentation)
1. Erstellen Sie Angebotsplatzierungen für jede Umgebung und konfigurieren Sie die Rendering-Funktionen. [Mehr dazu](interaction-offer-spaces.md)
Wenn eine Platzierung in einem Einzelmodus-Kanal als identifiziert definiert wurde, müssen ihre erweiterten Parameter angegeben werden.

### Erstellen und Veröffentlichen des Angebotskatalogs {#managing-the-offer-catalog-}

Als **Angebotsverantwortlicher** müssen Sie die folgenden Aufgaben ausführen:

1. Erstellen Sie Angebotskategorien in Design-Umgebungen. [Weitere Informationen](interaction-offer-catalog.md#creating-offer-categories)
1. Erstellen Sie Angebote in Design-Umgebungen. [Weitere Informationen](interaction-offer.md)
1. Validieren und veröffentlichen Sie Angebote in einer oder mehreren Platzierungen, um sie für den Versandverantwortlichen in den Live-Umgebungen verfügbar zu machen. [Weitere Informationen](interaction-offer.md#approve-offers)

### Verwenden des Angebotskatalogs {#using-the-offer-catalog-}

Als **Versandverantwortlicher** müssen Sie die folgenden Aufgaben ausführen:

1. Erstellen Sie eine Kampagne.
1. Referenzieren Sie ein Angebot in der Kampagne oder im Versand. [Weitere Informationen](interaction-send-offers.md).


## Konzepte und Terminologie

Bevor Sie beginnen, erfahren Sie mehr über angebotsspezifische Begriffe und entsprechende Anleitungen.

* **Umgebungen** beinhalten einen Angebotskatalog und Platzierungen (Hooks). Erstellen Sie eine Umgebung mithilfe einer Zielgruppendimension.
Hier bestehen zwei Arten von Einschränkungen:

   * **Design-Umgebung**: Angebote und Typologieregeln werden in der Design-Umgebung erstellt. Typologieregeln legen fest, welche Angebote einer Zielperson unterbreitet werden sollen. Die Tabelle der Zielkontakte für die Angebote und die Tabelle zum Speichern aller Angebotsvorschläge werden ebenfalls in dieser Umgebung definiert. Der Knoten **[!UICONTROL Design-Umgebung]** enthält Platzierungs-Unterordner, vordefinierte Filter und Angebotskategorien. Für jede **[!UICONTROL Design-Umgebung]** besteht eine entsprechende schreibgeschützte **[!UICONTROL Live-Umgebung]**, die aus derselben **[!UICONTROL Design-Umgebung]** erzeugt wird.
   * **Live-Umgebung**: Eine Live-Umgebung ist mit einer **[!UICONTROL Design-Umgebung]** verknüpft und enthält schreibgeschützte Angebote, deren Inhalt und Eignung in der **[!UICONTROL Design-Umgebung]** validiert wurden. Sie werden ausgewählt, um sie in eine Nachricht einzufügen.

* Eine **Platzierung** ist ein Ort (Ordner), der festlegt, wo das Angebot angezeigt wird. Bei der Erstellung einer Platzierung können Sie den Kanal angeben, den Inhalt des Angebots mithilfe von Rendering-Funktionen erstellen, die Reihenfolge der Angebote festlegen und dessen Modus festlegen: Einzelmodus und/oder Batch-Modus (Standard). Die Platzierung bildet die Schnittstelle zwischen Kanal und Angebotsmodul.
* Der **Angebotskatalog** ist ein Satz von in Adobe Campaign definierten Angeboten, die während einer Interaktion ausgewählt werden können. Der Katalog ist hierarchisch strukturiert, wobei jeder Knoten einer Kategorie entspricht.
* Eine **Kategorie** ist ein mit dem Angebotskatalog in einer Umgebung verknüpfter Ordner, der Angebote nach Art, Gültigkeit und Anwendungsthema organisiert. Eine Kategorie kann Unterkategorien enthalten, die alle Eigenschaften der übergeordneten Kategorie übernehmen. Eignungsregeln können für eine Kategorie definiert werden, um sie für mehrere Angebote freizugeben.
* **Anwendungsthemen** Auf Kategorieebene definierte Stichwörter, die es ermöglichen, Angebote bei ihrer Unterbreitung zu filtern. Die Angebotsauswahl kann auf eine oder mehrere Kategorien begrenzt werden.
* **Eignungsregeln** sind Einschränkungen, die auf eine Umgebung, eine Kategorie oder ein Angebot angewendet werden und sich auf den Gültigkeitszeitraum, die Zielgruppe und die Gewichtung beziehen. Auf diese Weise können Sie sicherstellen, dass ein Angebot auf den Zielkontakt abgestimmt ist.

   Auf Umgebungsniveau enthalten die Eignungsregeln die Unterbreitungsregeln, die auf Angebote und Zielpersonen angewendet werden.

   Auf Kategorieniveau ermöglichen es die Eignungsregeln, die Gültigkeit von Kategorien zeitlich zu begrenzen sowie Anwendungsthemen und Kriterien der Zielgruppenbestimmung zu definieren. Außerdem kann den Kategorien für einen bestimmten Zeitraum ein erhöhter Gewichtsfaktor zugewiesen werden. Kategorien vereinfachen die Angebotsverwaltung, da die auf diesem Niveau erstellten Regeln automatisch auf alle enthaltenen Angebote angewendet werden.

   Auf Angebotsniveau lassen sich mithilfe der Eignungsregeln die Gültigkeit von Angeboten zeitlich begrenzen sowie Kriterien der Zielgruppenbestimmung definieren.

* Die **Schlichtung** ist die Aktion der Auswahl von Angeboten, die in einer Umgebung (geeignete Angebote) angezeigt werden. Die Schlichtung ordnet Angebote nach ihrer Priorität entsprechend den Kriterien, die in Kategorien, Angeboten und Kontextangeboten definiert wurden.
* Eine **Ausgehende Interaktion** ruft das Interaktionsmodul von einer Kontaktliste auf (für den Versand von E-Mails, Briefpost usw.). Auf jeden Kontakt werden die gleichen Regeln und Prozesse angewendet. Dieser Interaktionstyp wird im Allgemeinen im Batch-Modus verarbeitet.
* Im **Batch-Modus** können Sie das beste Angebot für eine Gruppe von Kontakten auswählen. Eignungs-/Prioritätsregeln werden auf alle Kontakte der Gruppe angewendet. Dieser Modus wird im Allgemeinen für ausgehende Interaktionen verwendet.
* Im **Einzelmodus** können Sie jeweils nur einen Kontakt verarbeiten. Dieser Modus wird im Allgemeinen für Transaktionsnachrichten verwendet.
* **Geeignete Angebote** sind Angebote, die bestimmten, zuvor definierten Bedingungen entsprechen und somit einer Zielgruppe auf mit ihrem Markenerlebnis kohärente Weise unterbreitet werden können.
* **Unterbreitungsregeln** sind Typologieregeln, die auf Basis der einem Kontakt bereits vorgeschlagenen Angebote bestimmte Angebote von der Unterbreitung ausschließen.
* **Gewichtungsformeln** sind Formeln, die die exakte Berechnung der Relevanz eines Angebots ermöglichen, um das Angebot mit der höchsten Relevanz auszuwählen. Die Gewichtung wird in den Angeboten definiert. Geeignete Angebote werden in absteigender Reihenfolge der Gewichtung berücksichtigt.
* **Rendering-Funktionen** werden in der Platzierung definiert, um die Darstellung der Angebote anhand der im Angebot definierten Attribute zu erstellen. Es bestehen drei verschiedene Rendering-Funktionsmodi: HTML, XML und Text.
* **Angebotsvorschläge** sind das Ergebnis der Aktion, die einem Kontakt ein oder mehrere Angebote an einer bestimmten Stelle (z. B. Banner auf einer Website, E-Mail oder SMS) unterbreitet. Dieses Ergebnis wird in der Tabelle der Angebotsvorschläge gespeichert. Das Speichern der Vorschläge ist jedoch nicht obligatorisch.
* **Simulation** ist ein Modul, das es ermöglicht, die Angebotsunterbreitung vor dem tatsächlichen Versenden an Zielpersonen zu evaluieren.
* Die **Vorschau** des Angebots zeigt das Angebot so an, wie es im Ordner dargestellt wird. Der Zugriff ist über das Fenster mit den Angebotseinstellungen oder das Kontaktprofil möglich.
* **Vordefinierte Filter** sind Filterregeln, die Angebotsparameter (z. B. einen Angebots-Code) berücksichtigen können. Sie können nach der Erstellung von Angeboten wiederverwendet werden.
* Eine **Angebotsdarstellung** ist eine Information, die vom Kanal zur Anzeige des Angebots verwendet wird. Die Angebotsdarstellung kann ausgehend von der Rendering-Funktion der Platzierung erstellt werden, auf der das Angebot dargestellt wird, oder direkt in die Benutzeroberfläche eingegeben werden (z. B. im HTML-Block). Ein Angebot kann durch eine Platzierung dargestellt werden.
