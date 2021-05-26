---
solution: Campaign v8
product: Adobe Campaign
title: Campaign-Datenbank-Mapping
description: Campaign-Datenbank-Mapping
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '1463'
ht-degree: 0%

---

# Datenbank-Mapping{#database-mapping}

Die SQL-Zuordnung unseres Beispielschemas liefert das folgende XML-Dokument:

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

## Beschreibung  {#description}

Das Stammelement des Schemas ist nicht mehr **`<srcschema>`**, sondern **`<schema>`**.

Dadurch gelangen wir zu einem anderen Dokumenttyp, der automatisch aus dem Quellschema generiert wird, das einfach als Schema bezeichnet wird. Dieses Schema wird von der Adobe Campaign-Anwendung verwendet.

Die SQL-Namen werden automatisch anhand von Elementname und -typ bestimmt.

Die SQL-Benennungsregeln lauten wie folgt:

* table: Verkettung des Schema-Namespace und -Namens

   In unserem Beispiel wird der Name der Tabelle über das Hauptelement des Schemas im Attribut **sqltable** eingegeben:

   ```
   <element name="recipient" sqltable="CusRecipient">
   ```

* -Feld: Name des Elements, dem ein Präfix vorangestellt ist, das entsprechend dem Typ (&#39;i&#39; für Integer, &#39;d&#39; für Dublette, &#39;s&#39; für String, &#39;ts&#39; für Datumsangaben usw.) definiert wurde

   Der Feldname wird über das Attribut **sqlname** für jeden eingegebenen **`<attribute>`** und **`<element>`** eingegeben:

   ```
   <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
   ```

>[!NOTE]
>
>SQL-Namen können aus dem Quellschema überschrieben werden. Füllen Sie dazu die Attribute &quot;sqltable&quot;oder &quot;sqlname&quot;für das betroffene Element aus.

Das SQL-Skript zum Erstellen der aus dem erweiterten Schema generierten Tabelle stellt sich wie folgt dar:

```
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

Die SQL-Feldbeschränkungen lauten wie folgt:

* keine Nullwerte in numerischen und Datumsfeldern,
* numerische Felder werden auf 0 initialisiert.

## XML-Felder {#xml-fields}

Standardmäßig werden alle eingegebenen **`<attribute>`** - und **`<element>`** -Elemente einem SQL-Feld der Datenschematabelle zugeordnet. Sie können dieses Feld jedoch in XML anstelle von SQL referenzieren, was bedeutet, dass die Daten in einem Memofeld (&quot;mData&quot;) der Tabelle gespeichert sind, das die Werte aller XML-Felder enthält. Die Speicherung dieser Daten ist ein XML-Dokument, das die Schemastruktur einhält.

Um ein Feld in XML auszufüllen, müssen Sie dem betreffenden Element das Attribut **xml** mit dem Wert &quot;true&quot;hinzufügen.

**Beispiel**: Hier finden Sie zwei Beispiele für die Verwendung von XML-Feldern.

* Mehrzeiliges Kommentarfeld:

   ```
   <element name="comment" xml="true" type="memo" label="Comment"/>
   ```

* Beschreibung der Daten im HTML-Format:

   ```
   <element name="description" xml="true" type="html" label="Description"/>
   ```

   Mit dem HTML-Typ können Sie den HTML-Inhalt in einem CDATA-Tag speichern und eine spezielle HTML-Bearbeitungsprüfung in der Adobe Campaign-Clientschnittstelle anzeigen.

Mithilfe von XML-Feldern können Felder hinzugefügt werden, ohne dass die physische Struktur der Datenbank geändert werden muss. Ein weiterer Vorteil besteht darin, dass Sie weniger Ressourcen verwenden (Größe für SQL-Felder, Anzahl der Felder pro Tabelle usw.).

## Schlüsselverwaltung {#management-of-keys}

Eine Tabelle muss über mindestens einen Schlüssel zur Identifizierung eines Datensatzes in der Tabelle verfügen.

Ein Schlüssel wird aus dem Hauptelement des Datenschemas deklariert.

```
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

Die Schlüssel folgen den folgenden Regeln:

* Ein Schlüssel kann auf ein oder mehrere Felder in der Tabelle verweisen.
* Ein Schlüssel wird als &quot;primär&quot;(oder &quot;Priorität&quot;) bezeichnet, wenn er der erste im Schema ist, der ausgefüllt werden soll, oder wenn er das Attribut **internal** mit dem Wert &quot;true&quot;enthält.

**Beispiel**:

* Hinzufügen eines Schlüssels zur E-Mail-Adresse und Stadt:

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

   Das generierte Schema:

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

* Hinzufügen eines Primärschlüssels oder eines internen Schlüssels im Feld &quot;id&quot;-Name:

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

   Das generierte Schema:

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

### Primärer Schlüssel - Kennung

Der Primärschlüssel der Adobe Campaign-Tabellen ist eine von der Datenbank-Engine automatisch generierte **Universally Unique ID (UUID)**. Der Schlüsselwert ist in der gesamten Datenbank eindeutig. Der Inhalt des Schlüssels wird beim Einfügen des Datensatzes automatisch erzeugt.

**Beispiel**

Deklarieren eines inkrementellen Schlüssels im Quellschema:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient" autouuid="true">
  ...
  </element>
</srcSchema>
```

Das generierte Schema:

```
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" autouuid="true" sqltable="CusRecipient"> 

    <key internal="true" name="id">
      <keyfield xpath="@id"/>
    </key>

    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iRecipientId" type="long"/>
  </element>
</schema>
```

Zusätzlich zur Definition des Schlüssels wurde dem erweiterten Schema ein numerisches Feld namens &quot;id&quot;hinzugefügt, das den automatisch generierten Primärschlüssel enthält.

>[!CAUTION]
>
>Ein Datensatz mit einem Primärschlüssel, der auf 0 gesetzt ist, wird bei der Erstellung der Tabelle automatisch eingefügt. Dieser Datensatz wird verwendet, um äußere Joins zu vermeiden, die in Volumentabellen nicht wirksam sind. Standardmäßig werden alle Fremdschlüssel mit dem Wert 0 initialisiert, sodass beim Join immer ein Ergebnis zurückgegeben werden kann, wenn das Datenelement nicht ausgefüllt wird.

## Links: Relation zwischen Tabellen {#links--relation-between-tables}

Eine Relation beschreibt die Verbindung zwischen einer Tabelle und einer anderen.

Die verschiedenen Arten von Assoziationen (auch Kardinalität genannt) sind:

* Kardinalität 1-1: Eine Entität in der Quelltabelle kann maximal eine Entität in der Zieltabelle enthalten.
* Kardinalität 1-N: Eine Entität in der Quelltabelle kann mit mehreren Entitäten in der Zieltabelle in Beziehung stehen, aber eine Entität in der Zieltabelle kann maximal mit einer Entität in der Quelltabelle in Beziehung stehen.
* Kardinalität N-N: Eine Entität in der Quelltabelle kann mehrere Entitäten aufweisen, die der Zieltabelle entsprechen, und umgekehrt.

In der Benutzeroberfläche können Sie die verschiedenen Relationstypen durch ihre Symbole leicht unterscheiden.

Für Verknüpfungen mit einer Kampagnentabelle/-Datenbank:

* ![](assets/do-not-localize/join_with_campaign11.png) : Kardinalität 1-1. Beispielsweise zwischen einem Empfänger und einer aktuellen Bestellung. Ein Empfänger kann jeweils nur mit einer Entität in der aktuellen Bestelltabelle verknüpft sein.
* ![](assets/do-not-localize/externaljoin11.png) : Kardinalität 1-1, externer Join. Beispielsweise zwischen einem Empfänger und seinem Land. Ein Empfänger kann nur mit einer Entität im Tabellenland verbunden sein. Der Inhalt der Ländertabelle wird nicht gespeichert.
* ![](assets/do-not-localize/join_with_campaign1n.png) : Kardinalität 1-N. Beispielsweise zwischen einem Empfänger und der Abonnementtabelle. Ein Empfänger kann sich auf mehrere Ereignisse in der Abonnementtabelle beziehen.

Für Verknüpfungsrelationen mit Federated Database Access:

* ![](assets/do-not-localize/join_fda_11.png) : Kardinalität 1-1
* ![](assets/do-not-localize/join_fda_1m.png) : Kardinalität 1-N

[!DNL :bulb:] Weitere Informationen zu FDA-Tabellen finden Sie unter  [Federated Data Access](../connect/fda.md).

Eine Relation muss im Schema deklariert werden, das den Fremdschlüssel der über das Hauptelement verknüpften Tabelle enthält:

```
<element name="name_of_link" type="link" target="key_of_destination_schema">
  <join xpath-dst="xpath_of_field1_destination_table" xpath-src="xpath_of_field1_source_table"/>
  <join xpath-dst="xpath_of_field2_destination_table" xpath-src="xpath_of_field2_source_table"/>
  ...
</element>
```

Links folgen den folgenden Regeln:

* Die Definition eines Links wird in einem **Link**-Typ **`<element>`** mit den folgenden Attributen eingegeben:

   * **name**: Name des Links aus der Quelltabelle,
   * **target**: Name des Zielschemas,
   * **label**: Titel des Links,
   * **revLink**  (optional): Name des Rückwärtslinks aus dem Zielschema (standardmäßig automatisch abgezogen),
   * **integrität**  (optional): referenzielle Integrität des Vorkommens der Quelltabelle zum Vorkommen der Zieltabelle. Mögliche Werte sind:

      * **definieren**: das Auftreten der Quelle kann gelöscht werden, wenn es nicht mehr durch ein Zielereignis referenziert wird;
      * **normal**: Beim Löschen des Vorkommens der Quelle werden die Schlüssel des Links zum Vorkommen der Zielgruppe initialisiert (Standardmodus). Dieser Integritätstyp initialisiert alle Fremdschlüssel.
      * **own**: Das Löschen des Vorkommens der Quelle führt zum Löschen des Vorkommens der Zielgruppe,
      * **owncopy**: identisch mit  **own**  (im Fall des Löschens) oder dupliziert die Vorkommnisse (im Fall von Duplizierung),
      * **neutral**: nichts tut.
   * **revIntegrity**  (optional): Integrität des Zielschemas (optional, standardmäßig &quot;normal&quot;),
   * **revCardinality**  (optional): mit dem Wert &quot;single&quot;füllt die Kardinalität mit Typ 1-1 (standardmäßig 1-N).
   * **externalJoin**  (optional): erzwingt den äußeren Join
   * **revExternalJoin**  (optional): erzwingt den äußeren Join auf dem Rückwärtslink.


* Eine Verknüpfung referenziert ein oder mehrere Felder aus der Quelltabelle in die Zieltabelle. Die Felder, aus denen der Join besteht ( `<join>` -Element), müssen nicht ausgefüllt werden, da sie standardmäßig mithilfe des internen Schlüssels des Zielschemas automatisch abgezogen werden.
* Eine Relation besteht aus zwei Halblinks, wobei die erste aus dem Quellschema deklariert und die zweite automatisch im erweiterten Schema des Zielschemas erstellt wird.
* Ein Join kann ein äußeren Join sein, wenn das Attribut **externalJoin** hinzugefügt wird, mit dem Wert &quot;true&quot;(unterstützt in PostgreSQL).

>[!NOTE]
>
>Links sind die Elemente, die am Ende des Schemas deklariert werden.

### Beispiel 1 {#example-1}

1-N Relation zur Schema-Tabelle &quot;cus:Firma&quot;:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    ...
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

Das generierte Schema:

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

Die Linkdefinition wird durch die Felder ergänzt, aus denen der Join besteht, d. h. der Primärschlüssel mit seinem XPath (&quot;@id&quot;) im Zielschema und der Fremdschlüssel mit seinem XPath (&quot;@company-id&quot;) im Schema.

Der Fremdschlüssel wird automatisch in einem Element hinzugefügt, das dieselben Merkmale wie das zugehörige Feld in der Zieltabelle verwendet, mit der folgenden Namenskonvention: Name des Zielschemas gefolgt vom Namen des zugehörigen Felds (&quot;company-id&quot; in unserem Beispiel).

Erweitertes Schema der Zielgruppe (&quot;cus:Firma&quot;):

```
<schema mappingType="sql" name="company" namespace="cus" xtkschema="xtk:schema">  
  <element name="company" sqltable="CusCompany" autouuid="true"> 
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

Es wurde ein Umkehrlink zur Tabelle &quot;cus:recipient&quot;mit den folgenden Parametern hinzugefügt:

* **name**: automatisch vom Namen des Quellschemas abgezogen (kann mit dem Attribut &quot;revLink&quot;in der Linkdefinition im Quellschema erzwungen werden)
* **revLink**: Name des Reverse-Links
* **target**: Schlüssel des verknüpften Schemas ( Schema &quot;cus:recipient&quot;)
* **ungebunden**: Die Verknüpfung wird als Kollektionselement für eine 1:n-Kardinalität deklariert (standardmäßig)
* **Integrität**: &quot;define&quot; (kann standardmäßig mit dem Attribut &quot;revIntegrity&quot; in der Linkdefinition im Quellschema erzwungen werden).

### Beispiel 2 {#example-2}

In diesem Beispiel deklarieren wir einen Link zur Schematabelle &quot;nms:address&quot;. Der Join ist ein äußere Join und wird explizit mit der E-Mail-Adresse des Empfängers und dem Feld &quot;@address&quot; der verknüpften Tabelle (&quot;nms:address&quot;) ausgefüllt.

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

1-1 Relation zur Schemaschabelle &quot;cus:extension&quot;:

```
<element integrity="own" label="Extension" name="extension" revCardinality="single" revLink="recipient" target="cus:extension" type="link"/>
```

### Beispiel 4 {#example-4}

Link zu einem Ordner ( Schema &quot;xtk:folder&quot;):

```
<element default="DefaultFolder('nmsFolder')" label="Folder" name="folder" revDesc="Recipients in the folder" revIntegrity="own" revLabel="Recipients" target="xtk:folder" type="link"/>
```

Der Standardwert gibt die Kennung der ersten zulässigen Parametertyp-Datei zurück, die in der Funktion &quot;DefaultFolder(&#39;nmsFolder&#39;)&quot;eingegeben wurde.

### Beispiel 4 {#example-5}

In diesem Beispiel möchten wir einen Schlüssel für einen Link (&quot;company&quot; zum Schema &quot;cus:company&quot;) mit dem Attribut **xlink** und einem Feld der Tabelle (&quot;email&quot;) erstellen:

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

Das generierte Schema:

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

Die Definition des Namensschlüssels &quot;companyEmail&quot;wurde um den Fremdschlüssel der &quot;company&quot;-Relation erweitert.
