---
solution: Campaign v8
product: Adobe Campaign
title: Best Practices für Datenmodelle
description: Best Practices für die Erweiterung von Campaign-Datenmodellen
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '2688'
ht-degree: 35%

---

# Best Practices für Datenmodelle{#data-model-best-practices}

In diesem Dokument werden die wichtigsten Empfehlungen beim Entwerfen Ihres Adobe Campaign-Datenmodells erläutert.

Das Adobe Campaign-System ist sehr flexibel und kann über die ursprüngliche Implementierung hinaus erweitert werden. Obwohl die Möglichkeiten unbegrenzt sind, ist es wichtig, die richtigen Entscheidungen zu treffen und eine solide Grundlage zu schaffen, um mit der Entwicklung Ihres Datenmodells zu beginnen.

Ein besseres Verständnis der nativen Campaign-Tabellen und ihrer Beziehung untereinander finden Sie in [diesem Abschnitt](datamodel.md) .

:bulb: Lesen Sie [diesen Abschnitt](schemas.md) , um mit Campaign-Schemata zu beginnen.

:bulb: Erfahren Sie, wie Sie Erweiterungsschemata konfigurieren, um das konzeptionelle Datenmodell der Adobe Campaign-Datenbank in [dieser Seite](extend-schema.md) zu erweitern.

## Architektur von Datenmodellen {#data-model-architecture}

Adobe Campaign ist ein leistungsstarkes kanalübergreifendes System zur Kampagnenverwaltung, das es Ihnen ermöglicht, Online- und Offline-Strategien zu kombinieren, um personalisierte Kundenerlebnisse bereitzustellen.

### Kundenorientierter Ansatz {#customer-centric-approach}

Während die meisten E-Mail-Dienstleister für die Kundenkommunikation einen listenorientierten Ansatz verfolgen, setzt Adobe Campaign eine relationale Datenbank ein, um eine breitere Sicht auf die Kunden und ihre Eigenschaften zu nutzen.

Um auf die Beschreibung der einzelnen Tabellen zuzugreifen, navigieren Sie zu **[!UICONTROL Admin > Konfiguration > Datenschemata]**, wählen Sie eine Ressource aus der Liste aus und klicken Sie auf den Tab **[!UICONTROL Dokumentation]** .


>[!NOTE]
>
>Adobe Campaign ermöglicht das Erstellen einer [benutzerdefinierten Empfängertabelle](custom-recipient.md). In den meisten Fällen wird jedoch empfohlen, die integrierte [Empfängertabelle](datamodel.md#ootb-profiles) zu nutzen, die bereits über vordefinierte zusätzliche Tabellen und Funktionen verfügt.

### Daten für Adobe Campaign {#data-for-campaign}

Welche Daten sollten an Adobe Campaign gesendet werden? Es ist äußerst wichtig festzustellen, welche Daten Sie für Ihre Marketingaktivitäten benötigen.

>[!NOTE]
>
>Adobe Campaign ist weder ein Data Warehouse noch ein Reporting-Tool. Versuchen Sie daher nicht, alle möglichen Kunden und die zugehörigen Informationen in Adobe Campaign zu importieren oder Daten zu importieren, die nur zum Erstellen von Berichten verwendet werden.

Um zu entscheiden, ob ein Attribut in Adobe Campaign erforderlich ist oder nicht, fragen Sie sich, ob es unter eine dieser Kategorien fällt:

* Für die **Segmentierung** verwendetes Attribut
* Für **Datenverwaltungsprozesse** verwendetes Attribut (z. B. Aggregatberechnung)
* Für die **Personalisierung** verwendetes Attribut

Wenn ein Attribut nicht in eine dieser Kategorien fällt, benötigen Sie es wahrscheinlich nicht in Adobe Campaign.

### Auswahl der Datentypen {#data-types}

Um eine gute Architektur und Systemleistung sicherzustellen, befolgen Sie die folgenden Best Practices, wenn Sie Daten in Adobe Campaign einrichten.

* Innerhalb einer großen Tabelle können Sie Zeichenfolge oder numerische Felder einfügen und Links zu Referenztabellen hinzufügen (beim Arbeiten mit einer Werteliste).
* Mit dem Attribut **expr** können Sie ein Schemaattribut als berechnetes Feld und nicht als physischen Set-Wert in einer Tabelle definieren. Dadurch kann der Zugriff auf die Informationen in einem anderen Format (z. B. Alter und Geburtsdatum) möglich sein, ohne beide Werte speichern zu müssen. Auf diese Weise lassen sich Felder nicht duplizieren. Beispielsweise verwendet die Empfängertabelle einen Ausdruck für die Domain, der bereits im E-Mail-Feld vorhanden ist.
* Wenn die Berechnung des Ausdrucks komplex ist, wird jedoch nicht empfohlen, das Attribut **expr** zu verwenden, da sich die Berechnung direkt auf die Leistung Ihrer Abfragen auswirken kann.
* Der Typ **XML** eignet sich gut, um zu vermeiden, dass zu viele Felder erstellt werden. Es benötigt jedoch auch Speicherplatz, da eine CLOB-Spalte in der Datenbank verwendet wird. Dies kann auch zu komplexen SQL-Abfragen führen und die Leistung beeinträchtigen.
* Die Länge eines Felds **String** sollte immer mit der Spalte definiert werden. Standardmäßig beträgt die maximale Länge in Adobe Campaign 16.000. Adobe empfiehlt jedoch, das Feld zu kürzen, wenn Sie bereits wissen, dass die Feldlänge kürzer ist.
* Es ist akzeptabel, dass ein Feld in Adobe Campaign kürzer ist als im Quellsystem, wenn Sie sicher sind, dass die Länge im Quellsystem zu groß ist und nicht benötigt wird. Dies könnte eine kürzere Zeichenfolge oder kleinere Ganzzahl in Adobe Campaign bedeuten.

### Feldauswahl {#choice-of-fields}

Ein Feld muss in einer Tabelle gespeichert werden, wenn es einen Zielgruppen- oder Personalisierungszweck hat. Wenn also ein Feld nicht zum Senden einer personalisierten E-Mail verwendet oder als Kriterium in einer Abfrage verwendet wird, nimmt es unnötigerweise Speicherplatz in Anspruch.


### Auswahl der Schlüssel {#choice-of-keys}

Zusätzlich zu der in den meisten Tabellen standardmäßig definierten **autouid** sollten Sie erwägen, einige logische oder geschäftliche Schlüssel hinzuzufügen (Kontonummer, Kundennummer usw.). Sie kann später für Importe/Abstimmungen oder Datenpackages verwendet werden. Weitere Informationen hierzu finden Sie unter [Kennungen](#identifiers).

Effiziente Schlüssel sind unverzichtbar für die Leistung. Mit Snowflake können Sie numerische oder zeichenfolgenbasierte Datentypen als Schlüssel für Tabellen einfügen.

<!-- ### Dedicated tablespaces {#dedicated-tablespaces}

The tablespace attribute in the schema allows you to specify a dedicated tablespace for a table.

The installation wizard allows you to store objects by type (data, temporary).

Dedicated tablespaces are better for partitioning, security rules, and allow fluid and flexible administration, better optimization, and performance. -->

## Kennungen {#identifiers}

Adobe Campaign-Ressourcen verfügen über drei Kennungen (IDs). Sie können auch eine zusätzliche Kennung hinzuzufügen.

Die folgende Tabelle beschreibt diese Kennungen und ihren Zweck.

| Kennung | Beschreibung | Best Practices |
|--- |--- |--- |
| ID | <ul><li>Die ID ist der physische Primärschlüssel einer Adobe Campaign-Tabelle. Bei integrierten Tabellen handelt es sich um eine Universally Unique ID (UUID)</li><li>Diese Kennung muss eindeutig sein. </li><li>Eine UUID kann in einer Schemadefinition sichtbar sein.</li></ul> | <ul><li>Automatisch generierte Kennungen sollten nicht als Referenz in einem Workflow oder in einer Package-Definition verwendet werden.</li><li>Die ID in einer Tabelle ist eine UUID und dieser Typ sollte nicht geändert werden.</li></ul> |
| Name (oder interner Name) | <ul><li>Diese Information ist eine eindeutige Kennung eines Datensatzes in einer Tabelle. Dieser Wert kann manuell aktualisiert werden, in der Regel mit einem generierten Namen.</li><li>Diese Kennung behält ihren Wert bei, wenn er in einer anderen Instanz von Adobe Campaign bereitgestellt wird, und sollte nicht leer sein.</li></ul> | <ul><li>Benennen Sie den von Adobe Campaign generierten Datensatznamen um, wenn das Objekt von einer Umgebung in eine andere bereitgestellt werden soll.</li><li>Wenn ein Objekt beispielsweise über ein Namespace-Attribut verfügt (*schema*), wird dieser gemeinsame Namespace für alle erstellten benutzerdefinierten Objekte genutzt. Einige reservierte Namespaces sollten nicht verwendet werden: *nms*, *xtk* usw.  Beachten Sie, dass einige Namespaces nur intern sind. [Weitere Informationen](schemas.md#reserved-namespaces).</li><li>Wenn ein Objekt keinen Namespace hat (*workflow* oder *delivery* zum Beispiel), wird diese Namespace-Idee als Präfix eines internen Namensobjekts hinzugefügt: *namespaceMyObjectName*.</li><li>Verwenden Sie keine Sonderzeichen wie Leerzeichen &quot; &quot;, Doppelpunkt &quot;:&quot; oder Bindestrich &quot;-&quot;. Alle diese Zeichen würden durch einen Unterstrich (_) ersetzt werden. Beispielsweise würden &quot;abc-def&quot; und &quot;abc:def&quot; als &quot;abc_def&quot; gespeichert werden und sich gegenseitig überschreiben.</li></ul> |
| Titel | <ul><li>Der Titel ist die Unternehmenskennung eines Objekts oder Datensatzes in Adobe Campaign.</li><li>Dieses Objekt erlaubt Leerzeichen und Sonderzeichen.</li><li>Der Titel garantiert nicht die Einzigartigkeit eines Datensatzes.</li></ul> | <ul><li>Es wird empfohlen, eine Struktur für die Objekttitel festzulegen.</li><li>Dies ist die benutzerfreundlichste Lösung, um einen Datensatz oder ein Objekt für einen Adobe Campaign-Benutzer zu identifizieren.</li></ul> |

Der Primärschlüssel von Adobe Campaign ist eine automatisch generierte UUID für alle integrierten Tabellen. Eine UUID kann auch für benutzerdefinierte Tabellen verwendet werden.

Selbst wenn die Anzahl der IDs unbegrenzt ist, sollten Sie sich um die Größe Ihrer Datenbank kümmern, um eine optimale Leistung sicherzustellen. Um Probleme zu vermeiden, passen Sie die Bereinigungsparameter der Instanz an. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](#data-retention).


## Benutzerdefinierte interne Schlüssel {#custom-internal-keys}

Für jede in Adobe Campaign erstellte Tabelle sind Primären Schlüssel erforderlich.

Die meisten Organisationen importieren Datensätze aus externen Systemen. Während der physische Schlüssel der Empfängertabelle das Attribut &quot;id&quot;ist, kann zusätzlich ein benutzerdefinierter Schlüssel bestimmt werden.

Dieser benutzerdefinierte Schlüssel ist der tatsächliche Datensatz-Primärschlüssel im externen System, das Adobe Campaign versorgt.

Beim Erstellen einer benutzerdefinierten Tabelle haben Sie zwei Optionen:
* Eine Kombination aus automatisch generiertem Schlüssel (ID) und internem Schlüssel (benutzerdefiniert). Diese Option ist interessant, wenn Ihr Systemschlüssel ein zusammengesetzter Schlüssel oder keine Ganzzahl ist. Mit Snowflake bieten Ganzzahlen oder string-basierte Schlüssel höhere Leistungen in großen Tabellen und in Verbindung mit anderen Tabellen.
* Verwendung des Primärschlüssels als Primärschlüssel des externen Systems. Diese Lösung wird in der Regel bevorzugt, da sie das Importieren und Exportieren von Daten durch einen einheitlichen Schlüssel zwischen verschiedenen Systemen vereinfacht. Die automatische UID sollte deaktiviert werden, wenn der Schlüssel &quot;id&quot;heißt und mit externen Werten gefüllt werden soll (nicht automatisch generiert).

>[!CAUTION]
>
>Eine automatische ID sollte nicht als Referenz in Workflows verwendet werden.


## Relationen und Kardinalität {#links-and-cardinality}

### Relationen {#links}

Vorsicht vor der &quot;eigenen&quot; Integrität auf großen Tabellen. Das Löschen von Datensätzen mit großen Tabellen in der Integrität &quot;own&quot;kann die Instanz möglicherweise stoppen. Die Tabelle ist gesperrt und die Löschungen werden einzeln vorgenommen. Daher ist es am besten, &quot;neutrale&quot;Integrität auf untergeordneten Tabellen mit großen Volumina zu verwenden.

Das Deklarieren eines Links als externer Join ist nicht leistungsfähig. Der Nullid-Datensatz emuliert die externe Join-Funktion. Es ist nicht erforderlich, externe Joins zu deklarieren, wenn der Link die automatische UID verwendet.

Obwohl es möglich ist, eine beliebige Tabelle in einem Workflow einzubinden, empfiehlt Adobe, allgemeine Relationen zwischen Ressourcen direkt in der Definition der Datenstruktur festzulegen.

Die Relation sollte entsprechend den tatsächlichen Daten in den Tabellen definiert werden. Eine falsche Definition könnte sich auf Daten auswirken, die über Relationen abgerufen wurden, z. B. durch unerwartetes Duplizieren von Datensätzen.

Benennen Sie den Link konsistent mit dem Tabellennamen: Der Link-Name sollte helfen zu verstehen, was die entfernte Tabelle ist.

Benennen Sie eine Relation nicht mit &quot;id&quot; als Suffix. Benennen Sie sie beispielsweise &quot;transaction&quot; anstelle von &quot;transactionId&quot;.

Standardmäßig erstellt Adobe Campaign einen Link mithilfe des Primärschlüssels der externen Tabelle. Für mehr Klarheit ist es vorzuziehen, den Join in der Linkdefinition explizit zu definieren.

### Kardinalität {#cardinality}

Stellen Sie beim Entwerfen einer Relation sicher, dass der Zieldatensatz eindeutig ist, wenn eine 1:1-Beziehung deklariert wurde. Andernfalls kann der Join mehrere Datensätze zurückgeben, wenn nur einer erwartet wird. Dies führt zu Fehlern bei der Versandvorbereitung, wenn &quot;die Abfrage mehr Zeilen als erwartet zurückgibt&quot;. Setzen Sie den Linknamen auf denselben Namen wie das Zielschema.

Definieren Sie eine Relation mit einer Kardinalität (1-N) im Schema auf der (1) Seite. Beispielsweise sollte die Relation Empfänger (1) - (N) Transaktion im Transaktionsschema definiert werden.

Beachten Sie, dass die umgekehrte Kardinalität eines Links standardmäßig (N) ist. Es ist möglich, einen Link (1-1) zu definieren, indem das Attribut revCardinality=&#39;single&#39; zur Definition des Links hinzugefügt wird.

Wenn der umgekehrte Link für den Benutzer nicht sichtbar sein soll, können Sie ihn mit der Linkdefinition revLink=&#39;_NONE_&#39; ausblenden. Ein guter Anwendungsfall hierfür ist die Definition eines Links vom Empfänger zur letzten abgeschlossenen Transaktion. Sie müssen nur den Link vom Empfänger zur letzten Transaktion sehen und in der Transaktionstabelle muss kein Reverse-Link sichtbar sein.

Links, die einen externen Join ausführen (1-0.1), sollten mit Vorsicht verwendet werden, da dies die Systemleistung beeinträchtigt.

## Datenbeibehaltung {#data-retention}

Adobe Campaign ist weder ein Data Warehouse noch ein Reporting-Tool. Um eine gute Leistung der Adobe Campaign-Lösung sicherzustellen, sollte daher das Datenbankwachstum unter Kontrolle bleiben. Um dies zu erreichen, kann die Befolgung einiger der unten aufgeführten Best Practices hilfreich sein.

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
* Generieren Sie aggregierte Werte, die weniger Speicherplatz belegen und gleichzeitig für Ihre Marketingpraktiken ausreichen. Sie benötigen beispielsweise nicht den vollständigen Kundentransaktionsverlauf in Adobe Campaign, um die letzten Käufe zu verfolgen.

Sie können das Attribut &quot;deleteStatus&quot; in einem Schema deklarieren. Es ist effizienter, den Datensatz als gelöscht zu markieren und dann den Löschvorgang in der Bereinigungsaufgabe zu verschieben.

:Sprache_Ballon: Wenden Sie sich als Managed Cloud Services-Benutzer an die Adobe-Berater oder technischen Administratoren, um mehr über die Beibehaltung zu erfahren oder um festzustellen, ob Sie die Beibehaltung für benutzerdefinierte Tabellen festlegen müssen.

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

Adobe Campaign setzt auf Datenbank-Engines von Drittanbietern. Je nach Anbieter kann die Leistungsoptimierung für größere Tabellen ein bestimmtes Design erfordern.

Im Folgenden finden Sie einige gängige Best Practices, die beim Entwerfen Ihres Datenmodells mit großen Tabellen und komplexen Joins befolgt werden sollten.

* Wenn Sie zusätzliche benutzerdefinierte Empfängertabellen verwenden, stellen Sie sicher, dass Sie für jedes Versand-Mapping über eine dedizierte Protokolltabelle verfügen.
* Reduzieren Sie die Anzahl der Spalten, indem Sie beispielsweise die nicht verwendeten Spalten ermitteln.
* Optimieren Sie die Datenmodellrelationen, indem Sie komplexe Joins vermeiden, wie z. B. Joins mit mehreren Bedingungen und/oder mit mehreren Spalten.
* Bei Join-Schlüsseln können Sie numerische oder zeichenfolgenbasierte Werte verwenden.
* Reduzieren Sie die Tiefe der Protokollaufbewahrung so weit wie möglich. Wenn Sie einen tieferen Verlauf benötigen, können Sie Berechnungen aggregieren und/oder benutzerdefinierte Protokolltabellen bearbeiten, um einen größeren Verlauf zu speichern.

### Größe der Tabellen {#size-of-tables}

Die Tabellengröße ist eine Kombination aus der Anzahl der Datensätze und der Anzahl der Spalten pro Datensatz. Beide können die Leistung von Abfragen beeinträchtigen.

* Die Tabelle **small-size** ähnelt der Versandtabelle.
* Die Tabelle **medium size** entspricht der Größe der Empfängertabelle. Es hat einen Datensatz pro Kunde.
* Die Tabelle **large-size** ähnelt der Tabelle &quot;Broad log&quot;. Es enthält viele Datensätze pro Kunde.
Wenn Ihre Datenbank beispielsweise 10 Millionen Empfänger enthält, enthält die Tabelle Broad log etwa 100 bis 200 Millionen Nachrichten und die Tabelle Versand enthält einige Tausend Datensätze.

Die Anzahl der Zeilen wirkt sich auch auf die Leistung aus. Die Adobe Campaign-Datenbank ist nicht für die Speicherung von historischen Daten konzipiert, die nicht aktiv für Targeting- oder Personalisierungszwecke verwendet werden - dies ist eine funktionierende Datenbank.

Um Leistungsprobleme im Zusammenhang mit der hohen Zeilenanzahl zu vermeiden, sollten Sie nur die erforderlichen Datensätze in der Datenbank speichern. Jeder andere Datensatz sollte in ein Drittanbieter-Data Warehouse exportiert und aus der operativen Adobe Campaign-Datenbank entfernt werden.

Im Folgenden finden Sie einige Best Practices zur Größe von Tabellen:

* Entwerfen Sie große Tabellen mit weniger Feldern und numerischen Daten.
* Verwenden Sie nicht den großen Spaltentyp, um kleine Zahlen wie boolesche Werte zu speichern.
* Entfernen Sie nicht verwendete Spalten aus der Tabellendefinition.
* Behalten Sie keine historischen oder inaktiven Daten in Ihrer Adobe Campaign-Datenbank bei (Export und Bereinigung).
