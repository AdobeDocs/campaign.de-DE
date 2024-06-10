---
title: Schlüsselverwaltung in der Campaign-Datenbank
description: Grundlegendes zur Schlüsselverwaltung in Adobe Campaign-Schemata
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: cf1f5cfc-172f-44ec-ac97-804d15f9d628
source-git-commit: 0f5efba364ef924447324bdd806e15e6db8d799d
workflow-type: ht
source-wordcount: '268'
ht-degree: 100%

---

# Schlüsselverwaltung {#management-of-keys}

Jede mit einem Datenschema verknüpfte Tabelle benötigt mindestens einen Schlüssel zur Identifizierung eines Eintrags in einer Tabelle.

Ein Schlüssel wird über das Hauptelement des Datenschemas deklariert.

```sql
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

Ein Schlüssel wird als „Primärschlüssel“ bezeichnet, wenn er an erster Stelle im auszufüllenden Schema steht oder wenn er ein `internal`-Attribut enthält, das auf „true“ festgelegt ist.

Ein Schlüssel kann auf ein oder mehrere Felder in der Tabelle verweisen.

**Beispiel**:

* Hinzufügen eines Schlüssels zur E-Mail-Adresse und zum Ort:

  ```sql
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

  ```sql
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

  ```sql
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

  ```sql
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

## Primärschlüssel – Kennung{#primary-key}

Im Kontext einer [Enterprise (FFDA)-Bereitstellung](../architecture/enterprise-deployment.md) ist der Primärschlüssel der Adobe Campaign-Tabellen eine **Universally Unique ID (UUID)**, die automatisch von der Datenbank-Engine generiert wird. Der Schlüsselwert ist in der gesamten Datenbank eindeutig. Der Inhalt des Schlüssels wird beim Einfügen des Datensatzes automatisch generiert.

**Beispiel**

Im folgenden Beispiel deklarieren wir einen inkrementellen Schlüssel im Quellschema:

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"  autopk="true" autouuid="true">
  ...
  </element>
</srcSchema>
```

Das generierte Schema:

```sql
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
