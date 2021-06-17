---
product: Adobe Campaign
title: Mapping der Campaign-Datenbank
description: Mapping der Campaign-Datenbank
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: ht
source-wordcount: '1463'
ht-degree: 100%

---

# Datenbank-Mapping{#database-mapping}

Das SQL-Mapping dieses Beispielschemas ergibt das folgende XML-Dokument:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">
  <enumeration basetype="byte" name="gender">    
    <value label="Not specified" name="unknown" value="0"/>    
    <value label="Male" name="male" value="1"/>    
    <value label="Female" name="female" value="2"/> 
  </enumeration>  

  <element name="recipient" sqltable="CusRecipient">    
    <attribute desc="Recipient e-mail address" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
    <attribute default="GetDate()" label="Date of creation" name="created" sqlname="tsCreated" type="datetime"/>    
    <attribute enum="gender" label="Gender" name="gender" sqlname="iGender" type="byte"/>    
    <element label="Location" name="location">      
      <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
    </element>  
  </element>
</schema>
```

## Beschreibung {#description}

Das Stammelement des Schemas lautet nicht mehr **`<srcschema>`**, sondern **`<schema>`**.

Dies führt zu einem anderen Dokument, das automatisch aus dem Quellschema generiert und schlicht als &quot;Schema&quot; bezeichnet wird. Dieses Schema wird von Adobe Campaign verwendet.

Die SQL-Namen werden automatisch anhand des Elementnamens und des Elementtyps bestimmt.

Die SQL-Benennungsregeln lauten wie folgt:

* Tabelle: Verkettung des Namespace und Namens des Schemas

   In diesem Beispiel wird der Tabellenname über das Hauptelement des Schemas im Attribut **sqltable** eingegeben:

   ```
   <element name="recipient" sqltable="CusRecipient">
   ```

* Feld: Name des Elements mit vorangestelltem Präfix, das nach Typ definiert wird (&quot;i&quot; für Integer, &quot;d&quot; für Dublette, &quot;s&quot; für String, &quot;ts&quot; für Datumsangaben usw.)

   Der Feldname wird über das Attribut **sqlname** für die verschiedenen Eingaben von **`<attribute>`** und **`<element>`** eingegeben:

   ```
   <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
   ```

>[!NOTE]
>
>SQL-Namen können aus dem Quellschema geladen werden. Füllen Sie dazu die Attribute &quot;sqltable&quot; oder &quot;sqlname&quot; für das betreffende Element aus.

Das SQL-Script zur Erstellung der aus dem erweiterten Schema generierten Tabelle lautet wie folgt:

```
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

In Bezug auf SQL-Felder gelten folgende Einschränkungen:

* In numerischen und Datumsfeldern sind keine Nullwerte zulässig.
* Numerische Felder werden auf 0 initialisiert.

## XML-Felder {#xml-fields}

Standardmäßig werden alle eingegebenen **`<attribute>`**- und **`<element>`**-Elemente einem SQL-Schema der Datentabelle zugeordnet. Sie können dieses Feld jedoch anstatt in SQL auch in XML referenzieren. Das bedeutet, dass die Daten in einem Memo-Feld (&quot;mData&quot;) der Tabelle gespeichert werden, in der Werte aller XML-Felder enthalten sind. Als Speicher dieser Daten fungiert ein XML-Dokument, das die Struktur des Schemas beibehält.

Um ein Feld in XML auszufüllen, müssen Sie dem betreffenden Element das Attribut **xml** mit dem Wert &quot;true&quot; hinzufügen.

**Beispiel**: Im Folgenden finden Sie zwei Beispiele für die Verwendung von XML-Feldern.

* Mehrzeiliges Kommentarfeld:

   ```
   <element name="comment" xml="true" type="memo" label="Comment"/>
   ```

* Beschreibung der Daten im HTML-Format:

   ```
   <element name="description" xml="true" type="html" label="Description"/>
   ```

   Über den Typ &quot;html&quot; können Sie HTML-Inhalte in einem CDATA-Tag speichern und eine spezielle HTML-Bearbeitungsprüfung in der Benutzeroberfläche des Adobe Campaign-Clients anzeigen.

Bei Verwendung von XML-Feldern ist das Hinzufügen von Feldern ohne Anpassungen der physischen Struktur der Datenbank möglich. Ein weiterer Vorteil besteht darin, dass weniger Ressourcen benötigt werden (SQL-Feldern zugewiesene Größe, Anzahl der Felder pro Tabelle usw.).

## Schlüsselverwaltung {#management-of-keys}

Eine Tabelle muss mindestens einen Schlüssel zur Identifizierung eines Datensatzes in der Tabelle beinhalten.

Ein Schlüssel wird über das Hauptelement des Datenschemas deklariert.

```
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

Für Schlüssel gelten folgende Regeln:

* Ein Schlüssel kann auf ein oder mehrere Felder in der Tabelle verweisen.
* Ein Schlüssel wird als &quot;primary&quot; (primär) (oder &quot;priority&quot; (Priorität)) bezeichnet, wenn an erster Stelle im auszufüllenden Schema steht oder das Attribut **internal** (intern) mit dem Wert &quot;true&quot; enthält.

**Beispiel**:

* Hinzufügen eines Schlüssels zur E-Mail-Adresse und zum Ort:

   ```
   <srcSchema name="recipient" namespace="cus">
     <element name="recipient">
       <key name="email">
         <keyfield xpath="@email"/> 
         <keyfield xpath="location/@city"/> 
       </key>
   
       <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
       <element name="location" label="Location">
         <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
       </element>
     </element>
   </srcSchema>
   ```

   Generiertes Schema:

   ```
   <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
     <element name="recipient" sqltable="CusRecipient">    
      <key name="email">      
       <keyfield xpath="@email"/>      
       <keyfield xpath="location/@city"/>    
      </key>    
   
      <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
      <element label="Location" name="location">      
        <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
      </element>  
     </element>
   </schema>
   ```

* Hinzufügen eines primären oder internen Schlüssels zum Namensfeld &quot;id&quot;:

   ```
   <srcSchema name="recipient" namespace="cus">
     <element name="recipient">
       <key name="id" internal="true">
         <keyfield xpath="@id"/> 
       </key>
   
       <key name="email">
         <keyfield xpath="@email"/> 
       </key>
   
       <attribute name="id" type="long" label="Identifier"/>
       <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
     </element>
   </srcSchema>
   ```

   Generiertes Schema:

   ```
   <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
     <element name="recipient" sqltable="CusRecipient">    
       <key name="email">      
         <keyfield xpath="@email"/>    
       </key>  
   
       <key internal="true" name="id">      
        <keyfield xpath="@id"/>    
       </key>    
   
       <attribute label="Identifier" name="id" sqlname="iRecipientId" type="long"/>    
       <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>  
     </element>
   </schema>
   ```

### Primärschlüssel – Kennung

Adobe Campaign-Tabellen verwenden als Primärschlüssel eine **Universally Unique ID (UUID)**, die automatisch von der Datenbank-Engine generiert wird. Der Schlüsselwert ist in der gesamten Datenbank eindeutig. Der Inhalt des Schlüssels wird beim Einfügen des Datensatzes automatisch generiert.

**Beispiel**

Deklarieren eines inkrementellen Schlüssels im Quellschema:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"  autopk="true" autouuid="true">
  ...
  </element>
</srcSchema>
```

Generiertes Schema:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient"  autopk="true" autouuid="true" sqltable="CusRecipient"> 

    <key internal="true" name="id">
      <keyfield xpath="@id"/>
    </key>

    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iRecipientId" type="long"/>
  </element>
</schema>
```

Zusätzlich zur Definition des Schlüssels wurde dem erweiterten Schema ein numerisches Feld namens &quot;id&quot; hinzugefügt, das den automatisch generierten Primärschlüssel enthält.

>[!CAUTION]
>
>Ein Datensatz mit einem auf 0 gesetzten Primärschlüssel wird bei der Erstellung der Tabelle automatisch eingefügt. Durch die Verwendung dieses Datensatzes werden äußere Joins vermieden, die sich bei Volumentabellen als nicht effektiv erweisen. Standardmäßig werden alle Fremdschlüssel mit dem Wert 0 initialisiert. Auf diese Weise kann beim Join immer ein Ergebnis zurückgegeben werden, wenn das Datenelement nicht ausgefüllt wird.

## Relationen: Beziehungen zwischen Tabellen {#links--relation-between-tables}

Eine Relation beschreibt die Zuordnung einer Tabelle zu einer anderen.

Es gibt verschiedene Typen von Zuordnungen (auch &quot;Kardinalitäten&quot; genannt), darunter:

* 1-1-Kardinalität: Eine Entität in der Quelltabelle kann maximal mit einer Entität in der Zieltabelle in Beziehung stehen.
* 1-N-Kardinalität: Eine Entität in der Quelltabelle kann mit mehreren Entitäten in der Zieltabelle in Beziehung stehen, aber eine Entität in der Zieltabelle kann nur maximal mit einer Entität in der Quelltabelle in Beziehung stehen.
* N-N-Kardinalität: Eine Entität in der Quelltabelle kann mit mehreren Entitäten in der Zieltabelle in Beziehung stehen und umgekehrt.

In der Benutzeroberfläche sind die verschiedenen Beziehungstypen anhand ihrer Symbole leicht voneinander zu unterscheiden.

Für Join-Beziehungen mit einer Campaign-Tabelle/-Datenbank:

* ![](assets/do-not-localize/join_with_campaign11.png): 1-1-Kardinalität. Dies kann etwa eine Beziehung zwischen einem Empfänger und einer aktuellen Bestellung sein. Ein Empfänger kann jeweils nur mit einer Entität der aktuellen Tabelle zu Bestellungen verknüpft sein.
* ![](assets/do-not-localize/externaljoin11.png): 1-1-Kardinalität, externer Join. Dies kann etwa eine Beziehung zwischen einem Empfänger und dem ihm zugehörigen Land sein. Ein Empfänger kann nur mit einer Entität der Ländertabelle verknüpft sein. Der Inhalt der Ländertabelle wird nicht gespeichert.
* ![](assets/do-not-localize/join_with_campaign1n.png): 1-N-Kardinalität. Dies kann etwa eine Beziehung zwischen einem Empfänger und der Tabelle zu Abonnements sein. Ein Empfänger kann mit mehreren Entitäten in der Tabelle zu Abonnements verknüpft sein.

Für Join-Beziehungen mit Federated Database Access:

* ![](assets/do-not-localize/join_fda_11.png): 1-1-Kardinalität
* ![](assets/do-not-localize/join_fda_1m.png): 1-N-Kardinalität

[!DNL :bulb:] Weitere Informationen zu FDA-Tabellen finden Sie unter [Federated Data Access](../connect/fda.md).

In dem Schema, das den Fremdschlüssel der Tabelle enthält, muss über das Hauptelement eine Relation angegeben werden:

```
<element name="name_of_link" type="link" target="key_of_destination_schema">
  <join xpath-dst="xpath_of_field1_destination_table" xpath-src="xpath_of_field1_source_table"/>
  <join xpath-dst="xpath_of_field2_destination_table" xpath-src="xpath_of_field2_source_table"/>
  ...
</element>
```

Für Relationen gelten folgende Regeln:

* Die Definition einer Relation erfolgt über den Typ **link** für **`<element>`**, wobei folgende Attributen eingegeben werden:

   * **name**: Name der Relation aus der Quelltabelle
   * **target**: Name des Zielschemas
   * **label**: Bezeichnung der Relation
   * **revLink** (optional): Name des Umkehrlinks aus dem Zielschema (wird standardmäßig automatisch abgeleitet)
   * **integrity** (optional): Referenzintegrität der Entität der Quelltabelle zur Entität der Zieltabelle. Hierfür sind folgende Werte möglich:

      * **define**: Es ist möglich, die Quellentität zu löschen, wenn diese nicht mehr durch eine Zielentität referenziert wird.
      * **normal**: Durch Löschen der Quellentität werden die Schlüssel der Relation zur Zielentität initialisiert (Standardmodus). Bei diesem Integritätstyp werden alle Fremdschlüssel initialisiert.
      * **own**: Durch Löschen der Quellentität wird auch die Zielentität gelöscht.
      * **owncopy**: Führt die gleiche Operation aus wie **own** (beim Löschen) bzw. dupliziert die Entitäten (bei Duplizierung).
      * **neutral**: Führt keine Operation aus.
   * **revIntegrity** (optional): Integrität im Zielschema (optional, Standardwert ist &quot;normal&quot;)
   * **revCardinality** (optional): Mit dem Wert &quot;single&quot; wird die Kardinalität mit dem Typ 1-1 ausgefüllt (standardmäßig 1-N).
   * **externalJoin** (optional): Erzwingt den äußeren Join.
   * **revExternalJoin** (optional): Erzwingt den äußeren Join am Umkehr-Link.


* Eine Relation referenziert ein oder mehrere Felder aus der Quelltabelle mit der Zieltabelle. Die Felder, aus denen sich der Join zusammensetzt (`<join>`-Element), müssen nicht ausgefüllt werden, da sie standardmäßig aus dem internen Schlüssel des Zielschemas abgeleitet werden.
* Eine Relation setzt sich aus zwei Halb-Relationen zusammen, wobei die erste über das Quellschema deklariert und die zweite automatisch im erweiterten Schema des Zielschemas erstellt wird.
* Ein Join kann ein äußerer Join sein, wenn das Attribut **externalJoin** mit dem Wert &quot;true&quot; hinzugefügt wird (unterstützt in PostgreSQL).

>[!NOTE]
>
>Relation sind die am Ende des Schemas deklarierten Elemente.

### Beispiel 1 {#example-1}

1-N-Beziehung zur Schematabelle &quot;cus:company&quot;:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    ...
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

Generiertes Schema:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    ...
    <element label="Company" name="company" revLink="recipient" target="cus:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of 'Company' link (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

Die Definition der Relation wird ergänzt durch die Felder, aus denen sich die Relation zusammensetzt: der Primärschlüssel mit XPath (&quot;@id&quot;) im Zielschema und der Fremdschlüssel mit XPath (&quot;@company-id&quot;) im Schema.

Der Fremdschlüssel wird automatisch in einem Element hinzugefügt, das dieselben Eigenschaften wie das zugehörige Feld in der Zieltabelle verwendet. Die Benennungskonvention hierfür lautet wie folgt: Name des Zielschemas gefolgt vom Namen des zugehörigen Felds (in diesem Beispiel &quot;company-id&quot;).

Erweitertes Zielgruppenschema (&quot;cus:company&quot;):

```
<schema mappingType="sql" name="company" namespace="cus" xtkschema="xtk:schema">  
  <element name="company" sqltable="CusCompany"  autopk="true" autouuid="true"> 
    <key internal="true" name="id">      
      <keyfield xpath="@id"/>    
    </key>
    ...
    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iCompanyId" type="long"/>
    ...
    <element belongsTo="cus:recipient" integrity="define" label="Contact" name="recipient" revLink="company" target="nms:recipient" type="link" unbound="true">      
      <join xpath-dst="@company-id" xpath-src="@id"/>    
    </element>
  </element>
</schema>
```

Ein Umkehrlink zur Tabelle &quot;cus:recipient&quot; wurde mit folgenden Parametern hinzugefügt:

* **name**: wird automatisch vom Namen des Quellschemas abgeleitet (kann mit dem Attribut &quot;revLink&quot; in der Definition der Relation im Quellschema erzwungen werden)
* **revLink**: Name des Umkehr-Links
* **target**: Schlüssel des verknüpften Schemas (Schema &quot;cus:recipient&quot;)
* **unbound**: Relation wird als Kollektionselement für eine 1-N-Kardinalität deklariert (standardmäßig)
* **integrity**: Standardwert ist &quot;define&quot; (kann mit dem Attribut &quot;revIntegrity&quot; in der Definition der Relation im Quellschema erzwungen werden)

### Beispiel 2 {#example-2}

In diesem Beispiel wird eine Relation zur Schematabelle &quot;nms:address&quot; deklariert. Der Join ist ein äußerer Join und wird explizit mit der E-Mail-Adresse des Empfängers und dem Feld &quot;@address&quot; der verknüpften Tabelle (&quot;nms:address&quot;) ausgefüllt.

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"> 
    ...
    <element integrity="neutral" label="Info about email" name="emailInfo" revIntegrity="neutral" revLink="recipient" target="nms:address" type="link" externalJoin="true">      
      <join xpath-dst="@address" xpath-src="@email"/>
    </element>
  </element>
</srcSchema>
```

### Beispiel 3 {#example-3}

1-1-Beziehung zur Schematabelle &quot;cus:extension&quot;:

```
<element integrity="own" label="Extension" name="extension" revCardinality="single" revLink="recipient" target="cus:extension" type="link"/>
```

### Beispiel 4 {#example-4}

Relation zu einem Ordner (Schema &quot;xtk:folder&quot;):

```
<element default="DefaultFolder('nmsFolder')" label="Folder" name="folder" revDesc="Recipients in the folder" revIntegrity="own" revLabel="Recipients" target="xtk:folder" type="link"/>
```

Der Standardwert gibt die Kennung der ersten qualifizierten Parametertypdatei zurück, die in der Funktion &quot;DefaultFolder(&#39;nmsFolder&#39;)&quot; eingegeben wurde.

### Beispiel 5 {#example-5}

In diesem Beispiel wird ein Schlüssel für eine Relation (Schema &quot;company&quot; zu Schema &quot;cus:company&quot;) mit dem Attribut **xlink** und einem Feld der Tabelle (&quot;email&quot;) erstellt:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <key name="companyEmail"> 
      <keyfield xpath="@email"/>
      <keyfield xlink="company"/>
    </key>
    
    <attribute name="email" type="string" length="80" label="Email" desc="Recipient email"/>
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

Generiertes Schema:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    <key name="companyEmail">      
      <keyfield xpath="@email"/>      
      <keyfield xpath="@company-id"/>    
    </key>

    <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>
    <element label="Company" name="company" revLink="recipient" target="sfa:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of link 'Company' (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

Die Definition des Namensschlüssels &quot;companyEmail&quot; wurde um den Fremdschlüssel der Relation &quot;company&quot; erweitert.
