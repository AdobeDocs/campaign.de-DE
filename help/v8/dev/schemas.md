---
solution: Campaign v8
product: Adobe Campaign
title: Verwenden von Campaign-Schemata
description: Erste Schritte mit Schemata
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '1253'
ht-degree: 7%

---

# Arbeiten mit Schemata{#gs-ac-schemas}

Die physische und logische Struktur der in der Anwendung übertragenen Daten wird in XML beschrieben. Sie folgt einer für Adobe Campaign spezifischen Grammatik, die als **schema** bezeichnet wird.

Ein Schema ist ein mit einer Datenbanktabelle verknüpftes XML-Dokument. Sie definiert die Datenstruktur und beschreibt die SQL-Definition der Tabelle:

* Der Name der Tabelle
* Felder
* Relationen zu anderen Tabellen

Außerdem wird die zum Speichern von Daten verwendete XML-Struktur beschrieben:

* Elemente und Attribute
* Hierarchie der Elemente
* Element- und Attributtypen
* Standardwerte
* Beschriftungen, Beschreibungen und andere Eigenschaften.

Mithilfe von Schemata können Sie eine Entität in der Datenbank definieren. Für jede Entität gibt es ein Schema.

Adobe Campaign setzt Datenschemata ein, um:

* Definieren Sie, wie Datenobjekte innerhalb der Anwendung mit zugrunde liegenden Datenbanktabellen verknüpft werden.
* Definieren von Beziehungen zwischen den unterschiedlichen Datenobjekten in der Campaign-Anwendung
* Definieren und Beschreiben der einzelnen Felder eines jeden Objekts

Ein besseres Verständnis der in Campaign integrierten Tabellen und ihrer Interaktion finden Sie in [diesem Abschnitt](datamodel.md).

>[!CAUTION]
>
>Einige integrierte Campaign-Schemata verfügen über ein verknüpftes Schema in der Cloud-Datenbank. Diese Schemata werden durch den Namespace **Xxl** identifiziert und dürfen nicht geändert oder erweitert werden.

## Syntax von Schemata {#syntax-of-schemas}

Das Stammelement des Schemas ist **`<srcschema>`**. Sie enthält die Unterelemente **`<element>`** und **`<attribute>`** .

Das erste Unterelement **`<element>`** entspricht dem Stamm der Entität.

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">  
    <attribute name="lastName"/>
    <attribute name="email"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

>[!NOTE]
>
>Das Stammelement der Entität hat denselben Namen wie das Schema.

![](assets/schema_and_entity.png)

Die **`<element>`** -Tags definieren die Namen der Entitätselemente. **`<attribute>`** -Tags des Schemas definieren die Namen der Attribute in den  **`<element>`** Tags, mit denen sie verknüpft wurden.

## Identifizierung eines Schemas {#identification-of-a-schema}

Ein Datenschema wird durch seinen Namen und seinen Namespace identifiziert.

Mit einem Namespace können Sie eine Gruppe von Schemas nach Interessensgebieten gruppieren. Beispielsweise wird der Namespace **cus** für kundenspezifische Konfigurationen (**Kunden**) verwendet.

>[!CAUTION]
>
>Standardmäßig muss der Name des Namespace kurz sein und darf nur autorisierte Zeichen gemäß den XML-Benennungsregeln enthalten.
>
>Kennungen dürfen nicht mit numerischen Zeichen beginnen.

## Reservierte Namespaces {#reserved-namespaces}

Bestimmte Namespaces sind Beschreibungen der Systementitäten vorbehalten, die für den Betrieb der Adobe Campaign-Anwendung erforderlich sind. Der folgende Namespace **darf nicht** verwendet werden, um ein neues Schema in einer Kombination aus Groß-/Kleinschreibung zu identifizieren:

* **xxl**: für Cloud-Datenbankschemata reserviert
* **xtk**: reserviert für Plattformsystemdaten
* **nl**: der allgemeinen Verwendung des Antrags vorbehalten sind
* **nms**: Sendungen vorbehalten (Empfänger, Versand, Tracking etc.)
* **ncm**: Content Management vorbehalten
* **temp**: für temporäre Schemata reserviert
* **crm**: für CRM-Connectoren-Integration reserviert

Der Identifikationsschlüssel eines Schemas ist eine Zeichenfolge, die mithilfe des Namespace und des Namens (durch einen Doppelpunkt getrennt) erstellt wird. Beispiel: **nms:recipient**.

## Erstellen oder Erweitern von Campaign-Schemata {#create-or-extend-schemas}

Um ein Feld oder ein anderes Element zu einem der Kerndatenschemata in Campaign hinzuzufügen, z. B. die Empfängertabelle (nms:recipient), müssen Sie dieses Schema erweitern.

[!DNL :bulb:] Weitere Informationen hierzu finden Sie unter  [Schema erweitern](extend-schema.md).

Um einen völlig neuen Datentyp hinzuzufügen, der in Adobe Campaign nicht vorhanden ist (z. B. eine Vertragstabelle), können Sie direkt ein benutzerdefiniertes Schema erstellen.

[!DNL :bulb:] Weitere Informationen hierzu finden Sie unter  [Neues Schema erstellen](create-schema.md).

![](assets/schemaextension_1.png)


Nachdem Sie ein Schema für die Verwendung erstellt oder erweitert haben, empfiehlt es sich, seine XML-Inhaltselemente in der Reihenfolge zu definieren, in der sie unten aufgeführt sind.

## Auflistungen {#enumerations}

Auflistungen werden zuerst definiert, und zwar vor dem Hauptelement des Schemas. Sie ermöglichen es, Werte in einer Liste anzuzeigen, um die Optionen zu beschränken, die der Benutzer für ein bestimmtes Feld hat.

Beispiel:

```
<enumeration basetype="byte" name="exTransactionTypeEnum" default="store">
<value label="Website" name="web" value="0"/>
<value label="Call Center" name="phone" value="1"/>
<value label="In Store" name="store" value="2"/>
</enumeration>
```

Bei der Definition von Feldern kann diese Auflistung dann wie folgt verwendet werden:

```
<attribute desc="Type of Transaction" label="Transaction Type" name="transactionType" 
type="string" enum="exTransactionTypeEnum"/>
```

>[!NOTE]
>
>Sie können auch von Benutzern verwaltete Auflistungen verwenden (normalerweise unter **[!UICONTROL Administration]** > **[!UICONTROL Plattform]** ), um die Werte für ein bestimmtes Feld anzugeben. Hierbei handelt es sich um globale Auflistungen, die eine bessere Wahl dafür bieten, ob Ihre Auflistung außerhalb des spezifischen Schemas verwendet werden kann, in dem Sie arbeiten.

## Schlüssel {#keys}

Jede Tabelle muss über mindestens einen Schlüssel verfügen. Oft wird sie im Hauptelement des Schemas automatisch mithilfe des Attributs **@autouid=true** erstellt, das auf &quot;true&quot;gesetzt ist.

Der Primärschlüssel kann auch mithilfe des Attributs **internal** definiert werden.

Beispiel:

```
<key name="householdId" internal="true">
  <keyfield xpath="@householdId"/>
</key>
```

In diesem Beispiel wird anstelle des Attributs **@autouuid** ein standardmäßiger Primärschlüssel mit dem Namen &quot;id&quot;angegeben, den wir für unsere eigene &quot;budgetId&quot;verwenden.

>[!CAUTION]
>
>Beim Anlegen eines neuen Schemas oder bei einer Schema-Erweiterung müssen Sie für das gesamte Schema den gleichen Wert für die Primärschlüsselfolge (@pkSequence) beibehalten.

[!DNL :bulb:] Weitere Informationen zu Schlüsseln finden Sie in  [diesem Abschnitt](database-mapping.md#management-of-keys).

## Attribute (Felder) {#attributes--fields-}

Mithilfe von Attributen können Sie die Felder definieren, aus denen sich Ihr Datenobjekt zusammensetzt. Sie können die Schaltfläche **[!UICONTROL Einfügen]** in der Symbolleiste zur Schemabearbeitung verwenden, um leere Attributvorlagen in Ihre XML-Datei zu ziehen, wo sich der Cursor befindet. Weiterführende Informationen finden Sie in diesem [Abschnitt](create-schema.md).

![](assets/schemaextension_2.png)

Die vollständige Liste der Attribute finden Sie im Abschnitt `<attribute>` Element in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/attribute.html?lang=en#content-model). Im Folgenden finden Sie einige der am häufigsten verwendeten Attribute: **@advanced**, **@dataPolicy**, **@default**, **@desc**, **@enum**, **@expr**, **label a13/>,**@length **,**@name **,**@notNull **,**@required **,**@ref&lt;a2 3/>, **@xml**, **@type**.****

:[!DNL :arrow_upper_right:]: Weitere Informationen zu den einzelnen Attributen finden Sie in der Attributbeschreibung in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic).

### Beispiele      {#examples}

Beispiel für die Definition eines Standardwert:

```
<attribute name="transactionDate" label="Transaction Date" type="datetime" default="GetDate()"/>
```

Beispiel für die Verwendung eines allgemeinen Attributs als Vorlage für ein ebenfalls als Pflichtfeld gekennzeichnetes Feld:

```
<attribute name="mobile" label="Mobile" template="nms:common:phone" required="true" />
```

Beispiel eines berechneten Felds, das mit dem Attribut **@advanced** ausgeblendet wird:

```
<attribute name="domain" label="Email domain" desc="Domain of recipient email address" expr="GetEmailDomain([@email])" advanced="true" />
```

Beispiel eines XML-Felds, das auch in einem SQL-Feld gespeichert ist und das das Attribut **@dataPolicy** aufweist.

```
<attribute name="secondaryEmail" label="Secondary email address" length="100" xml="true" sql="true" dataPolicy="email" />
```

>[!CAUTION]
>
>Obwohl die meisten Attribute mit einer Kardinalität von 1 bis 1 mit einem physischen Feld der Datenbank verknüpft sind, ist dies nicht für die XML-Felder oder die berechneten Felder der Fall.\
>Ein XML-Feld wird in einem Memofeld (&quot;mData&quot;) der Tabelle gespeichert.\
>Ein berechnetes Feld wird jedoch bei jedem Start einer Abfrage dynamisch erstellt und existiert daher nur auf der Anwendungsebene.

## Relationen {#links}

Links sind einige der letzten Elemente im Hauptelement Ihres Schemas. Sie definieren, wie sich alle verschiedenen Schemas in Ihrer Instanz miteinander vergleichen.

Die Relationen werden im Schema deklariert, das den **Fremdschlüssel** der Tabelle enthält, mit der sie verknüpft sind.

Es gibt drei Arten von Kardinalität: 1-1, 1-N und N-N. Es ist der 1-N-Typ, der standardmäßig verwendet wird.

### Beispiele {#examples-1}

Beispiel einer 1:n-Relation zwischen der Empfängertabelle (natives Schema) und einer Tabelle mit benutzerdefinierten Transaktionen:

```
<element label="Recipient" name="lnkRecipient" revLink="lnkTransactions" target="nms:recipient" type="link"/>
```

Beispiel einer 1:1-Relation zwischen einem benutzerdefinierten Schema &quot;Auto&quot; (im Namespace &quot;cus&quot;) und der Empfängertabelle:

```
<element label="Car" name="lnkCar" revCardinality="single" revLink="recipient" target="cus:car" type="link"/>
```

Beispiel eines externen Joins zwischen der Empfängertabelle und einer Adresstabelle basierend auf der E-Mail-Adresse und nicht auf einem Primärschlüssel:

```
<element name="emailInfo" label="Email Info" revLink="recipient" target="nms:address" type="link" externalJoin="true">
  <join xpath-dst="@address" xpath-src="@email"/>
</element>
```

Hier entspricht &quot;xpath-dst&quot;dem Primärschlüssel im Zielschema und &quot;xpath-src&quot; dem Fremdschlüssel im Quellschema.

## Audit-Protokoll {#audit-trail}

Ein nützliches Element, das Sie am unteren Rand des Schemas einfügen können, ist ein Tracking-Element (Audit-Protokoll).

Verwenden Sie das folgende Beispiel, um Felder zum Erstellungsdatum, zum Benutzer, der die Daten erstellt hat, zum Datum und zum Autor der letzten Änderung für alle Daten in Ihrer Tabelle einzuschließen:

```
<element aggregate="xtk:common:auditTrail" name="auditTrail"/>
```

## Datenbankstruktur aktualisieren {#updating-the-database-structure}

Sobald Ihre Änderungen abgeschlossen und gespeichert sind, müssen alle Änderungen, die sich auf die SQL-Struktur auswirken können, auf die Datenbank angewendet werden. Verwenden Sie dazu den Datenbankaktualisierungs-Assistenten.

![](assets/schemaextension_3.png)

Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](update-database-structure.md).

>[!NOTE]
>
>Wenn Änderungen keine Auswirkungen auf die Datenbankstruktur haben, müssen Sie nur Schemas neu generieren. Wählen Sie dazu das zu aktualisierende(n) Schema(e) aus, klicken Sie mit der rechten Maustaste darauf und wählen Sie **[!UICONTROL Aktionen > Ausgewählte Schemas regenerieren... aus.]** .

