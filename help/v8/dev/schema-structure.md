---
solution: Campaign v8
product: Adobe Campaign
title: Struktur des Kampagnenschemas
description: Struktur des Kampagnenschemas
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '1403'
ht-degree: 12%

---

# Schemastruktur{#schema-structure}

Die grundlegende Struktur von `<srcschema>` lautet wie folgt:

```
<srcSchema>
    <enumeration>
        ...          //definition of enumerations
    </enumeration>
   
    <element>         //definition of the root <element>    (mandatory)

        <compute-string/>  //definition of a compute-string
        <key>
            ...        //definition of keys
        </key>
        <sysFilter>
            ...           //definition of filters
        </sysFilter>
        <attribute>
            ...             //definition of fields
        </attribute>
    
            <element>           //definition of sub-<element> 
                  <attribute>           //(collection, links or XML)
                  ...                         //and additional fields
                  </attribute>
                ...
            </element>
      
    </element> 

        <methods>                 //definition of SOAP methods
            <method>
                ...
            </method>
            ...
    </methods>  
          
</srcSchema>
```

Das XML-Dokument eines Datenschemas muss die Wurzel **`<srcschema>`** mit den Attributen **name** und **namespace** zur Angabe des Schemanamens und des Namensraums enthalten.

```
<srcSchema name="schema_name" namespace="namespace">
...
</srcSchema>
```

Verwenden Sie den folgenden XML-Inhalt, um die Struktur eines Datenschemas zu veranschaulichen:

```
<recipient email="John.doe@aol.com" created="AAAA/DD/MM" gender="1"> 
  <location city="London"/>
</recipient>
```

Mit dem entsprechenden Datenschema:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <attribute name="email"/>
    <attribute name="created"/>
    <attribute name="gender"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

## Beschreibung  {#description}

Der Startpunkt des Schemas ist sein Hauptelement. Es ist leicht identifizierbar, da sein Name mit dem des Schemas identisch ist. Außerdem handelt es sich um das direkte untergeordnete Element der Wurzel. Ausgehend von diesem Element beginnt die Inhaltsbeschreibung.

In unserem Beispiel wird das Hauptelement durch die folgende Zeile dargestellt:

```
<element name="recipient">
```

Die Elemente **`<attribute>`** und **`<element>`**, die dem Hauptelement folgen, ermöglichen es Ihnen, die Speicherorte und Namen der Datenelemente in der XML-Struktur zu definieren.

In unserem Beispielschema sind dies:

```
<attribute name="email"/>
<attribute name="created"/>
<attribute name="gender"/>
<element name="location">
  <attribute name="city"/>
</element>
```

Die folgenden Regeln müssen eingehalten werden:

* Jede **`<element>`** und **`<attribute>`** müssen anhand des Namens über das Attribut **name** identifiziert werden.

   >[!CAUTION]
   >
   >Der Name des Elements sollte kurz sein, vorzugsweise in englischer Sprache, und nur autorisierte Zeichen gemäß XML-Benennungsregeln enthalten.

* Nur **`<element>`** -Elemente können **`<attribute>`** -Elemente und **`<element>`** -Elemente in der XML-Struktur enthalten.
* Ein **`<attribute>`** -Element muss einen eindeutigen Namen innerhalb eines **`<element>`** haben.
* Die Verwendung von **`<elements>`** in mehrzeiligen Datenzeichenfolgen wird empfohlen.

## Datentypen {#data-types}

Der Datentyp wird über das Attribut **type** in den Elementen **`<attribute>`** und **`<element>`** eingegeben.

Eine detaillierte Liste finden Sie in der [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=en#configuring-campaign-classic).

Wenn dieses Attribut nicht ausgefüllt wird, ist **string** der Standarddatentyp, es sei denn, das Element enthält untergeordnete Elemente. Ist dies der Fall, wird es nur verwendet, um die Elemente hierarchisch zu strukturieren (**`<location>`** -Element in unserem Beispiel).

Die folgenden Datentypen werden in Schemata unterstützt:

* **string**: Zeichenfolge. Beispiele: Vorname, Stadt usw.

   Die Größe kann über das Attribut **length** angegeben werden (optional, Standardwert &quot;255&quot;).

* **boolean**: Boolesches Feld. Beispiel möglicher Werte: true/false, 0/1, ja/nein usw.
* **byte**,  **short**,  **long**: Ganzzahlen (1 Byte, 2 Byte, 4 Byte). Beispiele: Alter, Kontonummer, Anzahl Punkte usw.
* **double**: Gleitkommazahl mit doppelter Genauigkeit. Beispiele: Preis, Preis usw.
* **date**,  **datetime**: Datum und Datum + Uhrzeit. Beispiele: Geburtsdatum, Kaufdatum usw.
* **datetimenotz**: Datum + Uhrzeit ohne Zeitzonendaten.
* **timespan**: Dauern. Beispiel: Prioritätsstufe.
* **Memo**: Lange Textfelder (mehrere Zeilen). Beispiele: eine Beschreibung, einen Kommentar usw.
* **uuid**: Felder &quot;uniqueidentifier&quot;

   >[!NOTE]
   >
   >Um das Feld **uuid** zu enthalten, muss die Funktion &quot;newuid()&quot; hinzugefügt und mit dem Standardwert ausgefüllt werden.

Im Folgenden finden Sie unser Beispielschema mit den eingegebenen Typen:

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <attribute name="email" type="string" length="80"/>
    <attribute name="created" type="datetime"/>
    <attribute name="gender" type="byte"/>
    <element name="location">
      <attribute name="city" type="string" length="50"/>
   </element>
  </element>
</srcSchema>
```

## Eigenschaften {#properties}

Die Elemente **`<elements>`** und **`<attributes>`** des Datenschemas können mit verschiedenen Eigenschaften angereichert werden. Sie können einen Titel eingeben, um das aktuelle Element zu beschreiben.

### Beschriftungen und Beschreibungen {#labels-and-descriptions}

* Mit der Eigenschaft **label** können Sie eine kurze Beschreibung eingeben.

   >[!NOTE]
   >
   >Die Bezeichnung ist mit der aktuellen Sprache der Instanz verknüpft.

   **Beispiel**:

   ```
   <attribute name="email" type="string" length="80" label="Email"/>
   ```

   Der Titel wird im Eingabeformular der Adobe Campaign-Clientkonsole angezeigt:

   ![](assets/schema_label.png)

* Mit der Eigenschaft **desc** können Sie eine lange Beschreibung eingeben.

   Die Beschreibung wird im Formular in der Statusleiste des Hauptfensters der Adobe Campaign-Clientkonsole angezeigt.

   >[!NOTE]
   >
   >Die Beschreibung ist mit der aktuellen Sprache der Instanz verknüpft.

   **Beispiel**:

   ```
   <attribute name="email" type="string" length="80" label="Email" desc="Email of recipient"/>
   ```

### Standardwerte {#default-values}

Mit der Eigenschaft **default** können Sie einen Ausdruck definieren, der bei der Inhaltserstellung einen Standardwert zurückgibt.

Der Wert muss ein Ausdruck sein, der mit der XPath-Sprache konform ist. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](#reference-with-xpath).

**Beispiel**:

* Aktuelles Datum: **default=&quot;GetDate()&quot;**
* Zähler: **default=&quot;&#39;FRM&#39;+CounterValue(&#39;myCounter&#39;)&quot;**

   In diesem Beispiel wird der Standardwert mithilfe der Verkettung einer Zeichenfolge erstellt und die Funktion **CounterValue** mit einem freien Zählernamen aufgerufen. Die zurückgegebene Zahl wird bei jeder Einfügung um 1 inkrementiert.

   >[!NOTE]
   >
   >In der Adobe Campaign-Clientkonsole wird der Knoten **[!UICONTROL Administration>Zähler]** zum Verwalten von Zählern verwendet.

Um einen Standardwert mit einem Feld zu verknüpfen, können Sie den`<default>  or  <sqldefault>   field.  </sqldefault> </default>`

`<default>` : ermöglicht es Ihnen, das Feld beim Erstellen von Entitäten mit einem Standardwert vorab auszufüllen. Der Wert ist kein SQL-Standardwert.

`<sqldefault>` : ermöglicht Ihnen, beim Erstellen eines Felds einen Mehrwert zu erzielen. Dieser Wert wird als SQL-Ergebnis angezeigt. Während einer Schemaaktualisierung wirkt sich dieser Wert nur auf die neuen Datensätze aus.

### Auflistungen {#enumerations}

#### Freie Auflistung {#free-enumeration}

Mit der Eigenschaft **userEnum** können Sie eine freie Auflistung definieren, um die in diesem Feld eingegebenen Werte zu speichern und anzuzeigen. Die Syntax sieht folgendermaßen aus:

**userEnum=&quot;Name der Auflistung&quot;**

Der Name der Auflistung kann frei gewählt und für andere Felder freigegeben werden.

Diese Werte werden in einer Dropdown-Liste des Formulars angezeigt:

![](assets/schema_user_enum.png)

>[!NOTE]
>
>In der Adobe Campaign-Clientkonsole wird der Knoten **[!UICONTROL Administration > Auflistungen]** zum Verwalten von Auflistungen verwendet.

#### Enumeration festlegen {#set-enumeration}

Mit der Eigenschaft **enum** können Sie eine feste Auflistung definieren, die verwendet wird, wenn die Liste der möglichen Werte im Voraus bekannt ist.

Das Attribut **enum** bezieht sich auf die Definition einer Auflistungsklasse, die im Schema außerhalb des Hauptelements notiert ist.

Auflistungen ermöglichen es dem Benutzer, einen Wert aus einer Dropdown-Liste auszuwählen, anstatt den Wert in ein reguläres Eingabefeld einzugeben:

![](assets/schema_enum.png)

Beispiel einer Auflistungsdeklaration im Datenschema:

```
<enumeration name="gender" basetype="byte" default="0">    
  <value name="unknown" label="Not specified" value="0"/>    
  <value name="male" label="male" value="1"/>   
  <value name="female" label="female" value="2"/>   
</enumeration>
```

Über das Element **`<enumeration>`** wird eine Auflistung außerhalb des Hauptelements deklariert.

Die Auflistungseigenschaften lauten wie folgt:

* **baseType**: Datentyp, der den Werten zugeordnet ist,
* **label**: Beschreibung der Auflistung,
* **name**: Name der Auflistung,
* **Standard**: Standardwert der Auflistung.

Die Auflistungswerte werden im Element **`<value>`** mit den folgenden Attributen deklariert:

* **name**: Name des intern gespeicherten Werts,
* **label**: in der grafischen Benutzeroberfläche angezeigt.

#### dbenum enumeration {#dbenum-enumeration}

* Mit der Eigenschaft **dbenum** können Sie eine Auflistung definieren, deren Eigenschaften denen der Eigenschaft **enum** ähneln.

   Das Attribut **name** speichert den Wert jedoch nicht intern, sondern speichert einen Code, mit dem Sie die betreffenden Tabellen erweitern können, ohne ihr Schema zu ändern.

   Die Werte werden über den Knoten **[!UICONTROL Administration>Auflistungen]** definiert.

   Diese Auflistung dient beispielsweise zur Angabe der Art von Kampagnen.

   ![](assets/schema_dbenum.png)

### Beispiel {#example}

Beispiel des um diese Eigenschaften ergänzten Schemas:

```
<srcSchema name="recipient" namespace="cus">
  <enumeration name="gender" basetype="byte">    
    <value name="unknown" label="Not specified" value="0"/>    
    <value name="male" label="male" value="1"/>   
    <value name="female" label="female" value="2"/>   
  </enumeration>

  <element name="recipient">
    <attribute name="email" type="string" length="80" label="Email" desc="Email of recipient"/>
    <attribute name="created" type="datetime" label="Date of creation" default="GetDate()"/>
    <attribute name="gender" type="byte" label="gender" enum="gender"/>
    <element name="location" label="Location">
      <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
   </element>
  </element>
</srcSchema>
```

## Kollektionen {#collections}

Eine Kollektion ist eine Liste von Elementen mit gleichem Namen und auf gleicher Hierarchieebene.

Mit dem Attribut **unbound** mit dem Wert &quot;true&quot;können Sie ein Kollektionselement ausfüllen.

**Beispiel**: Definition des  **`<group>`** Kollektionselements im Schema.

```
<element name="group" unbound="true" label="List of groups">
  <attribute name="label" type="string" label="Label"/>
</element>
```

Mit Projektion des XML-Inhalts:

```
<group label="Group1"/>
<group label="Group2"/>
```

## Referenz mit XPath {#reference-with-xpath}

Die XPath-Sprache wird in Adobe Campaign verwendet, um ein zu einem Datenschema gehörendes Element oder Attribut zu adressieren.

XPath ist eine Syntax, die es ermöglicht, einen Knoten in der Baumstruktur eines XML-Dokuments zu lokalisieren.

Elemente werden mit ihren Namen bezeichnet, während den Namen von Attributen ein &quot;@&quot;-Zeichen vorangestellt wird.

**Beispiel**:

* **@email**: wählt die E-Mail aus,
* **location/@city**: markiert das Attribut &quot;city&quot;unter dem  **`<location>`** Element
* **../@email**: wählt die E-Mail-Adresse aus dem übergeordneten Element des aktuellen Elements aus
* **Gruppe`[1]/@label`**: markiert das Attribut &quot;label&quot;, das dem ersten  **`<group>`** Kollektionselement untergeordnet ist
* **Gruppe`[@label='test1']`**: markiert das Attribut &quot;label&quot;, das dem  **`<group>`** Element untergeordnet ist und den Wert &quot;test1&quot;enthält

>[!NOTE]
>
>Eine zusätzliche Einschränkung wird hinzugefügt, wenn der Pfad ein Unterelement passiert. In diesem Fall muss der folgende Ausdruck in Klammern gesetzt werden:
>
>* **location/@** city ist ungültig; verwenden  **`[location/@city]`**
>* **`[@email]`** und  **@** emailare-Entsprechung

>



Es ist auch möglich, komplexe Ausdrücke zu definieren, z. B. die folgenden arithmetischen Vorgänge:

* **@gender+1**: fügt dem Inhalt des  **** genderattribute 1 hinzu,
* **@email + &#39;(&#39;+@created+&#39;)&#39;**: erstellt einen String, indem der Wert der E-Mail-Adresse, die zum Erstellungsdatum hinzugefügt wurde, zwischen Klammern steht (setzen Sie die Konstante für den String-Typ in Anführungszeichen).

Den Ausdrücken wurden Funktionen auf hoher Ebene hinzugefügt, um das Potenzial dieser Sprache zu erweitern.

Sie können über einen beliebigen Ausdruckseditor in der Adobe Campaign-Clientkonsole auf die Liste der verfügbaren Funktionen zugreifen:

![](assets/schema_function.png)

**Beispiel**:

* **GetDate()**: gibt das aktuelle Datum aus
* **Year(@created)**: gibt das Jahr des Datums zurück, das im Attribut &quot;created&quot;enthalten ist.
* **GetEmailDomain(@email)**: gibt die Domain der E-Mail-Adresse zurück.

## Erstellen einer Zeichenfolge über die Compute String {#building-a-string-via-the-compute-string}

Ein **Compute string** ist ein XPath-Ausdruck, der verwendet wird, um eine Zeichenfolge zu erstellen, die einen Datensatz in einer mit dem Schema verknüpften Tabelle darstellt. **Compute** String wird hauptsächlich in der grafischen Oberfläche verwendet, um den Titel eines ausgewählten Datensatzes anzuzeigen.

Der **Compute string** wird über das Element **`<compute-string>`** unter dem Hauptelement des Datenschemas definiert. Ein **expr** -Attribut enthält einen XPath-Ausdruck zur Berechnung der Anzeige.

**Beispiel**: Compute string of the recipient table.

```
<srcSchema name="recipient" namespace="nms">  
  <element name="recipient">
    <compute-string expr="@lastName + ' ' + @firstName +' (' + @email + ')' "/>
    ...
  </element>
</srcSchema>
```

Ergebnis der berechneten Zeichenfolge für einen Empfänger: **Doe John (john.doe@aol.com)**

>[!NOTE]
>
>Wenn das Schema keine Compute string enthält, wird standardmäßig eine Compute string -Zeichenfolge mit den Werten des Primärschlüssels des Schemas gefüllt.
