---
product: campaign
title: Hinzufügen eines Angebots auf einer Web-Seite
description: Erfahren Sie, wie Sie ein Angebot auf einer Webseite hinzufügen
exl-id: 1eb0775a-5da9-4a27-aa7b-339372748f9c
source-git-commit: 213a10fea36b3b08c1dd8525084d212e191b2fc7
workflow-type: tm+mt
source-wordcount: '1479'
ht-degree: 99%

---

# Hinzufügen eines Angebots auf einer Web-Seite{#add-an-offer-in-web}

Um das Angebotsmodul auf einer Web-Seite aufzurufen, fügen Sie einen JavaScript-Aufruf direkt in die Seite ein. Dieser Aufruf gibt den Angebotsinhalt in einem Zielelement zurück.

Die URL des Aufruf-Scripts stellt sich wie folgt dar:

```
<script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=" type="text/javascript"></script>
```

Der Parameter &quot;**env**&quot; erhält den internen Namen der anonymen Interaktionen vorbehaltenen Live-Umgebung.

Um ein Angebot zu unterbreiten, müssen somit eine Umgebung und eine Platzierung in Adobe Campaign erstellt sowie eine HTML-Seite konfiguriert werden.

Unten stehend werden verschiedene Integrationsmöglichkeiten mit JavaScript beispielhaft dargestellt.

## Option 1: HTML-Modus {#html-mode}

### Angebote für einen anonymen Kontakt {#presenting-an-anonymous-offer}

**Schritt 1: Angebotsmodul vorbereiten**

1. Konfigurieren Sie in Adobe Campaign eine anonyme Umgebung.
1. Erstellen Sie dann eine dieser Umgebung zugeordnete Platzierung.
1. Erstellen Sie schließlich ein Angebot und eine der Platzierung entsprechende Darstellung.

**Schritt 2: Inhalt der HTML-Seite aktualisieren**

Die HTML-Seite muss ein Element mit einem &quot;@id&quot;-Attribut mit dem Wert des internen Namens der erstellten Platzierung enthalten (&quot;i_internal name space&quot;). Das Angebot wird von Interaction in dieses Element eingefügt.

Im vorliegenden Beispiel nimmt das Attribut @id den Wert &quot;i_SPC12&quot; an, wobei &quot;SPC12&quot; der interne Name der zuvor erstellten Platzierung ist:

```
<div id="i_SPC12"></div>
```

Im vorliegenden Beispiel stellt sich die URL des Script-Aufrufs wie folgt dar (&quot;OE3&quot; ist der interne Name der Live-Umgebung):

```
<script id="interactionProposalScript" src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" type="text/javascript"></script>
```

>[!CAUTION]
>
>Das `<script>`-Element darf nicht in sich geschlossen sein.

Dieser statische Aufruf erzeugt automatisch einen dynamischen Aufruf, der alle vom Angebotsmodul benötigten Parameter enthält.

Dies ermöglicht es, verschiedene Platzierungen innerhalb einer Seite mit einer einzigen Abfrage des Angebotsmoduls abzudecken.

**Schritt 3: Ergebnisse auf der HTML-Seite anzeigen**

Der Inhalt der Angebotsdarstellung wird durch das Angebotsmodul an die HTML-Seite zurückgegeben:

```
<div id="banner_header">
 <div id="i_SPC12">
   <table>
    <tbody>
        <tr>
            <td><h3>Fly to Japan!</h3></td>
        </tr>
        <tr>
            <td><img width="150px" src="https://instance.adobe.org/res/Track/874fdaf72ddc256b2d8260bb8ec3a104.jpg"></td>
            <td>
            <p>Discover Japan for 2 weeks at an unbelievable price!!</p>
            <p><b>2345 Dollars - All inclusive</b></p>
        </td>
        </tr>
    </tbody>
    </table>
 </div>
<script src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" id="interactionProposalScript" type="text/javascript"></script>
</div>
```

### Angebot für einen identifizierten Kontakt {#presenting-an-identified-offer}

Um einem identifizierten Kontakt ein Angebot zu unterbreiten, läuft der Prozess ähnlich ab, wie [in diesem Abschnitt](#presenting-an-anonymous-offer) beschrieben.

Im Inhalt der Web-Seite müssen Sie das folgende Skript hinzufügen, das während des Aufrufs an das Modul den Kontakt identifiziert:

```
<script type="text/javascript">
  interactionTarget = <contact_identifier>;
</script>
```

1. Klicken Sie in der Platzierung, die von der Webseite aus aufgerufen werden soll, auf **[!UICONTROL Erweiterte Parameter]** und fügen Sie mindestens einen Identifikationsschlüssel hinzu.

   ![](assets/interaction_htmlmode_001.png)

   Im vorliegenden Beispiel handelt es sich um einen zusammengesetzten Identifikationsschlüssel, da er sowohl auf die E-Mail-Adresse als auch auf den Namen des Kontakts Bezug nimmt.

1. Wenn die Web-Seite aufgerufen wird, ermöglicht es die Auswertung des Skripts, die ID des Kontakts an das Angebotsmodul zu übergeben. Bei einer zusammengesetzten ID werden die Schlüssel in der gleichen Reihenfolge angezeigt wie in den erweiterten Parametern und durch | getrennt.

   In folgendem Beispiel-Code hat sich der Kontakt auf der Web-Seite angemeldet. Er wurde bei der Abfrage des Angebotsmoduls mithilfe seiner E-Mail-Adresse und seines Familiennamens identifiziert:

   ```
   <script type="text/javascript">
     interactionTarget = myEmail|myName;
   </script>
   ```

### Verwenden der HTML-Rendering-Funktion {#using-an-html-rendering-function}

Die Verwendung einer HTML-Rendering-Funktion bietet den Vorteil, das die HTML-Darstellung des Angebots automatisch erzeugt wird.

1. Klicken Sie in der Angebotsplatzierung auf den Link **[!UICONTROL Funktionen bearbeiten...]**.
1. Kreuzen Sie die Option **[!UICONTROL HTML-Rendering-Funktion überschreiben]** an.
1. Geben Sie dann im Tab **[!UICONTROL HTML-Rendering]** die den in der Platzierung für den Angebotsinhalt definierten Feldern entsprechenden Variablen ein.

   ![](assets/interaction_htmlmode_002.png)

   Im vorliegenden Beispiel wird das Angebot in Form eines Webseitenbanners unterbreitet. Es besteht aus einem anklickbaren Bild mit Untertitel, entsprechend den im Angebotsinhalt definierten Feldern.

## Option 2: XML-Modus {#xml-mode}

### Unterbreiten eines Angebots {#presenting-an-offer}

Mit dem Campaign **Interaction**-Modul können Sie einen XML-Knoten an die HTML-Seite zurückgeben, die das Angebotsmodul aufruft. Dieser XML-Knoten kann von Funktionen verarbeitet werden, die auf Kundenseite entwickelt werden.

Die Angebotsmodul-Abfrage stellt sich wie folgt dar:

```
<script type="text/javascript" id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=&cb="></script>
```

* Der Parameter &quot;**env**&quot; erhält den internen Namen der Live-Umgebung.

* Der optionale Parameter &quot;**cb**&quot; erhält den Namen der Funktion, die den vom Angebotsmodul zurückgegebenen XML-Knoten auswerten wird (Callback).

* Der optionale Parameter &quot;**t**&quot; erhält bei Interaktionen mit identifizierten Kontakten die Kennung des Kontakts. Der Parameter kann auch mit der Variablen **interactionTarget** übergeben werden.

* Der optionale Parameter &quot;**c**&quot; erhält die Liste der internen Kategorienamen.

* Der optionale Parameter &quot;**th**&quot; erhält die Liste der Themen.

* Der optionale Parameter &quot;**gctx**&quot; erhält die globalen Aufrufdaten (Kontext) der gesamten Seite.

Der zurückgegebene XML-Knoten stellt sich wie folgt dar:

```
<propositions>
 <proposition id="" offer-id="" weight="" rank="" space="" div=""> //proposition identifiers
   ...XML content defined in Adobe Campaign...
 </proposition>
 ...
</propositions>
```

Das folgende Anwendungsbeispiel beschreibt die in Adobe Campaign vorzunehmenden Konfigurationen zur Aktivierung des XML-Modus und zeigt das Ergebnis der Angebotsmodul-Abfrage in der HTML-Seite.

1. **Erstellen einer Umgebung und einer Platzierung**

   Weiterführende Informationen zur Erstellung einer Umgebung finden Sie auf [dieser Seite](interaction-env.md).

   Die Erstellung von Platzierungen wird auf [dieser Seite](interaction-offer-spaces.md) genauer erläutert.

1. **Erweitern des Angebotsschemas zur Hinzufügung neuer Felder**

   Das Schema definiert die Felder Titel 2 und Preis.

   Im vorliegenden Beispiel trägt es den Namen **cus:offer**.

   ```
   <srcSchema _cs="Marketing offers (cus)" created="2013-01-18 17:14:20.762Z" createdBy-id="0"
              desc="" entitySchema="xtk:srcSchema" extendedSchema="nms:offer" img="nms:offer.png"
              label="Marketing offers" labelSingular="Marketing offers" lastModified="2013-01-18 15:20:18.373Z"
              mappingType="sql" md5="F14A7AA009AE1FCE31B0611E72866AC3" modifiedBy-id="0"
              name="offer" namespace="cus" xtkschema="xtk:srcSchema">
     <createdBy _cs="Administrator (admin)"/>
     <modifiedBy _cs="Administrator (admin)"/>
     <element img="nms:offer.png" label="Marketing offers" labelSingular="Marketing offer"
              name="offer">
       <element label="Content" name="view">
         <element label="Price" name="price" type="long" xml="true"/>
         <element label="Title 2" name="title2" type="string" xml="true"/>
   
         <element advanced="true" desc="Price calculation script." label="Script price"
                  name="price_jst" type="CDATA" xml="true"/>
         <element advanced="true" desc="Title calculation script." label="Script title"
                  name="title2_jst" type="CDATA" xml="true"/>
       </element>
     </element>
   </srcSchema>
   ```

   >[!CAUTION]
   >
   >Jedes Element muss zweimal definiert werden. CDATA-Elemente (&quot;_jst&quot;) können Personalisierungsfelder enthalten.
   >
   >Vergessen Sie nicht, die Datenbankstruktur zu aktualisieren.

   Sie können das Angebotsschema erweitern, um neue Felder sowohl im Batch- als auch im Einzelmodus in jedem beliebigen Format (Text, HTML oder XML) hinzuzufügen.

1. **Erweitern des Angebotsformulars zur Hinzufügung neuer Felder und Änderung eines existierenden Felds**

   Öffnen Sie das Formular **Angebot (nms)**.

   Fügen Sie im Abschnitt &quot;Views&quot; die zwei neuen Felder mit folgendem Inhalt ein:

   ```
   <input label="Title 2" margin-right="5" prebuildSubForm="false" type="subFormLink" xpath="title2_jst">
        <form label="Edit title 2" name="editForm" nothingToSave="true">
            <input nolabel="true" toolbarAlign="horizontal" type="jstEdit" xpath="." xpathInsert="/ignored/customizeTitle2">
            <container>
                <input menuId="viewMenuBuilder" options="inbound" type="customizeBtn" xpath="/ignored/customizeTitle2"/>
            </container>
            </input>
        </form>
    </input>
    <input nolabel="true" type="edit" xpath="title2_jst"/>
    <input label="Price" margin-right="5" prebuildSubForm="false" type="subFormLink" xpath="price_jst">
        <form label="Edit price" name="editForm" nothingToSave="true">
        <input nolabel="true" toolbarAlign="horizontal" type="jstEdit" xpath="." xpathInsert="/ignored/customizePrice">
            <container>
                <input menuId="viewMenuBuilder" options="inbound" type="customizeBtn" xpath="/ignored/customizePrice"/>
            </container>
        </input>
        </form>
    </input>
    <input colspan="2" label="Prix" nolabel="true" type="number" xpath="price_jst"/>
   ```

   Kommentieren Sie das Ziel-URL-Feld:

   ![](assets/interaction_xmlmode_form_001.png)

   >[!CAUTION]
   >
   >Die Formularfelder (`<input>`) müssen auf die im zuvor erstellten Schema definierten CDATA-Elemente verweisen.

   Im Formular der Angebotsdarstellungen schlagen sich die Änderungen wie folgt nieder:

   ![](assets/interaction_xmlmode_form.png)

   Die Felder **[!UICONTROL Titel 2]** und **[!UICONTROL Preis]** wurden eingefügt und das Feld **[!UICONTROL Ziel-URL]** wird nicht mehr angezeigt.

1. **Erstellen eines Angebots**

   Weiterführende Informationen zum Erstellen von Angeboten finden Sie auf [dieser Seite](interaction-offer.md).

   Im vorliegenden Anwendungsbeispiel wird das Angebot wie folgt konfiguriert:

   ![](assets/interaction_xmlmode_offer.png)

1. **Genehmigen des Angebots**

   Validieren Sie das Angebot oder lassen Sie es validieren und aktivieren Sie es in der zuvor erstellten Platzierung, um es in der entsprechenden Live-Umgebung verfügbar zu machen.

1. **Abfrage des Angebotsmoduls und Ergebnis in der HTML-Seite**

   Die Abfrage des Angebotsmoduls in der HTML-Seite stellt sich wie folgt dar:

   ```
   <script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=OE7&cb=alert" type="text/javascript">
   ```

   Der Parameter &quot;**env**&quot; nimmt als Wert den internen Namen der Live-Umgebung an.

   Der Parameter &quot;**cb**&quot; nimmt als Wert den Namen der Funktion an, die den vom Angebotsmodul zurückgegebenen XML-Knoten auswerten soll. Im vorliegenden Beispiel öffnet die aufgerufene Funktion ein Modalfenster (alert()-Funktion).

   Der vom Angebotsmodul zurückgegebene XML-Knoten stellt sich wie folgt dar:

   ```
   <propositions>
    <proposition id="a28002" offer-id="10322005" weight="1" rank="1" space="SPC14" div="i_SPC14">
     <xmlOfferView>
      <title>Travel to Russia</title>
      <price>3456</price>
      <description>Discover this vacation package!INCLUDES 10 nights. FEATURES buffet breakfast daily. BONUS 5th night free.</description>
      <image>
       <path>https://myinstance.com/res/Track/ae1d2113ed732d58a3beb441084e5960.jpg</path>
       <alt>Travel to Russia</alt>
      </image>
     </xmlOfferView>
    </proposition>
   </propositions>
   ```

### Verwendung einer Rendering-Funktion {#using-a-rendering-function-}

Es ist möglich, eine Angebotsunterbreitung mithilfe einer XML-Rendering-Funktion zu erstellen. Diese Funktion ändert den XML-Knoten, der beim Aufruf des Angebotsmoduls an die HTML-Seite zurückgegeben wird.

1. Klicken Sie in der Angebotsplatzierung auf den Link **[!UICONTROL Funktionen bearbeiten...]**.
1. Kreuzen Sie die Option **[!UICONTROL XML-Rendering-Funktion überschreiben]** an.
1. Fügen Sie im Tab **[!UICONTROL XML-Rendering]** die gewünschte Funktion ein.

   Die Funktion kann folgendem Beispiel entsprechen:

   ```
   function (proposition) {
     delete proposition.@id;
     proposition.@newAttribute = "newValue";
   } 
   ```

![](assets/interaction_xmlmode_001.png)

## Einrichten einer SOAP-Integration

Die für die Angebotsverwaltung verfügbaren SOAP-Webservices unterscheiden sich von den in Adobe Campaign gewöhnlich verwendeten. Sie sind über die im vorangehenden Kapitel beschriebene Interaction-URL zugänglich und ermöglichen es, ein Angebot für einen spezifischen Kontakt vorzuschlagen oder zu aktualisieren.

### Angebotsvorschläge {#offer-proposition}

Für Angebotsvorschläge über SOAP muss der Befehl **nms:proposition#Propose** hinzugefügt werden, gefolgt von im Anschluss erläuterten Parametern:

* **targetId** - Primärschlüssel des Kontakts (es kann sich um einen zusammengesetzten Schlüssel handeln).
* **maxCount** - gibt die Anzahl an Angebotsvorschlägen für den Kontakt an.
* **context** - erlaubt das Einfügen von Kontextdaten in das Platzierungsschema. Wenn das verwendete Schema **nms:interaction** lautet, sollte **`<empty>`** hinzugefügt werden.
* **categories** - bezeichnet die Kategorie, der die vorgeschlagenen Angebote angehören müssen.
* **themes** - bezeichnet die Themen, denen die vorgeschlagenen Angebote entsprechen müssen.
* **uuid** - Wert des permanenten Adobe-Campaign-Cookies (&quot;uuid230&quot;).
* **nlid** - Wert des Adobe-Campaign-Sitzungs-Cookies (&quot;nlid&quot;).
* **noProp** - Angabe des Werts &quot;true&quot;, wenn keine Vorschläge eingefügt werden sollen.

>[!NOTE]
>
>**targetId** und **maxCount** sind Pflichtparameter, die Angabe der anderen ist optional.

Als Antwort auf die Abfrage gibt der SOAP-Dienst folgende Parameter zurück:

* **interactionId** - Kennung der Interaktion.
* **propositions** - das die Liste der Vorschläge enthaltene XML-Element. Jeder Vorschlag verfügt über eine Kennung und eine spezifische HTML-Darstellung.

### Angebotsaktualisierung {#offer-update}

Ergänzen Sie die URL mit dem Befehl **nms:interaction#UpdateStatus** und folgenden Parametern:

* **proposition** - die die vom Angebotsmodul ausgegebene Vorschlagskennung enthaltende Zeichenkette. Siehe [Angebotsvorschläge](#offer-proposition).
* **status** - Zahl, die den neuen Status des Angebots angibt. Die möglichen Werte sind in der Auflistung **propositionStatus**, im Schema **nms:common** aufgeführt. Beispielsweise entspricht die Zahl 3 werksmäßig dem Status **Akzeptiert**.
* **context** - XML-Element, mit dem Sie Kontextdaten zum Platzierungsschema hinzufügen können. Wenn das verwendete Schema **nms:interaction** lautet, sollte **`<empty>`** hinzugefügt werden.

### Anwendungsbeispiel eines SOAP-Aufrufs {#example-using-a-soap-call}

Unten stehend ein Beispiel-Code eines SOAP-Aufrufs:

```
<%
  var space = request.parameters.sp
  var cnx = new HttpSoapConnection(
    "https://" + request.serverName + ":" + request.serverPort + "/interaction/" + env + "/" + space,
    "utf-8",
    HttpSoapConnection.SOAP_12)
  var session = new SoapService(cnx, "nms:interaction")
  var action = request.parameters.a
  if( action == undefined )
    action = 'propose'

  try
  {
    switch( action )
    {
    case "update":
      var proposition = request.parameters.p
      var status      = request.parameters.st
      session.addMethod("UpdateStatus", "nms:interaction#UpdateStatus",
       ["proposition", "string",
        "status",      "string",
        "context",     "NLElement"],
       [])
      session.UpdateStatus(proposition, status, <undef/>)
      var redirect = request.parameters.r
      if( redirect != undefined )
        response.sendRedirect(redirect)
      break;

    case "propose":
      var count = request.parameters.n
      var target = request.parameters.t
      var categorie = request.parameters.c
      var theme = request.parameters.th
      var layout = request.parameters.l
      if( count == undefined )
        count = 1
      session.addMethod("Propose", "nms:proposition#Propose",
       ["targetId",      "string",
        "maxCount",      "string",
         "categories",    "string",
         "themes",        "string",
        "context",       "NLElement"],
       ["interactionId", "string",
        "propositions",  "NLElement"])
      response.setContentType("text/html")
      var result = session.Propose(target, count, category, theme, <empty/>)
      var props = result[1]
  %><table><tr><%
      for each( var propHtml in props.proposition.*.mdSource )
      {
        %><td><%=propHtml%></td><%
      }
  %></tr></table><%
      break;
    }
  }
  catch( e )
  {
  }
  %>
```
