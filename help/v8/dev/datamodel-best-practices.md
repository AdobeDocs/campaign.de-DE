---
title: Best Practices für Datenmodelle
description: Best Practices für die Erweiterung von Campaign-Datenmodellen
exl-id: bdd5e993-0ce9-49a8-a618-ab0ff3796d49
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: ht
source-wordcount: '2688'
ht-degree: 100%

---

# Best Practices für Datenmodelle{#data-model-best-practices}

In diesem Dokument werden die wichtigsten Empfehlungen beim Entwerfen Ihres Adobe Campaign-Datenmodells erläutert.

Das Adobe Campaign-System ist äußerst flexibel und kann über die ursprüngliche Implementierung hinaus erweitert werden. Obwohl die Möglichkeiten unbegrenzt sind, ist es wichtig, die richtigen Entscheidungen zu treffen und eine solide Grundlage zu schaffen, um mit der Entwicklung Ihres Datenmodells zu beginnen.

Genauere Informationen zu den in Campaign integrierten Tabellen und ihrer Beziehung zueinander finden Sie in [diesem Abschnitt](datamodel.md).

?? Lesen Sie [diesen Abschnitt](schemas.md), um mit Campaign-Schemata zu beginnen.

?? Erfahren Sie auf [dieser Seite](extend-schema.md), wie Sie Erweiterungsschemata konfigurieren können, um das konzeptionelle Datenmodell der Adobe Campaign-Datenbank zu erweitern.

## Architektur von Datenmodellen {#data-model-architecture}

Adobe Campaign ist ein leistungsstarkes kanalübergreifendes System zur Kampagnenverwaltung, das es Ihnen ermöglicht, Online- und Offline-Strategien zu kombinieren, um personalisierte Kundenerlebnisse bereitzustellen.

### Kundenorientierter Ansatz {#customer-centric-approach}

Während die meisten E-Mail-Dienstleister für die Kundenkommunikation einen listenorientierten Ansatz verfolgen, setzt Adobe Campaign eine relationale Datenbank ein, um eine breitere Sicht auf die Kunden und ihre Eigenschaften zu nutzen.

Um Beschreibungen der einzelnen Tabellen aufzurufen, navigieren Sie zu **[!UICONTROL &quot;Admin&quot; > &quot;Konfiguration&quot; > &quot;Datenschemata&quot;]**, wählen Sie eine Ressource aus der Liste und klicken Sie auf die Registerkarte **[!UICONTROL Dokumentation]**.


>[!NOTE]
>
>Adobe Campaign ermöglicht das Erstellen einer [benutzerdefinierten Empfängertabelle](custom-recipient.md). In den meisten Fällen wird jedoch empfohlen, die integrierte [Empfängertabelle](datamodel.md#ootb-profiles) zu nutzen, die über zusätzliche vordefinierte Tabellen und Funktionen verfügt.

### Daten für Adobe Campaign {#data-for-campaign}

Welche Daten sollten an Adobe Campaign gesendet werden? Es ist äußerst wichtig festzustellen, welche Daten Sie für Ihre Marketingaktivitäten benötigen.

>[!NOTE]
>
>Adobe Campaign ist weder ein Data Warehouse noch ein Reporting-Tool. Versuchen Sie also nicht, alle möglichen Kunden und zugehörige Daten in Adobe Campaign zu importieren bzw. Daten zu importieren, die nur dem Erstellen von Berichten dienen werden.

Um zu entscheiden, ob ein Attribut in Adobe Campaign erforderlich ist, fragen Sie sich, ob es in eine der folgenden Kategorien passt:

* Für die **Segmentierung** verwendetes Attribut
* Für **Datenverwaltungsprozesse** verwendetes Attribut (z. B. Aggregatberechnung)
* Für die **Personalisierung** verwendetes Attribut

Wenn ein Attribut nicht in eine dieser Kategorien fällt, benötigen Sie es wahrscheinlich nicht in Adobe Campaign.

### Auswahl von Datentypen {#data-types}

Um eine gute Architektur und Systemleistung sicherzustellen, befolgen Sie die folgenden Best Practices, wenn Sie Daten in Adobe Campaign einrichten.

* Innerhalb einer großen Tabelle können Sie zeichenfolgenbasierte oder numerische Felder einfügen und Links zu Referenztabellen hinzufügen (beim Arbeiten mit einer Werteliste).
* Mit dem Attribut **expr** können Sie ein Schema-Attribut in einer Tabelle als berechnetes Feld definieren (anstelle eines physischen definierten Werts). Dadurch wird Zugriff auf die Daten in einem anderen Format (z. B. Alter und Geburtsdatum) möglich, ohne dass beide Werte gespeichert werden müssen. So lässt sich verhindern, dass Felder dupliziert werden. Die Empfängertabelle nutzt beispielsweise einen Ausdruck für die Domain, der bereits im E-Mail-Feld vorhanden ist.
* Wenn die Berechnung des Ausdrucks jedoch komplex ist, wird eine Verwendung des Attributs **expr** nicht empfohlen, da eine Ad-hoc-Berechnung Auswirkungen auf die Leistung Ihrer Abfragen haben kann.
* Der Typ **XML** hilft dabei, eine Erstellung von zu vielen Feldern zu verhindern. Er benötigt jedoch Speicherplatz, da er eine CLOB-Spalte in der Datenbank verwendet. Außerdem können komplexe SQL-Abfragen entstehen, die die Leistung beeinträchtigen.
* Die Länge eines **Zeichenfolgenfelds** sollte immer mit der Spalte definiert werden. Standardmäßig beträgt die maximale Länge in Adobe Campaign 16.000 Zeichen. Adobe empfiehlt jedoch, eine kürzere maximale Länge zu definieren, wenn Sie bereits wissen, dass weniger Zeichen ausreichen werden.
* Es ist akzeptabel, dass ein Feld in Adobe Campaign kürzer ist als im Quellsystem, wenn Sie sicher sind, dass die Länge im Quellsystem zu groß ist und nicht benötigt wird. Dies könnte eine kürzere Zeichenfolge oder kleinere Ganzzahl in Adobe Campaign bedeuten.

### Auswahl von Feldern {#choice-of-fields}

Felder müssen in einer Tabelle gespeichert werden, wenn sie Zielgruppenbestimmungs- oder Personalisierungszwecken dienen. Anders ausgedrückt: Wird ein Feld nicht zum Senden einer personalisierten E-Mail oder als Kriterium in einer Abfrage verwendet, nimmt es unnötigerweise Speicherplatz in Anspruch.

### Auswahl von Schlüsseln {#choice-of-keys}

Zusätzlich zu dem in den meisten Tabellen standardmäßig definierten Schlüsseln **autouid** und **autopk** sollten Sie gegebenenfalls einige logische oder geschäftliche Schlüssel (Kundennummer usw.) hinzufügen. Diese können später für Importe, Abstimmungen oder Daten-Packages verwendet werden. Weitere Informationen hierzu finden Sie unter [Kennungen](#identifiers).

Effiziente Schlüssel sind unverzichtbar für hohe Leistung. Mit Snowflake können Sie numerische oder zeichenfolgenbasierte Datentypen als Schlüssel für Tabellen einfügen.

<!-- ### Dedicated tablespaces {#dedicated-tablespaces}

The tablespace attribute in the schema allows you to specify a dedicated tablespace for a table.

The installation wizard allows you to store objects by type (data, temporary).

Dedicated tablespaces are better for partitioning, security rules, and allow fluid and flexible administration, better optimization, and performance. -->

## Kennungen {#identifiers}

Adobe Campaign-Ressourcen verfügen über drei Kennungen (IDs). Sie können auch eine zusätzliche Kennung hinzuzufügen.

Die folgende Tabelle beschreibt diese Kennungen und ihren Zweck.

| Kennung | Beschreibung | Best Practices |
|--- |--- |--- |
| ID | <ul><li>Die ID ist der physische Primärschlüssel einer Adobe Campaign-Tabelle. Bei integrierten Tabellen handelt es sich um eine Universally Unique ID (UUID).</li><li>Diese Kennung muss eindeutig sein. </li><li>Eine UUID kann in einer Schemadefinition sichtbar sein.</li></ul> | <ul><li>Automatisch erstellte Kennungen sollten nicht als Referenz in einem Workflow oder in einer Package-Definition verwendet werden.</li><li>Die ID in einer Tabelle ist eine UUID. Dieser Typ sollte nicht geändert werden.</li></ul> |
| Name (oder interner Name) | <ul><li>Diese Information ist eine eindeutige Kennung eines Datensatzes in einer Tabelle. Der Wert kann manuell aktualisiert werden, üblicherweise mit einem erstellten Namen.</li><li>Die Kennung behält ihren Wert bei, wenn sie in einer anderen Instanz von Adobe Campaign bereitgestellt wird, und darf nicht leer sein.</li></ul> | <ul><li>Ändern Sie den von Adobe Campaign erstellten Namen, wenn Sie das Objekt von einer Umgebung aus in einer anderen bereitstellen möchten.</li><li>Wenn ein Objekt beispielsweise über ein Namespace-Attribut verfügt (zum Beispiel *schema*), wird dieser gemeinsame Namespace für alle erstellten benutzerdefinierten Objekte genutzt. Bestimmte reservierte Namespaces sollten nicht verwendet werden: *nms*, *xtk* usw.  Beachten Sie, dass einige Namespaces nur zur internen Verwendung verfügbar sind. [Weitere Informationen](schemas.md#reserved-namespaces).</li><li>Wenn ein Objekt keinen Namespace aufweist (zum Beispiel *workflow* oder *delivery*), wird dieser Namespace-Begriff als Präfix eines internen Namensobjekts hinzugefügt: *namespaceMyObjectName*.</li><li>Verwenden Sie keine Sonderzeichen wie Leerzeichen &quot; &quot;, Doppelpunkt &quot;:&quot; oder Bindestrich &quot;-&quot;. Alle diese Zeichen würden durch einen Unterstrich (_) ersetzt werden. Beispielsweise würden &quot;abc-def&quot; und &quot;abc:def&quot; als &quot;abc_def&quot; gespeichert werden und sich gegenseitig überschreiben.</li></ul> |
| Titel | <ul><li>Der Titel ist die Unternehmenskennung eines Objekts oder Datensatzes in Adobe Campaign.</li><li>Dieses Objekt erlaubt Leerzeichen und Sonderzeichen.</li><li>Der Titel garantiert nicht die Einzigartigkeit eines Datensatzes.</li></ul> | <ul><li>Es wird empfohlen, eine Struktur für die Objekttitel festzulegen.</li><li>Dies ist die benutzerfreundlichste Lösung, um einen Datensatz oder ein Objekt für einen Adobe Campaign-Benutzer zu identifizieren.</li></ul> |

Der Adobe Campaign-Primärschlüssel ist eine automatisch generierte UUID für alle integrierten Tabellen. Eine UUID kann auch für benutzerdefinierte Tabellen verwendet werden. [Weitere Informationen](keys.md)

Zwar ist die Anzahl der IDs unbegrenzt, doch sollten Sie auf die Größe Ihrer Datenbank achten, um optimale Leistung sicherzustellen. Um Probleme zu vermeiden, sollten Sie die Einstellungen für die Bereinigung von Instanzen anpassen. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](#data-retention).


## Benutzerdefinierte interne Schlüssel {#custom-internal-keys}

Für jede in Adobe Campaign erstellte Tabelle sind Primärschlüssel erforderlich.

Die meisten Unternehmen importieren Datensätze aus externen Systemen. Während der physische Schlüssel der Empfängertabelle das &quot;id&quot;-Attribut ist, kann zusätzlich ein benutzerdefinierter Schlüssel festgelegt werden.

Dieser benutzerdefinierte Schlüssel ist der eigentliche Hauptschlüssel des Datensatzes im externen System, das Daten für Adobe Campaign bereitstellt.

Beim Erstellen einer benutzerdefinierten Tabelle stehen Ihnen zwei Optionen zur Verfügung:
* Kombination aus einem automatisch erstellten Schlüssel (ID) und einem internen Schlüssel (benutzerdefiniert). Diese Option ist interessant, wenn Ihr Systemschlüssel ein zusammengesetzter Schlüssel oder keine Ganzzahl ist. Mit Snowflake ermöglichen ganze Zahlen oder zeichenfolgenbasierte Schlüssel höhere Leistungen in großen Tabellen sowie in Verbindung mit anderen Tabellen.
* Verwendung des Primärschlüssels als Primärschlüssel des externen Systems. Diese Lösung wird in der Regel bevorzugt, da sie das Importieren und Exportieren von Daten durch einen einheitlichen Schlüssel zwischen verschiedenen Systemen vereinfacht. **Autouuid** sollte deaktiviert werden, wenn der Schlüssel &quot;id&quot; heißt und mit externen Werten ausgefüllt wird (also nicht automatisch erstellt werden soll).

>[!CAUTION]
>
>Eine Autouuid sollte nicht als Referenz in Workflows verwendet werden.


## Relationen und Kardinalität {#links-and-cardinality}

### Relationen {#links}

Achten Sie bei großen Tabellen auf die &quot;eigene&quot; Integrität. Durch das Löschen von Datensätzen, die über große Tabellen mit &quot;eigener&quot; Integrität verfügen, kann die Instanz möglicherweise angehalten werden. Die Tabelle wird gesperrt; die Löschungen werden einzeln vorgenommen. Daher ist es am besten, bei untergeordneten Tabellen mit großen Volumen &quot;neutrale&quot; Integrität anzuwenden.

Das Deklarieren einer Relation als externer Join ist nicht gut für die Leistung. Der Null-ID-Datensatz emuliert die externe Join-Funktion. Es müssen keine externen Joins deklariert werden, wenn die Relation die **autouuid** verwendet.

Obwohl es möglich ist, eine beliebige Tabelle in einem Workflow einzubinden, empfiehlt Adobe, allgemeine Relationen zwischen Ressourcen direkt in der Definition der Datenstruktur festzulegen.

Die Relation sollte entsprechend den tatsächlichen Daten in den Tabellen definiert werden. Eine falsche Definition könnte sich auf Daten auswirken, die über Relationen abgerufen wurden, z. B. durch unerwartetes Duplizieren von Datensätzen.

Benennen Sie die Relation konsequent nach der Tabelle: Der Name der Relation sollte Aufschluss über die ferne Tabelle geben.

Benennen Sie eine Relation nicht mit &quot;id&quot; als Suffix. Benennen Sie sie beispielsweise &quot;transaction&quot; anstelle von &quot;transactionId&quot;.

Standardmäßig erstellt Adobe Campaign eine Relation mit dem Primärschlüssel der externen Tabelle. Aus Gründen der Klarheit ist es besser, den Join in der Relationsdefinition explizit zu definieren.

### Kardinalität {#cardinality}

Stellen Sie beim Entwerfen einer Relation sicher, dass der Zieldatensatz eindeutig ist, falls eine 1-1-Beziehung deklariert wurde. Andernfalls gibt der Join möglicherweise mehrere Datensätze zurück, wenn nur einer erwartet wird. Dies führt bei der Versandvorbereitung zu Fehlern, wenn &quot;die Abfrage mehr Zeilen zurückgibt als erwartet&quot;. Verwenden Sie als Namen für die Relation denselben Namen wie beim Zielschema.

Definieren Sie eine Relation mit einer Kardinalität (1-N) im Schema auf der Seite (1). So sollte beispielsweise die Relation &quot;Empfänger (1) - (N) Transaktion&quot; im Transaktionsschema definiert werden.

Beachten Sie, dass eine Umkehrkardinalität einer Relation standardmäßig (N) lautet. Sie können eine Relation (1-1) definieren, indem Sie das Attribut revCardinality=&#39;single&#39; zur Relationsdefinition hinzufügen.

Wenn die Umkehrrelation für den Anwender nicht sichtbar sein soll, können Sie sie mit der Relationsdefinition revLink=&#39;_NONE_&#39; ausblenden. Ein typischer Anwendungsfall hierfür wäre die Definition einer Relation vom Empfänger zur letzten ausgeführten Transaktion. Sie müssen lediglich die Relation vom Empfänger zur letzten Transaktion sehen. In der Transaktionstabelle muss keine Umkehrrelation sichtbar sein.

Relationen, die einen externen Join vornehmen (1-0..1), sollten mit Vorsicht verwendet werden, da sie die Systemleistung beeinträchtigen.

## Datenbeibehaltung {#data-retention}

Adobe Campaign ist weder ein Data Warehouse noch ein Reporting-Tool. Zur Sicherstellung hoher Leistung von Adobe Campaign sollte daher das Datenbankwachstum kontrolliert werden. Dazu kann hilfreich sein, einige der unten aufgeführten Best Practices zu befolgen.

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
>Benutzerdefinierte Tabellen werden im standardmäßigen Bereinigungsprozess nicht bereinigt. Er mag zwar am ersten Tag noch nicht erforderlich sein, vergessen Sie aber nicht, einen Bereinigungsprozess für Ihre benutzerdefinierten Tabellen einzurichten, da sonst später Leistungsprobleme auftreten können.

Es gibt verschiedene Lösungen, um den Bedarf an Datensätzen in Adobe Campaign zu minimieren:
* Exportieren Sie die Daten in ein Data Warehouse außerhalb von Adobe Campaign.
* Generieren Sie aggregierte Werte, die weniger Platz einnehmen und dennoch für Ihre Marketing-Zwecke ausreichen. Sie benötigen beispielsweise nicht den vollständigen Verlauf von Kundentransaktionen in Adobe Campaign, um die letzten Käufe verfolgen zu können.

Sie können in einem Schema das Attribut &quot;deleteStatus&quot; deklarieren. Effizienter ist es, den Datensatz als gelöscht zu markieren und das Löschen in die Bereinigungsaufgabe zu verschieben.

?? Wenden Sie sich als Managed Cloud Services-Anwender an die Berater oder technischen Administratoren von Adobe, um mehr über Datenspeicherung zu erfahren oder wenn Sie eine Datenspeicherung für benutzerdefinierte Tabellen aktivieren müssen.

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

Adobe Campaign setzt auf Datenbank-Engines von Drittanbietern. Je nach Anbieter ist für die Leistungsoptimierung bei größeren Tabellen möglicherweise ein bestimmtes Design erforderlich.

Im Folgenden finden Sie einige verbreitete Best Practices, die beim Entwerfen Ihres Datenmodells mit großen Tabellen und komplexen Joins befolgt werden sollten.

* Wenn Sie zusätzliche benutzerdefinierte Empfängertabellen verwenden, stellen Sie sicher, dass Sie für jedes Versand-Mapping über eine dedizierte Protokolltabelle verfügen.
* Reduzieren Sie die Anzahl der Spalten, indem Sie beispielsweise die nicht verwendeten Spalten ermitteln.
* Optimieren Sie die Datenmodellrelationen, indem Sie komplexe Joins vermeiden, wie z. B. Joins mit mehreren Bedingungen und/oder mit mehreren Spalten.
* Bei Join-Schlüsseln können Sie numerische oder zeichenfolgenbasierte Werte verwenden.
* Reduzieren Sie die Tiefe der Protokollaufbewahrung so weit wie möglich. Wenn Sie einen tieferen Verlauf benötigen, können Sie Berechnungen aggregieren und/oder benutzerdefinierte Protokolltabellen bearbeiten, um einen größeren Verlauf zu speichern.

### Größe von Tabellen {#size-of-tables}

Die Tabellengröße ist eine Kombination aus der Anzahl der Datensätze und der Anzahl der Spalten pro Datensatz. Beide können sich auf die Leistung von Abfragen auswirken.

* Eine **kleine** Tabelle entspricht der Größe der Versandtabelle.
* Eine **mittelgroße** Tabelle entspricht der Größe der Empfängertabelle. Sie weist einen Datensatz pro Kunde auf.
* Eine **große** Tabelle entspricht der Größe der Tabelle &quot;Umfassendes Protokoll&quot;. Sie enthält mehrere Datensätze pro Kunde.
Wenn Ihre Datenbank z. B. 10 Millionen Empfänger umfasst, enthält die Tabelle &quot;Umfassendes Protokoll&quot; etwa 100 bis 200 Millionen Nachrichten und die Tabelle &quot;Versand&quot; einige Tausend Datensätze.

Die Anzahl der Zeilen wirkt sich ebenfalls auf die Leistung aus. Die Adobe Campaign-Datenbank dient nicht zum Speichern von Verlaufsdaten, die nicht aktiv für Zielgruppenbestimmungs- oder Personalisierungszwecke verwendet werden. Es handelt sich dabei um eine operative Datenbank.

Um Leistungsprobleme im Zusammenhang mit der hohen Zeilenanzahl zu verhindern, sollten Sie nur die erforderlichen Datensätze in der Datenbank speichern. Alle anderen Datensätze sollten Sie in das Data Warehouse eines Drittanbieters exportieren und aus der Adobe Campaign-Betriebsdatenbank entfernen.

Im Folgenden finden Sie Best Practices zur Größe von Tabellen:

* Planen Sie große Tabellen mit weniger Feldern und mehr numerischen Daten.
* Verwenden Sie nicht Spalten vom Typ große Zahlen, um kleine Zahlen wie boolesche Werte darin zu speichern.
* Entfernen Sie nicht verwendete Spalten aus der Tabellendefinition.
* Behalten Sie keine alten oder inaktiven Daten in Ihrer Adobe Campaign-Datenbank bei (Export und Bereinigung).
