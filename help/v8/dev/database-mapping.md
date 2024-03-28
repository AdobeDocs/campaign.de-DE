---
title: Mapping der Campaign-Datenbank
description: Mapping der Campaign-Datenbank
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: a804d164-58bf-4b15-a48e-8cf75d793668
source-git-commit: 673298a60927902bba71fd9167c5408e538f4929
workflow-type: ht
source-wordcount: '371'
ht-degree: 100%

---

# Datenbank-Mapping{#database-mapping}

Das SQL-Mapping dieses Beispielschemas ergibt das folgende XML-Dokument:

```sql
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

  ```sql
  <element name="recipient" sqltable="CusRecipient">
  ```

* Feld: Name des Elements mit vorangestelltem Präfix, das nach Typ definiert wird (&quot;i&quot; für Integer, &quot;d&quot; für Dublette, &quot;s&quot; für String, &quot;ts&quot; für Datumsangaben usw.)

  Der Feldname wird über das Attribut **sqlname** für die verschiedenen Eingaben von **`<attribute>`** und **`<element>`** eingegeben:

  ```sql
  <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
  ```

>[!NOTE]
>
>SQL-Namen können aus dem Quellschema geladen werden. Füllen Sie dazu die Attribute &quot;sqltable&quot; oder &quot;sqlname&quot; für das betreffende Element aus.

Das SQL-Script zur Erstellung der aus dem erweiterten Schema generierten Tabelle lautet wie folgt:

```sql
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

In Bezug auf SQL-Felder gelten folgende Einschränkungen:

* Keine Nullwerte in numerischen und Datumsfeldern
* Numerische Felder werden mit 0 initialisiert

## XML-Felder {#xml-fields}

Standardmäßig werden alle eingegebenen **`<attribute>`**- und **`<element>`**-Elemente einem SQL-Schema der Datentabelle zugeordnet. Sie können dieses Feld jedoch anstatt in SQL auch in XML referenzieren. Das bedeutet, dass die Daten in einem Memo-Feld (&quot;mData&quot;) der Tabelle gespeichert werden, in der Werte aller XML-Felder enthalten sind. Als Speicher dieser Daten fungiert ein XML-Dokument, das die Struktur des Schemas beibehält.

Um ein Feld in XML auszufüllen, müssen Sie dem betreffenden Element das Attribut **xml** mit dem Wert &quot;true&quot; hinzufügen.

**Beispiele**

* Mehrzeiliges Kommentarfeld:

  ```sql
  <element name="comment" xml="true" type="memo" label="Comment"/>
  ```

* Beschreibung der Daten im HTML-Format:

  ```sql
  <element name="description" xml="true" type="html" label="Description"/>
  ```

  Über den Typ &quot;html&quot; können Sie HTML-Inhalte in einem CDATA-Tag speichern und eine spezielle HTML-Bearbeitungsprüfung in der Benutzeroberfläche des Adobe Campaign-Clients anzeigen.

Bei Verwendung von XML-Feldern ist das Hinzufügen von Feldern ohne Anpassungen der physischen Struktur der Datenbank möglich. Ein weiterer Vorteil besteht darin, dass weniger Ressourcen benötigt werden (SQL-Feldern zugewiesene Größe, Anzahl der Felder pro Tabelle usw.).
