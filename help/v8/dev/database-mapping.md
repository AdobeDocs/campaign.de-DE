---
solution: Campaign
product: Adobe Campaign
title: Kampagne der Datenbankzuordnung
description: Kampagne der Datenbankzuordnung
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '1464'
ht-degree: 0%

---

# Datenbank-Mapping{#database-mapping}

Die SQL-Zuordnung unseres Beispiels Schema enthält das folgende XML-Dokument:

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

Das Stammelement des Schemas ist nicht mehr **`<srcschema>`**, sondern **`<schema>`**.

Dies führt uns zu einem anderen Dokument, das automatisch aus dem Quellcode-Schema generiert wird, das einfach als Schema bezeichnet wird. Dieses Schema wird von der Adobe Campaign-Anwendung verwendet.

Die SQL-Namen werden automatisch anhand des Elementnamens und des Elementtyps bestimmt.

Die SQL-Benennungsregeln lauten wie folgt:

* Tabelle: Verkettung des Schema-Namensraums und -Namens

   In unserem Beispiel wird der Tabellenname über das Hauptelement des Schemas im Attribut **sqltable** eingegeben:

   ```
   <element name="recipient" sqltable="CusRecipient">
   ```

* Feld: Name des Elements, dem ein Präfix vorangestellt wird, der nach Typ (&#39;i&#39; für Ganzzahl, &#39;d&#39; für Dublette, &#39;s&#39; für Zeichenfolge, &#39;ts&#39; für Datumsangaben usw.) definiert ist

   Der Feldname wird über das **sqlname**-Attribut für jede Eingabe von **`<attribute>`** und **`<element>`** eingegeben:

   ```
   <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
   ```

>[!NOTE]
>
>SQL-Namen können aus dem Quellcode-Schema überladen werden. Füllen Sie dazu die Attribute &quot;sqltable&quot;oder &quot;sqlname&quot;für das betreffende Element aus.

Das SQL-Skript zum Erstellen der aus dem erweiterten Schema generierten Tabelle lautet wie folgt:

```
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

Die SQL-Feldbeschränkungen lauten wie folgt:

* keine Nullwerte in numerischen und Datumsfeldern,
* Numerische Felder werden auf 0 initialisiert.

## XML-Felder {#xml-fields}

Standardmäßig werden alle eingegebenen **`<attribute>`**- und **`<element>`**-Elemente einem SQL-Schema der Datentabelle zugeordnet. Sie können dieses Feld jedoch in XML anstatt in SQL referenzieren. Das bedeutet, dass die Daten in einem Memofeld (&quot;mData&quot;) der Tabelle gespeichert werden, das die Werte aller XML-Felder enthält. Die Datenspeicherung dieser Daten ist ein XML-Dokument, das die Schema-Struktur einhält.

Um ein Feld in XML auszufüllen, müssen Sie dem betreffenden Element das Attribut **xml** mit dem Wert &quot;true&quot;hinzufügen.

**Beispiel**: Es gibt zwei Beispiele für die Verwendung von XML-Feldern.

* Mehrzeiliges Kommentarfeld:

   ```
   <element name="comment" xml="true" type="memo" label="Comment"/>
   ```

* Beschreibung der Daten im HTML-Format:

   ```
   <element name="description" xml="true" type="html" label="Description"/>
   ```

   Mit dem &quot;html&quot;-Typ können Sie HTML-Inhalte in einem CDATA-Tag speichern und eine spezielle HTML-Bearbeitungsprüfung in der Adobe Campaign-Client-Oberfläche anzeigen.

Mithilfe von XML-Feldern können Sie Felder hinzufügen, ohne die physische Struktur der Datenbank ändern zu müssen. Ein weiterer Vorteil besteht darin, dass Sie weniger Ressourcen verwenden (Größe den SQL-Feldern zugeordnet, Anzahl der Felder pro Tabelle usw.).

## Schlüsselverwaltung {#management-of-keys}

Eine Tabelle muss über mindestens einen Schlüssel zur Identifizierung eines Datensatzes in der Tabelle verfügen.

Ein Schlüssel wird aus dem Hauptelement des data-Schemas deklariert.

```
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

Schlüssel beachten die folgenden Regeln:

* Ein Schlüssel kann auf ein oder mehrere Felder in der Tabelle verweisen.
* Ein Schlüssel wird als &quot;primär&quot;(oder &quot;Priorität&quot;) bezeichnet, wenn er der erste im auszufüllenden Schema ist oder wenn er das Attribut **internal** mit dem Wert &quot;true&quot;enthält.

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

### Primär key - Identifier

Der Hauptschlüssel von Adobe Campaign-Tabellen ist eine **Universally Unique ID (UUID)**, die automatisch von der Datenbankmaschine generiert wird. Der Schlüsselwert ist in der gesamten Datenbank eindeutig. Der Inhalt des Schlüssels wird beim Einfügen des Datensatzes automatisch generiert.

**Beispiel**

Deklarieren eines inkrementellen Schlüssels im Quell-Schema:

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

Zusätzlich zur Schlüsseldefinition wurde dem erweiterten Schema ein numerisches Feld namens &quot;id&quot;hinzugefügt, um den automatisch generierten Primärschlüssel zu enthalten.

>[!CAUTION]
>
>Ein Datensatz mit einem Primärschlüssel auf 0 wird bei der Tabellenerstellung automatisch eingefügt. Dieser Datensatz wird verwendet, um äußere Verbindungen zu vermeiden, die bei Volumentabellen nicht wirksam sind. Standardmäßig werden alle Fremdschlüssel mit dem Wert 0 initialisiert, sodass ein Ergebnis immer bei der Verknüpfung zurückgegeben werden kann, wenn das Datenelement nicht gefüllt wird.

## Links: Beziehung zwischen Tabellen {#links--relation-between-tables}

Eine Verknüpfung beschreibt die Verbindung zwischen einer Tabelle und einer anderen.

Die verschiedenen Vereinigungen (auch &quot;Kardinalitäten&quot; genannt) sind:

* Kardinalität 1-1: Ein Vorkommen der Quelltabelle kann maximal ein entsprechendes Vorkommen der Zielgruppe aufweisen.
* Kardinalität 1-N: Ein Vorkommen der Quelltabelle kann mehrere entsprechende Vorkommen der Tabelle &quot;Zielgruppe&quot;aufweisen, aber ein Vorkommen der Tabelle &quot;Zielgruppe&quot;kann höchstens ein entsprechendes Vorkommen der Quelltabelle aufweisen.
* Kardinalität N-N: Ein Vorkommen der Quelltabelle kann mehrere entsprechende Vorkommen der Tabelle &quot;Zielgruppe&quot;aufweisen und umgekehrt.

In der Oberfläche können Sie die verschiedenen Arten von Beziehungen leicht durch ihre Symbole unterscheiden.

Verknüpfen von Beziehungen mit einer Kampagne:

* ![](assets/do-not-localize/join_with_campaign11.png) : Kardinalität 1-1. Beispielsweise zwischen einem Empfänger und einer aktuellen Reihenfolge. Ein Empfänger kann jeweils nur mit einem Vorkommen der aktuellen Bestelltabelle verknüpft werden.
* ![](assets/do-not-localize/externaljoin11.png) : Kardinalität 1-1, externe Verbindung. Zum Beispiel zwischen einem Empfänger und seinem Land. Ein Empfänger kann nur mit einem Vorkommen des Tabellenlandes verbunden sein. Der Inhalt der Ländertabelle wird nicht gespeichert.
* ![](assets/do-not-localize/join_with_campaign1n.png) : Kardinalität 1-N. Beispielsweise zwischen einem Empfänger und der Tabelle &quot;Abonnement&quot;. Ein Empfänger kann mit mehreren Vorfällen in der Abonnement-Tabelle in Zusammenhang stehen.

Für Verbindungsbeziehungen mit Federated Database Access:

* ![](assets/do-not-localize/join_fda_11.png) : Kardinalität 1-1
* ![](assets/do-not-localize/join_fda_1m.png) : Kardinalität 1-N

:bulb: Weitere Informationen zu FDA finden Sie unter [Federated Data Access](../connect/fda.md).

In dem Schema, das den Fremdschlüssel der Tabelle enthält, muss über das Hauptelement ein Link angegeben werden:

```
<element name="name_of_link" type="link" target="key_of_destination_schema">
  <join xpath-dst="xpath_of_field1_destination_table" xpath-src="xpath_of_field1_source_table"/>
  <join xpath-dst="xpath_of_field2_destination_table" xpath-src="xpath_of_field2_source_table"/>
  ...
</element>
```

Links folgen den folgenden Regeln:

* Die Definition eines Links wird auf einem **link**-Typ **`<element>`** mit den folgenden Attributen eingegeben:

   * **name**: Name des Links aus der Quelltabelle,
   * **Zielgruppe**: Name des Schemas der Zielgruppe,
   * **label**: Bezeichnung des Links,
   * **revLink**  (optional): Name des Rückwärtslinks aus dem Schema Zielgruppe (standardmäßig automatisch abgezogen),
   * **Integrität**  (optional): Referenzintegrität des Vorkommens der Quelltabelle zum Vorkommen der Zielgruppe-Tabelle. Mögliche Werte sind:

      * **definieren**: das Quellvorkommen gelöscht werden kann, wenn es nicht mehr durch ein Vorkommen einer Zielgruppe referenziert wird,
      * **normal**: Wenn Sie das Quellvorkommen löschen, werden die Schlüssel des Links zum Vorkommen der Zielgruppe (Standardmodus) initialisiert. Bei diesem Integritätstyp werden alle Fremdschlüssel initialisiert,
      * **eigene**: Das Löschen des Quellvorkommens führt zum Löschen des Vorkommens der Zielgruppe,
      * **Copyright**: dieselben wie  **eigene**  (im Falle der Löschung) oder Duplikat die Vorkommnisse (im Falle der Vervielfältigung),
      * **neutral**: tut nichts.
   * **revIntegrity** (optional): Integrität im Schema Zielgruppe (optional, standardmäßig &quot;normal&quot;),
   * **revCardinality**  (optional): mit dem Wert &quot;single&quot;wird die Kardinalität mit dem Typ 1-1 ausgefüllt (standardmäßig 1-N).
   * **externalJoin**  (optional): erzwingt die äußere Verbindung
   * **revExternalJoin** (optional): erzwingt die äußere Verbindung am Rückwärtslink


* Ein Link verweist auf ein oder mehrere Felder aus der Quelltabelle zur Zieltabelle. Die Felder, aus denen die Verknüpfung besteht ( `<join>`), müssen nicht ausgefüllt werden, da sie standardmäßig mit dem internen Schlüssel des Zielgruppe-Schemas abgezogen werden.
* Ein Link besteht aus zwei Halblinks, wobei der erste aus dem Quellcode-Schema deklariert und der zweite automatisch im erweiterten Schema des Zielgruppe-Schemas erstellt wird.
* Ein Join kann ein externer Join sein, wenn das Attribut **externalJoin** mit dem Wert &quot;true&quot;(unterstützt in PostgreSQL) hinzugefügt wird.

>[!NOTE]
>
>Links sind die am Ende des Schemas deklarierten Elemente.

### Beispiel 1 {#example-1}

1-N Bezug zur Tabelle &quot;cus:Firma&quot;-Schema:

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

Die Linkdefinition wird ergänzt durch die Felder, aus denen die Verknüpfung besteht, d. h. der Primärschlüssel mit XPath (&quot;@id&quot;) im Ziel-Schema und der Fremdschlüssel mit XPath (&quot;@Firma-id&quot;) im Schema.

Der Fremdschlüssel wird automatisch in einem Element hinzugefügt, das dieselben Eigenschaften wie das zugehörige Feld in der Zieltabelle verwendet, mit der folgenden Benennungskonvention: Name des Schemas Zielgruppe gefolgt vom Namen des zugehörigen Felds (&quot;Firma-ID&quot;in unserem Beispiel).

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

Ein umgekehrter Link zur Tabelle &quot;cus:Empfänger&quot;wurde mit folgenden Parametern hinzugefügt:

* **name**: automatisch vom Namen des Quell-Schemas abgezogen (kann mit dem Attribut &quot;revLink&quot;in der Linkdefinition im Quell-Schema erzwungen werden)
* **revLink**: Name des umgekehrten Links
* **Zielgruppe**: Schlüssel des verknüpften Schemas (&quot;cus:Empfänger&quot;-Schema)
* **ungebunden**: Der Link wird als Collection-Element für eine 1-N Kardinalität deklariert (standardmäßig)
* **Integrität**: &quot;Definieren&quot;standardmäßig (kann mit dem Attribut &quot;revIntegrity&quot;in der Linkdefinition im Quellcode-Schema erzwungen werden).

### Beispiel 2 {#example-2}

In diesem Beispiel werden wir einen Link zum Schema &quot;nms:address&quot;angeben. Der Join ist ein externer Join und wird explizit mit der E-Mail-Adresse des Empfängers und dem Feld &quot;@address&quot;der verknüpften Tabelle (&quot;nms:address&quot;) ausgefüllt.

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

1-1 Bezug zur Tabelle mit dem Schema &quot;cus:extension&quot;:

```
<element integrity="own" label="Extension" name="extension" revCardinality="single" revLink="recipient" target="cus:extension" type="link"/>
```

### Beispiel 4 {#example-4}

Verknüpfen mit einem Ordner (&quot;xtk:folder&quot;-Schema):

```
<element default="DefaultFolder('nmsFolder')" label="Folder" name="folder" revDesc="Recipients in the folder" revIntegrity="own" revLabel="Recipients" target="xtk:folder" type="link"/>
```

Der Standardwert gibt den Bezeichner der ersten zulässigen Parametertypdatei zurück, die in der Funktion &quot;DefaultFolder(&#39;nmsFolder&#39;)&quot;eingegeben wurde.

### Beispiel 5 {#example-5}

In diesem Beispiel möchten wir einen Schlüssel für einen Link (&quot;Firma&quot; zu &quot;cus:Firma&quot;-Schema) mit dem **xlink**-Attribut und einem Feld der Tabelle (&quot;email&quot;) erstellen:

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

Die Definition des Namensschlüssels &quot;companyEmail&quot;wurde um den Fremdschlüssel des Links &quot;Firma&quot;erweitert.
