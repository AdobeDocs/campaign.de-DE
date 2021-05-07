---
solution: Campaign
product: Adobe Campaign
title: Best Practices für Datenmodelle
description: Bewährte Verfahren zur Kampagne von Datenmodellerweiterungen
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '2713'
ht-degree: 36%

---

# Best Practices für Datenmodelle{#data-model-best-practices}

In diesem Dokument werden die wichtigsten Empfehlungen beim Entwerfen Ihres Adobe Campaign-Datenmodells erläutert.

Das Adobe Campaign-System ist sehr flexibel und kann über die ursprüngliche Implementierung hinaus erweitert werden. Obwohl die Möglichkeiten unbegrenzt sind, ist es wichtig, die richtigen Entscheidungen zu treffen und eine solide Grundlage zu schaffen, um mit der Entwicklung Ihres Datenmodells zu beginnen.

Für ein besseres Verständnis der in der Kampagne integrierten Tabellen und ihrer Interaktion lesen Sie [diesen Abschnitt](datamodel.md) .

:bulb: Lesen Sie [diesen Abschnitt](schemas.md), um mit Kampagne-Schemas zu beginnen.

:bulb: Erfahren Sie, wie Sie Erweiterungsschema konfigurieren, um das konzeptionelle Datenmodell der Adobe Campaign-Datenbank auf [dieser Seite](extend-schema.md) zu erweitern.

## Architektur von Datenmodellen {#data-model-architecture}

Adobe Campaign ist ein leistungsstarkes kanalübergreifendes System zur Kampagnenverwaltung, das es Ihnen ermöglicht, Online- und Offline-Strategien zu kombinieren, um personalisierte Kundenerlebnisse bereitzustellen.

### Kundenorientierter Ansatz {#customer-centric-approach}

Während die meisten E-Mail-Dienstleister für die Kundenkommunikation einen listenorientierten Ansatz verfolgen, setzt Adobe Campaign eine relationale Datenbank ein, um eine breitere Sicht auf die Kunden und ihre Eigenschaften zu nutzen.

Um die Tabellenbeschreibung aufzurufen, gehen Sie zu **[!UICONTROL Admin > Konfiguration > Data Schemas]**, wählen Sie eine Ressource aus der Liste und klicken Sie auf die Registerkarte **[!UICONTROL Dokumentation]**.


>[!NOTE]
>
>Adobe Campaign ermöglicht das Erstellen einer [Tabelle mit benutzerdefiniertem Empfänger](custom-recipient.md). In den meisten Fällen wird jedoch empfohlen, die integrierte [Empfänger-Tabelle](datamodel.md#ootb-profiles) zu nutzen, die bereits über vordefinierte zusätzliche Tabellen und Funktionen verfügt.

### Daten für Adobe Campaign {#data-for-campaign}

Welche Daten sollten an Adobe Campaign gesendet werden? Es ist äußerst wichtig festzustellen, welche Daten Sie für Ihre Marketingaktivitäten benötigen.

>[!NOTE]
>
>Adobe Campaign ist weder ein Data Warehouse noch ein Berichte-Tool. Versuchen Sie daher nicht, alle möglichen Kunden und die zugehörigen Informationen in Adobe Campaign zu importieren oder Daten zu importieren, die nur zum Erstellen von Berichten verwendet werden.

Wenn Sie entscheiden möchten, ob ein Attribut im Adobe Campaign benötigt wird oder nicht, fragen Sie sich, ob es unter eine dieser Kategorien fällt:

* Für die **Segmentierung** verwendetes Attribut
* Für **Datenverwaltungsprozesse** verwendetes Attribut (z. B. Aggregatberechnung)
* Für die **Personalisierung** verwendetes Attribut

Wenn ein Attribut nicht in eine dieser Kategorien fällt, benötigen Sie es wahrscheinlich nicht in Adobe Campaign.

### Auswahl der Datentypen {#data-types}

Um eine gute Architektur und Systemleistung sicherzustellen, befolgen Sie die folgenden Best Practices, wenn Sie Daten in Adobe Campaign einrichten.

* Eine große Tabelle sollte meist numerische Felder enthalten und Links zu Referenztabellen enthalten (bei der Liste von Werten).
* Mit dem Attribut **expr** können Sie ein Schema-Attribut als berechnetes Feld und nicht als physikalischen Tabellensatzwert definieren. Dadurch können Informationen in einem anderen Format (z. B. Alter und Geburtsdatum) aufgerufen werden, ohne dass beide Werte gespeichert werden müssen. Dies ist eine gute Möglichkeit, Felder nicht zu duplizieren. Die Tabelle &quot;Empfänger&quot;verwendet beispielsweise einen Ausdruck für die Domäne, der bereits im E-Mail-Feld vorhanden ist.
* Wenn die Berechnung des Ausdrucks jedoch komplex ist, wird die Verwendung des Attributs **expr** nicht empfohlen, da die Berechnung der Pausierung Auswirkungen auf die Leistung Ihrer Abfragen haben kann.
* Der Typ **XML** ist eine gute Möglichkeit, zu viele Felder zu vermeiden. Es nimmt aber auch Speicherplatz auf der Festplatte auf, da es eine CLOB-Spalte in der Datenbank verwendet. Es kann auch zu komplexen SQL-Abfragen führen und die Leistung beeinträchtigen.
* Die Länge eines Felds **string** sollte immer mit der Spalte definiert werden. Standardmäßig ist das Adobe Campaign maximal 255 Zeichen lang. Es wird jedoch empfohlen, das Feld kürzer zu halten, wenn Sie bereits wissen, dass die Feldlänge kürzer ist.
* Es ist akzeptabel, dass ein Feld in Adobe Campaign kürzer ist als im Quellsystem, wenn Sie sicher sind, dass die Länge im Quellsystem zu groß ist und nicht benötigt wird. Dies könnte eine kürzere Zeichenfolge oder kleinere Ganzzahl in Adobe Campaign bedeuten.

### Auswahl der Felder {#choice-of-fields}

Ein Feld muss in einer Tabelle gespeichert werden, wenn es einen Targeting- oder Personalisierungszweck hat. Mit anderen Worten, wenn ein Feld nicht zum Senden einer personalisierten E-Mail verwendet wird oder als Kriterium in einer Abfrage verwendet wird, nimmt es Speicherplatz auf der Festplatte in Anspruch, ist jedoch nutzlos.

Bei Hybrid- und lokalen Instanzen deckt die FDA (Federated Data Access, eine optionale Funktion, die den Zugriff auf externe Daten ermöglicht) die Notwendigkeit ab, während einer Kampagne ein Feld &quot;on-the-fly&quot;hinzuzufügen. Sie müssen nicht alles importieren, wenn Sie FDA haben. Weitere Informationen finden Sie unter [Federated Data Access](../connect/fda.md).

### Wahl der Schlüssel {#choice-of-keys}

Zusätzlich zu den in den meisten Tabellen standardmäßig definierten Variablen **autouid** sollten Sie einige logische oder geschäftliche Schlüssel (Kontonummer, Kundennummer usw.) hinzufügen. Sie kann später für Einfuhren/Überleitungszwecke oder Datenpackagen verwendet werden. Weitere Informationen hierzu finden Sie unter [Bezeichner](#identifiers).

Effiziente Schlüssel sind unverzichtbar für die Leistung. Numerische Datentypen sollten immer als Schlüssel für Tabellen bevorzugt werden.

<!-- ### Dedicated tablespaces {#dedicated-tablespaces}

The tablespace attribute in the schema allows you to specify a dedicated tablespace for a table.

The installation wizard allows you to store objects by type (data, temporary).

Dedicated tablespaces are better for partitioning, security rules, and allow fluid and flexible administration, better optimization, and performance. -->

## Kennungen {#identifiers}

Adobe Campaign-Ressourcen verfügen über drei Kennungen (IDs). Sie können auch eine zusätzliche Kennung hinzuzufügen.

Die folgende Tabelle beschreibt diese Kennungen und ihren Zweck.

| Kennung | Beschreibung | Best Practices |
|--- |--- |--- |
| ID | <ul><li>Die ID ist der physische Primärschlüssel einer Adobe Campaign-Tabelle. Bei integrierten Tabellen handelt es sich um eine Universally Unique ID (UUID)</li><li>Diese Kennung muss eindeutig sein. </li><li>Eine UUID kann in einer Schema-Definition sichtbar sein.</li></ul> | <ul><li>Automatisch generierte IDs sollten nicht als Referenz in einem Workflow oder in einer Paketdefinition verwendet werden.</li><li>Die ID in einer Tabelle ist eine UUID und dieser Typ sollte nicht geändert werden.</li></ul> |
| Name (oder interner Name) | <ul><li>Diese Information ist eine eindeutige Kennung eines Datensatzes in einer Tabelle. Dieser Wert kann manuell aktualisiert werden, üblicherweise mit einem generierten Namen.</li><li>Dieser Bezeichner behält seinen Wert bei, wenn er in einer anderen Instanz von Adobe Campaign bereitgestellt wird, und sollte nicht leer sein.</li></ul> | <ul><li>Benennen Sie den von Adobe Campaign generierten Datensatznamen um, wenn das Objekt von einer Umgebung in eine andere bereitgestellt werden soll.</li><li>Wenn ein Objekt beispielsweise über ein Namensraum-Attribut verfügt (*Schema*), wird dieser allgemeine Namensraum für alle erstellten benutzerdefinierten Objekte genutzt. Einige reservierte Namensraum sollten nicht verwendet werden: *nms*, *xtk*.</li><li>Wenn ein Objekt keinen Namensraum hat (*workflow* oder *Versand*), wird dieser Namensraum-Begriff als Präfix eines internen Namensobjekts hinzugefügt: *namespaceMyObjectName*.</li><li>Verwenden Sie keine Sonderzeichen wie Leerzeichen &quot; &quot;, Doppelpunkt &quot;:&quot; oder Bindestrich &quot;-&quot;. Alle diese Zeichen würden durch einen Unterstrich (_) ersetzt werden. Beispielsweise würden &quot;abc-def&quot; und &quot;abc:def&quot; als &quot;abc_def&quot; gespeichert werden und sich gegenseitig überschreiben.</li></ul> |
| Titel | <ul><li>Der Titel ist die Unternehmenskennung eines Objekts oder Datensatzes in Adobe Campaign.</li><li>Dieses Objekt erlaubt Leerzeichen und Sonderzeichen.</li><li>Der Titel garantiert nicht die Einzigartigkeit eines Datensatzes.</li></ul> | <ul><li>Es wird empfohlen, eine Struktur für die Objekttitel festzulegen.</li><li>Dies ist die benutzerfreundlichste Lösung, um einen Datensatz oder ein Objekt für einen Adobe Campaign-Benutzer zu identifizieren.</li></ul> |

Der primäre Adobe Campaign ist eine automatisch generierte UUID für alle integrierten Tabellen und kann für benutzerdefinierte Tabellen identisch sein.

Auch wenn die Anzahl der IDs unbegrenzt ist, sollten Sie sich um die Größe Ihrer Datenbank kümmern, um eine optimale Leistung sicherzustellen. Um Probleme zu vermeiden, müssen Sie die Einstellungen für die Bereinigung der Instanz anpassen. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](#data-retention).


## Benutzerdefinierte interne Schlüssel {#custom-internal-keys}

Für jede in Adobe Campaign erstellte Tabelle sind Primär Schlüssel erforderlich.

Die meisten Organisationen importieren Datensätze aus externen Systemen. Während der physische Schlüssel der Empfänger-Tabelle das Attribut &quot;id&quot;ist, kann zusätzlich ein benutzerdefinierter Schlüssel festgelegt werden.

Dieser benutzerdefinierte Schlüssel ist der eigentliche Hauptschlüssel für den Datensatz im externen Adobe Campaign zur Systemzufuhr.

Beim Erstellen einer benutzerdefinierten Tabelle stehen Ihnen zwei Optionen zur Verfügung:
* Eine Kombination aus automatisch generiertem Schlüssel (ID) und internem Schlüssel (benutzerdefiniert). Diese Option ist interessant, wenn Ihr Systemschlüssel ein zusammengesetzter Schlüssel oder keine Ganzzahl ist. Ganzzahlen bieten höhere Leistungen in umfangreichen Tabellen und in Verbindung mit anderen Tabellen.
* Verwendung des Primärschlüssels als Primärschlüssel des externen Systems. Diese Lösung wird in der Regel bevorzugt, da sie das Importieren und Exportieren von Daten durch einen einheitlichen Schlüssel zwischen verschiedenen Systemen vereinfacht. Autouuid sollte deaktiviert werden, wenn der Schlüssel &quot;id&quot;heißt und mit externen Werten gefüllt werden soll (nicht automatisch generiert).

>[!CAUTION]
>
>Eine Autuid sollte nicht als Referenz in Workflows verwendet werden.


## Links und Kardinalität {#links-and-cardinality}

### Relationen {#links}

Achten Sie auf die &quot;eigene&quot; Integrität auf großen Tischen. Das Löschen von Datensätzen mit einer breiten Tabelle in &quot;eigener&quot;Integrität kann die Instanz stoppen. Die Tabelle ist gesperrt und die Löschungen werden einzeln vorgenommen. Daher ist es am besten, &quot;neutrale&quot; Integrität auf untergeordneten Tabellen mit großen Mengen zu verwenden.

Das Deklarieren eines Links als externer Verbindungspunkt ist nicht gut für die Leistung. Der Null-ID-Datensatz emuliert die externe Verbindungsfunktion. Es ist nicht erforderlich, externe Verbindungen zu deklarieren, wenn der Link die Autouuid verwendet.

Obwohl es möglich ist, eine beliebige Tabelle in einem Workflow einzubinden, empfiehlt Adobe, allgemeine Relationen zwischen Ressourcen direkt in der Definition der Datenstruktur festzulegen.

Die Relation sollte entsprechend den tatsächlichen Daten in den Tabellen definiert werden. Eine falsche Definition könnte sich auf Daten auswirken, die über Relationen abgerufen wurden, z. B. durch unerwartetes Duplizieren von Datensätzen.

Benennen Sie den Link konsistent mit dem Tabellennamen: der Linkname sollte dabei helfen, zu verstehen, was die entfernte Tabelle ist.

Benennen Sie eine Relation nicht mit &quot;id&quot; als Suffix. Benennen Sie sie beispielsweise &quot;transaction&quot; anstelle von &quot;transactionId&quot;.

Standardmäßig erstellt Adobe Campaign eine Verknüpfung mit dem Primärschlüssel der externen Tabelle. Aus Gründen der Klarheit ist es besser, die Verknüpfung in der Linkdefinition explizit zu definieren.

### Kardinalität {#cardinality}

Stellen Sie beim Entwerfen eines Links sicher, dass der Datensatz der Zielgruppe eindeutig ist, wenn eine 1-1-Beziehung deklariert wurde. Andernfalls gibt der Beitritt möglicherweise mehrere Datensätze zurück, wenn nur einer erwartet wird. Dies führt bei der Vorbereitung des Versands zu Fehlern, wenn &quot;die Abfrage mehr Zeilen zurückgibt als erwartet&quot;. Stellen Sie den Linknamen auf denselben Namen wie das Zielgruppe-Schema ein.

Definieren Sie einen Link mit einer Kardinalität (1-N) im Schema auf der (1) Seite. So sollte beispielsweise der Empfänger (1) - (N) Transaktion im Transaktions-Schema definiert werden.

Beachten Sie, dass die umgekehrte Kardinalität eines Links standardmäßig (N) lautet. Es ist möglich, einen Link (1-1) zu definieren, indem das Attribut revCardinality=&#39;single&#39; zur Linkdefinition hinzugefügt wird.

Wenn der umgekehrte Link für den Benutzer nicht sichtbar sein sollte, können Sie ihn mit der Linkdefinition revLink=&#39;_KEINE_&#39; ausblenden. Ein guter Anwendungsfall hierfür ist die Definition eines Links vom Empfänger zur letzten abgeschlossenen Transaktion. Sie müssen nur den Link vom Empfänger zur letzten Transaktion sehen, und es ist kein Rückwärtslink erforderlich, um in der Transaktionstabelle sichtbar zu sein.

Links, die einen externen Anschluss (1-0.1) ausführen, sollten mit Vorsicht verwendet werden, da dies die Systemleistung beeinträchtigt.

## Datenbeibehaltung {#data-retention}

Adobe Campaign ist weder ein Data Warehouse noch ein Berichte-Tool. Um eine gute Performance der Adobe Campaign-Lösung zu gewährleisten, sollte daher das Datenbankwachstum unter Kontrolle bleiben. Um dies zu erreichen, kann die Befolgung einiger der unten aufgeführten Best Practices hilfreich sein.

Die nativen Log-Tabellen in Campaign verfügen über eine vordefinierte Beibehaltungsdauer, die üblicherweise auf maximal sechs Monate begrenzt ist.

Im Folgenden finden Sie die standardmäßige Beibehaltungsdauer für Standardtabellen. Beachten Sie, dass diese Beibehaltungswerte von den technischen Adobe-Administratoren während der Implementierung festgelegt werden und daher je nach Kundenanforderungen variieren können.

* **Konsolidiertes Tracking**: 1 Jahr
* **Versandlogs**: 6 Monate
* **Trackinglogs**: 1 Jahr
* **Gelöschte Sendungen**: 1 Woche
* **Importzurückweisungen**: 6 Monate
* **Besucherprofile**: 1 Monat
* **Angebotsvorschläge**: 1 Jahr
* **Ereignisse**: 1 Monat
* **Statistiken zur Ereignisverarbeitung**: 1 Jahr
* **Ereignisse mit Verlauf**: 1 Jahr
* **Ignorierte Pipeline-Ereignisse**: 1 Monat

>[!CAUTION]
>
>Benutzerdefinierte Tabellen werden nicht mit dem standardmäßigen Bereinigungsprozess bereinigt. Dies ist zwar am ersten Tag nicht erforderlich, vergessen Sie jedoch nicht, einen Bereinigungsprozess für Ihre benutzerdefinierten Tabellen zu erstellen, da dies zu Leistungsproblemen führen könnte.

Es gibt einige Lösungen, um den Bedarf an Datensätzen in Adobe Campaign zu minimieren:
* Exportieren Sie die Daten in ein Data Warehouse außerhalb von Adobe Campaign.
* Generieren Sie aggregierte Werte, die weniger Platz einnehmen und gleichzeitig für Ihre Marketingpraktiken ausreichen. So benötigen Sie beispielsweise nicht den vollständigen Verlauf der Kundentransaktionen in Adobe Campaign, um die letzten Käufe zu verfolgen.

Sie können das Attribut &quot;deleteStatus&quot;in einem Schema deklarieren. Es ist effizienter, den Datensatz als gelöscht zu kennzeichnen und dann die Löschung in der Bereinigungs-Aufgabe zu verschieben.

:language_ballon: Wenden Sie sich als Managed Cloud Services an die Adobe Consultants oder technischen Administratoren, um mehr über die Aufbewahrung zu erfahren oder um die Aufbewahrung für benutzerdefinierte Tabellen festzulegen.

## Leistung {#performance}

Befolgen Sie die nachstehenden Best Practices, um eine bessere Leistung sicherzustellen.

### Allgemeine Empfehlungen {#general-recommendations}

* Vermeiden Sie die Verwendung von Operationen wie &quot;CONTAINS&quot; in Abfragen. Wenn Sie wissen, wonach gefiltert werden soll, wenden Sie dieselbe Bedingung mit &quot;EQUAL TO&quot; oder anderen spezifischen Filteroperatoren an.
* Vergewissern Sie sich, dass Prozesse wie Import und Export außerhalb der Geschäftszeiten ausgeführt werden.
* Stellen Sie sicher, dass ein Zeitplan für alle täglichen Aktivitäten vorhanden ist und halten Sie sich an ihn.
* Wenn einer oder mehrere der täglichen Prozesse fehlschlagen und sie am selben Tag noch ausgeführt werden müssen, stellen Sie sicher, dass beim Starten des manuellen Prozesses keine Konflikte auftreten, da dies die Systemleistung beeinträchtigen könnte.
* Stellen Sie sicher, dass keine der täglichen Kampagnen während des Importvorgangs oder bei der Ausführung eines manuellen Prozesses ausgeführt wird.
* Verwenden Sie eine oder mehrere Referenztabellen, anstatt ein Feld in jeder Zeile zu duplizieren. Bei Verwendung von Schlüssel/Wert-Paaren ist es empfehlenswert, einen numerischen Schlüssel zu wählen.
* Eine kurze Zeichenfolge ist weiterhin zulässig. Falls Referenztabellen bereits in einem externen System vorhanden sind, erleichtert die Wiederverwendung derselben die Datenintegration mit Adobe Campaign.

### 1-zu-n-Beziehungen {#one-to-many-relationships}

* Das Datendesign beeinflusst Benutzerfreundlichkeit und Funktionalität. Wenn Sie Ihr Datenmodell mit zahlreichen 1-zu-n-Beziehungen entwickeln, wird es für Benutzer schwieriger, in der Anwendung eine sinnvolle Logik zu erstellen. Für technisch nicht versierte Marketing-Experten kann es schwierig sein, eine 1-zu-n-Filterlogik zu entwerfen und zu verstehen.
* Es wird empfohlen, alle wichtigen Felder in einer Tabelle zu vereinen, da Benutzer so leichter Abfragen erstellen können. Unter Umständen kann die Leistung auch verbessert werden, wenn einige Felder in mehreren Tabellen dupliziert werden, wenn dadurch ein Join vermieden werden kann.
* Bestimmte integrierte Funktionen können nicht auf 1-zu-n Beziehungen verweisen, z. B. die Angebotsgewichtungsformel und Sendungen.

## Große Tabellen {#large-tables}

Adobe Campaign setzt auf Datenbankmaschinen von Drittanbietern. Je nach Anbieter ist für die Leistungsoptimierung bei größeren Tabellen möglicherweise ein bestimmtes Design erforderlich.

Im Folgenden finden Sie einige gängige Best Practices, die beim Entwerfen Ihres Datenmodells mit großen Tabellen und komplexen Verbindungen befolgt werden sollten.

* Wenn Sie zusätzliche benutzerdefinierte Empfänger-Tabellen verwenden, stellen Sie sicher, dass Sie für jede Zuordnung von Versänden über eine dedizierte Protokolltabelle verfügen.
* Reduzieren Sie die Anzahl der Spalten, indem Sie beispielsweise die nicht verwendeten Spalten ermitteln.
* Optimieren Sie die Datenmodellrelationen, indem Sie komplexe Joins vermeiden, wie z. B. Joins mit mehreren Bedingungen und/oder mit mehreren Spalten.
* Verwenden Sie für Join-Schlüssel immer numerische Daten anstelle von Zeichenfolgen.
* Reduzieren Sie die Tiefe der Protokollaufbewahrung so weit wie möglich. Wenn Sie einen tieferen Verlauf benötigen, können Sie Berechnungen aggregieren und/oder benutzerdefinierte Protokolltabellen bearbeiten, um einen größeren Verlauf zu speichern.

### Größe der Tabellen {#size-of-tables}

Die Tabellengröße ist eine Kombination aus der Anzahl der Datensätze und der Anzahl der Spalten pro Datensatz. Beide können sich auf die Performance von Abfragen auswirken.

* Eine **kleine**-Tabelle ähnelt der Versand-Tabelle.
* Eine **mittlere**-Tabelle entspricht der Größe der Empfänger-Tabelle. Es hat einen Datensatz pro Kunde.
* Die Tabelle **large-size** ist der Tabelle &quot;Weit gefasst&quot;ähnlich. Es enthält viele Datensätze pro Kunde.
Wenn Ihre Datenbank z. B. 10 Millionen Empfänger enthält, enthält die Tabelle &quot;Umfassendes Protokoll&quot;etwa 100 bis 200 Millionen Meldungen und die Tabelle &quot;Versand&quot;einige Tausend Datensätze.

Die Anzahl der Zeilen wirkt sich auch auf die Leistung aus. Die Adobe Campaign-Datenbank dient nicht zum Speichern von Verlaufsdaten, die nicht aktiv für Targeting- oder Personalisierungszwecke verwendet werden - dies ist eine operative Datenbank.

Um Leistungsprobleme im Zusammenhang mit der hohen Zeilenanzahl zu vermeiden, sollten Sie nur die erforderlichen Datensätze in der Datenbank speichern. Alle anderen Datensätze sollten in ein Drittanbieter-Data Warehouse exportiert und aus der Adobe Campaign-Betriebsdatenbank entfernt werden.

Im Folgenden finden Sie einige Best Practices zur Größe von Tabellen:

* Entwerfen Sie große Tabellen mit weniger Feldern und mehr numerischen Daten.
* Verwenden Sie nicht den Typ einer großen Anzahl von Spalten, um kleine Zahlen wie boolesche Werte zu speichern.
* Entfernen Sie nicht verwendete Spalten aus der Tabellendefinition.
* Behalten Sie keine historischen oder inaktiven Daten in Ihrer Adobe Campaign-Datenbank bei (Export und Bereinigung).
