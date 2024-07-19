---
title: Schemastruktur von Campaign
description: Schemastruktur von Campaign
feature: Schema Extension, Configuration, Data Model
role: Developer
level: Intermediate, Experienced
exl-id: 9c4a9e71-3fc8-4b4e-8782-0742bbeaf426
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1400'
ht-degree: 100%

---

# Schemastruktur{#schema-structure}

Die Grundstruktur eines `<srcschema>` sieht wie folgt aus:

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

Das XML-Dokument eines Datenschemas muss die Wurzel **`<srcschema>`** mit den Attributen **name** und **namespace** zur Angabe des Schemanamens und des Namespace enthalten.

```
<srcSchema name="schema_name" namespace="namespace">
...
</srcSchema>
```

Verwenden wir den folgenden XML-Inhalt, um die Struktur eines Schemas zu illustrieren:

```
<recipient email="John.doe@aol.com" created="AAAA/DD/MM" gender="1"> 
  <location city="London"/>
</recipient>
```

Mit dem zugehörigen Datenschema:

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

Folgende Regeln müssen eingehalten werden:

* Jedes **`<element>`** und **`<attribute>`** müssen mit dem Namen über das Attribut **name** identifiziert werden.

  >[!CAUTION]
  >
  >Der Name des Elements sollte kurz sein, vorzugsweise in Englisch, und nur gemäß den XML-Benennungsregeln zulässige Zeichen enthalten.

* In der XML-Struktur dürfen nur **`<element>`**-Elemente **`<attribute>`**-Elemente und **`<element>`**-Elemente enthalten.
* Ein **`<attribute>`**-Element muss einen eindeutigen Namen innerhalb eines **`<element>`** haben.
* Die Verwendung von **`<elements>`** in mehrzeiligen Datenzeichenfolgen wird empfohlen.

## Datentypen {#data-types}

Der Datentyp wird über das Attribut **type** in den Elementen **`<attribute>`** und **`<element>`** eingegeben.

In der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/elements-attributes/schema-introduction.html?lang=de#configuring-campaign-classic) finden Sie eine detaillierte Liste{target="_blank"}.

Wenn dieses Attribut nicht gefüllt wird, ist **string** der Standarddatentyp, es sei denn, das Element enthält untergeordnete Elemente. Wenn es gefüllt ist, wird es nur zur hierarchischen Strukturierung der Elemente verwendet (Element **`<location>`** in unserem Beispiel).

Die folgenden Datentypen werden in Schemata unterstützt:

* **string**: Zeichenfolge. Beispiele: ein Vorname, eine Stadt usw.

  Die Größe kann über das Attribut **length** (optional, Standardwert &quot;255&quot;) angegeben werden.

* **boolean**: Boolesches Feld. Beispiel für mögliche Werte: wahr/falsch, 0/1, ja/nein usw.
* **byte**, **short**, **long**: ganze Zahlen (1 Byte, 2 Byte, 4 Byte). Beispiele: Alter, Kontonummer, Anzahl der Punkte usw.
* **double**: Gleitkommazahl doppelter Genauigkeit. Beispiele: Preis, Quote usw.
* **date**, **datetime**: Datum und Datum + Uhrzeit. Beispiele: Geburtsdatum, Kaufdatum usw.
* **datetimenotz**: Datum + Uhrzeit ohne Zeitzonendaten.
* **timespan**: Dauer. Beispiel: Betriebszugehörigkeit.
* **memo**: Langtextfelder (mehrere Zeilen). Beispiele: eine Beschreibung, ein Kommentar usw.
* **uuid**: eindeutig identifizierende Felder

  >[!NOTE]
  >
  >Um ein **uuid**-Feld zu enthalten, muss die Funktion &quot;newuid()&quot;hinzugefügt und mit ihrem Standardwert gefüllt werden.

Im Folgenden finden Sie unser Schema mit den eingegebenen Typen:

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

Die Elemente **`<elements>`** und **`<attributes>`** des Datenschemas können mit verschiedenen Eigenschaften angereichert werden. Sie können ein Label ausfüllen, um das aktuelle Element zu beschreiben.

### Labels und Beschreibungen {#labels-and-descriptions}

* Mit der Eigenschaft **label** können Sie eine kurze Beschreibung eingeben.

  >[!NOTE]
  >
  >Das Label ist mit der aktuellen Sprache der Instanz verknüpft.

  **Beispiel**:

  ```
  <attribute name="email" type="string" length="80" label="Email"/>
  ```

  Das Label wird vom Formular der Adobe Campaign-Client-Konsole aus angezeigt:

  ![](assets/schema_label.png)

* Mit der Eigenschaft **desc** können Sie eine lange Beschreibung eingeben.

  Die Beschreibung ist vom Formular aus in der Statusleiste des Hauptfensters der Adobe Campaign-Client-Konsole zu finden.

  >[!NOTE]
  >
  >Die Beschreibung ist mit der aktuellen Sprache der Instanz verknüpft.

  **Beispiel**:

  ```
  <attribute name="email" type="string" length="80" label="Email" desc="Email of recipient"/>
  ```

### Standardwerte {#default-values}

Mit der Eigenschaft **default** können Sie einen Ausdruck definieren, der bei der Inhaltserstellung einen Standardwert zurückgibt.

Der Wert muss ein mit der XPath-Sprache kompatibler Ausdruck sein. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](#reference-with-xpath).

**Beispiel**:

* Aktuelles Datum: **default=&quot;GetDate()&quot;**
* Zähler: **default=&quot;&#39;FRM&#39;+CounterValue(&#39;myCounter&#39;)&quot;**

  In diesem Beispiel wird der Standardwert mithilfe der Verkettung einer Zeichenfolge und des Aufrufs der Funktion **CounterValue** mit einem freien Zählernamen erstellt. Die zurückgegebene Zahl wird bei jedem Einfügen um 1 erhöht.

  >[!NOTE]
  >
  >In der Adobe Campaign-Client-Konsole wird der Knoten **[!UICONTROL Administration > Zähler]** verwendet, um Zähler zu verwalten.

Um einen Standardwert mit einem Feld zu verknüpfen, können Sie die Variable `<default>  or  <sqldefault>   field.  </sqldefault> </default>` verwenden.

`<default>` : ermöglicht es Ihnen, das Feld beim Erstellen von Entitäten mit einem Standardwert vorauszufüllen. Der Wert wird kein SQL-Standardwert sein.

`<sqldefault>` : ermöglicht es Ihnen, beim Erstellen eines Felds einen zusätzlichen Wert zu erhalten. Dieser Wert wird als SQL-Ergebnis angezeigt. Während einer Aktualisierung des Schemas wirkt sich dieser Wert nur auf die neuen Einträge aus.

### Auflistungen {#enumerations}

#### Freie Auflistung {#free-enumeration}

Mit der Eigenschaft **userEnum** können Sie eine freie Auflistung definieren, um die in diesem Feld eingegebenen Werte zu speichern und anzuzeigen. Die Syntax sieht folgendermaßen aus:

**userEnum=&quot;Name der Auflistung&quot;**

Der Name der Auflistung kann frei gewählt und für andere Felder freigegeben werden.

Diese Werte werden in einer Dropdown-Liste im Formular angezeigt:

![](assets/schema_user_enum.png)

>[!NOTE]
>
>In der Adobe Campaign-Client-Konsole wird der Knoten **[!UICONTROL Administration > Auflistungen]** zum Verwalten von Auflistungen verwendet.

#### Auflistung festlegen {#set-enumeration}

Mit der Eigenschaft **enum** können Sie eine feste Auflistung definieren, die verwendet wird, wenn die Liste der möglichen Werte im Voraus bekannt ist.

Das Attribut **enum** bezieht sich auf die Definition einer Auflistungsklasse, die im Schema außerhalb des Hauptelements gefüllt wird.

Auflistungen ermöglichen es dem Benutzer, einen Wert aus einer Dropdown-Liste auszuwählen, anstatt ihn in ein reguläres Eingabefeld einzugeben:

![](assets/schema_enum.png)

Beispiel für eine Deklaration einer Auflistung im Datenschema:

```
<enumeration name="gender" basetype="byte" default="0">    
  <value name="unknown" label="Not specified" value="0"/>    
  <value name="male" label="male" value="1"/>   
  <value name="female" label="female" value="2"/>   
</enumeration>
```

Eine Auflistung wird über das Element **`<enumeration>`** außerhalb des Hauptelements deklariert.

Die Eigenschaften der Auflistung lauten wie folgt:

* **baseType**: Datentyp, der mit den Werten verknüpft ist,
* **label**: Beschreibung der Auflistung,
* **name**: Name der Auflistung,
* **default**: Standardwert der Auflistung.

Die Werte für die Auflistung werden im Element **`<value>`** mit den folgenden Attributen deklariert:

* **name**: Name des intern gespeicherten Werts,
* **label**: über die grafische Oberfläche angezeigtes Label.

#### dbenum-Auflistung {#dbenum-enumeration}

* Mit der Eigenschaft **dbenum** können Sie eine Auflistung definieren, deren Eigenschaften denen der Eigenschaft **enum** ähnlich sind.

  Das Attribut **name** speichert den Wert jedoch nicht intern, sondern speichert einen Code, mit dem Sie die betreffenden Tabellen erweitern können, ohne ihr Schema zu ändern.

  Die Werte werden über den Knoten **[!UICONTROL Administration > Auflistungen]** definiert.

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

## Sammlungen {#collections}

Eine Sammlung ist eine Liste von Elementen mit gleichem Namen und auf gleicher Hierarchieebene.

Mithilfe des Attributs **unbound** mit dem Wert &quot;true&quot; können Sie ein Sammlungselement füllen.

**Beispiel**: Definition des Sammlungselements **`<group>`** im Schema.

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

* **@email**: wählt die E-Mail-Adresse aus,
* **location/@city**: wählt das Attribut &quot;city&quot; unter dem Element **`<location>`** aus,
* **../@email**: wählt die E-Mail-Adresse aus dem übergeordneten Element des aktuellen Elements aus,
* **group`[1]/@label`**: wählt das Attribut &quot;label&quot; aus, das dem ersten **`<group>`**-Sammlungselement untergeordnet ist,
* **group`[@label='test1']`**: wählt das Attribut &quot;label&quot; aus, das dem Element **`<group>`** untergeordnet ist und den Wert &quot;test1&quot; enthält.

>[!NOTE]
>
>Eine zusätzliche Einschränkung wird hinzugefügt, wenn der Pfad ein Unterelement kreuzt. In diesem Fall muss der folgende Ausdruck zwischen Klammern stehen:
>
>* **location/@city** ist nicht gültig; verwenden Sie **`[location/@city]`**
>* **`[@email]`** und **@email** entsprechen einander
>

Es ist auch möglich, komplexe Ausdrücke wie die folgenden arithmetischen Operationen zu definieren:

* **@gender+1**: fügt 1 zum Inhalt des Attributs **gender** hinzu,
* **@email + &#39;(&#39;+@created+&#39;)&#39;**: erstellt eine Zeichenfolge unter Verwendung des Werts der E-Mail-Adresse, zu der das Erstellungsdatum zwischen Klammern hinzugefügt wird (für den Typ &quot;string&quot; muss die Konstante in Anführungszeichen gesetzt werden).

Die Ausdrücke wurden um Funktionen auf hoher Ebene erweitert, um das Potenzial dieser Sprache zu erweitern.

In der Adobe Campaign-Client-Konsole können Sie über einen beliebigen Ausdruckseditor auf die Liste der verfügbaren Funktionen zugreifen:

![](assets/schema_function.png)

**Beispiel**:

* **GetDate()**: gibt das aktuelle Datum zurück,
* **Year(@created)**: gibt das Jahr des Datums zurück, das im Attribut &quot;created&quot; enthalten ist,
* **GetEmailDomain(@email)**: gibt die Domain der E-Mail-Adresse zurück.

## Erstellen einer Zeichenfolge über den Compute string {#building-a-string-via-the-compute-string}

Ein **Compute string** ist ein XPath-Ausdruck, mit dem eine Zeichenfolge erstellt wird, die einen Eintrag in einer mit dem Schema verknüpften Tabelle darstellt. **Compute string** wird hauptsächlich in der grafischen Oberfläche verwendet, um die Beschriftung eines ausgewählten Eintrags anzuzeigen.

Der **Compute string** wird über das Element **`<compute-string>`** unter dem Hauptelement des Datenschemas definiert. Ein **expr**-Attribut enthält einen XPath-Ausdruck zur Berechnung der Anzeige.

**Beispiel**: Compute string der Empfänger-Tabelle.

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
>Wenn das Schema keinen Compute string enthält, wird standardmäßig ein Compute string mit den Werten des Primärschlüssels des Schemas gefüllt.
