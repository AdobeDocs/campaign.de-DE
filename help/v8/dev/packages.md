---
title: Datenpackages
description: Datenpackages
feature: Data Management, Package Export/Import
role: Developer
level: Intermediate, Experienced
source-git-commit: 202a0553f0c736086eca993b9647737732f57d07
workflow-type: tm+mt
source-wordcount: '2020'
ht-degree: 48%

---

# Daten-Packages {#data-packages}

## Erste Schritte mit Paketen {#gs-data-packages}

Sie können Datenpackages verwenden, um benutzerdefinierte Plattformeinstellungen und -daten zu exportieren und zu importieren. Ein Paket kann verschiedene Arten von Konfigurationen und Komponenten enthalten, gefiltert oder nicht.

In Campaign-Datenpackages werden Entitäten der Adobe Campaign-Datenbank in XML-Dateien angezeigt. In einem Package wird jede Entität mit allen Daten dargestellt.

Der Grundsatz **Datenpackages** eine Datenkonfiguration zu exportieren und in eine andere Adobe Campaign-Umgebung zu integrieren. In diesem [Abschnitt](#data-package-best-practices) erfahren Sie, wie Sie einen konsistenten Satz von Daten-Packages aufrechterhalten.

### Typen von Packages {#types-of-packages}

Sie können in Adobe Campaign mit drei Pakettypen arbeiten: Benutzerpakete, Plattformpakete und Admin-Packages.

* A **Benutzerpaket** ermöglicht die Auswahl der Liste der zu exportierenden Entitäten. Dieser Pakettyp verwaltet Abhängigkeiten und überprüft Fehler.
* A **Plattform-Package** enthält alle hinzugefügten (nicht standardmäßigen) technischen Ressourcen: Schemata, JavaScript-Code usw.
* Ein **Admin-Paket** enthält alle hinzugefügten (nicht standardmäßigen) Vorlagen und Geschäftsobjekte: Vorlagen, Bibliotheken usw.

>[!CAUTION]
>
>Die **platform** und **admin** -Pakete enthalten eine vordefinierte Liste von Entitäten, die exportiert werden sollen. Jeder exportierbaren Entität sind Filterbedingungen zugeordnet, die es ermöglichen, die Standard-Ressourcen aus dem erstellten Package auszuschließen.

## Datenstruktur {#data-structure}

Die Beschreibung eines Datenpakets ist ein strukturiertes XML-Dokument, das der Grammatik der **xrk:navtree** Datenschema wie im folgenden Beispiel:

```xml
<package>
  <entities schema="nms:recipient">
    <recipient email="john.smith@adobe.com" lastName="Smith" firstName="John">      
      <folder _operation="none" name="nmsRootFolder"/>      
      <company _operation="none" name="Adobe"/>
    </recipient>
  </entities>
  <entities schema="sfa:company">
    <company name="Adobe">
      <location city="London" zipCode="W11 2BQ"/>
    </company>
  </entities>
</package>
```

Das XML-Dokument muss mit dem `<package>`-Element beginnen und enden. Alle `<entities>` -Elemente, die darauf folgen, verteilen die Daten nach Dokumenttyp. Ein `<entities>` -Element enthält die Daten des Packages im Format des in der Variablen **schema** -Attribut. Die Daten eines Packages dürfen keine internen Schlüssel enthalten, die nicht zwischen Datenbanken kompatibel sind, wie beispielsweise automatisch generierte Schlüssel (Option **autopk**).

In unserem Beispiel werden die Joins auf der `folder` und `company` -Links wurden in den Zieltabellen durch so genannte &quot;High-Level&quot;-Schlüssel ersetzt:

```xml
<recipient>
  <folder _operation="none" name="nmsRootFolder"/>
  <company _operation="none" name="Adobe"/>
</recipient>
```

Die `operation` -Attribut mit dem Wert `none` eine Abstimmrelation definiert.

Ein Datenpaket kann manuell über einen beliebigen Texteditor erstellt werden. Sie müssen sicherstellen, dass die Struktur des XML-Dokuments mit dem `xtk:navtree` Datenschema. Die Client-Konsole verfügt über ein Datenpaketexport- und -importmodul.

## Packages exportieren {#export-packages}

Für den Export von Packages gibt es drei Möglichkeiten:

* Verwenden Sie die **[!UICONTROL Package-Export]** unterstützt den Export von Objektgruppen in ein einzelnes Package. [Weitere Informationen](#export-a-set-of-objects-in-a-package)
* So exportieren Sie **Einzelobjekt**, klicken Sie mit der rechten Maustaste darauf und wählen Sie **[!UICONTROL Aktionen > In ein Package exportieren]**.
* Verwenden Sie die **Package-Definitionen** um eine Package-Struktur zu erstellen, in der Sie Objekte hinzufügen, die später in einem Package exportiert werden sollen. [Weitere Informationen](#manage-package-definitions)

Nachdem ein Package exportiert wurde, können Sie es und alle hinzugefügten Entitäten in eine andere Campaign-Instanz importieren.

### Objekte in ein Package exportieren {#export-a-set-of-objects-in-a-package}

Gehen Sie wie folgt vor, um eine Gruppe von Objekten in ein Datenpaket zu exportieren:

1. Navigieren Sie zum Package-Export-Assistenten über **[!UICONTROL Tools > Erweitert > Package exportieren..]** Menü des Explorers.
1. Wählen Sie die [Packagetypen](#types-of-packages).

   ![](assets/package_type.png)

1. Klicken Sie auf **Hinzufügen** -Schaltfläche, um die Entitäten auszuwählen, die als Package exportiert werden sollen.

   >[!CAUTION]
   >
   >Beim Export eines Ordners vom Typ **[!UICONTROL Angebotskategorie]**, **[!UICONTROL Angebotsumgebung]**, **[!UICONTROL Programm]** oder **[!UICONTROL Plan]** darf unter keinen Umständen die Entität **xtk:folder** gewählt werden, da dies einen Datenverlust verursachen kann. Wählen Sie stattdessen die jeweils dem Ordner entsprechende Entität aus: **nms:offerCategory** für Angebotskategorien, **nms:offerEnv** für Angebotsumgebungen, **nms:program** für Programme und **nms:plan** für Pläne.

   Der Abhängigkeitsmechanismus steuert die Exportsequenz der Entitäten. Weitere Informationen hierzu finden Sie unter [Abhängigkeitsverwaltung](#manage-dependencies).

1. Klicks **[!UICONTROL Nächste]** und definieren die Filterabfrage nach dem zu extrahierenden Dokumenttyp. Hier muss die Filterbedingung der Datenextraktion angegeben werden.

   >[!NOTE]
   >
   >Der Abfrageeditor wird in [diesem Abschnitt](../../automation/workflow/query.md) beschrieben.

1. Klicks **[!UICONTROL Nächste]** und wählen Sie die Sortierreihenfolge der exportierten Daten aus.

1. Sehen Sie sich die zu extrahierenden Daten in der Vorschau an, um Ihre Konfiguration zu überprüfen.

1. Auf der letzten Seite des Package-Export-Assistenten können Sie den Export starten. Die Daten werden in der im Feld **[!UICONTROL Datei]** angegebenen Datei gespeichert.

### Abhängigkeiten verwalten {#manage-dependencies}

Der Exportvorgang verfolgt die Verknüpfungen zwischen den verschiedenen exportierten Elementen. Der Mechanismus wird durch zwei Regeln bestimmt:

* Objekte, die mit einer Relation mit einer `own` oder `owncopy` Die Typintegrität wird im selben Package exportiert wie das exportierte Objekt.
* Objekte, die mit einer Verknüpfung verknüpft sind `neutral` oder `define` Integrität des Typs (definierte Relation) muss separat exportiert werden.

>[!NOTE]
>
>Mit Schemaelementen verknüpfte Integritätstypen werden definiert in [diese Seite](database-links.md).

#### Eine Kampagne exportieren {#export-a-campaign}

Im Folgenden finden Sie ein Beispiel für den Export einer Kampagne. Die zu exportierende Marketingkampagne enthält:
* a `MyTask`Aufgabe
* a `campaignWorkflow` Workflow im folgenden Ordner: **[!UICONTROL Administration > Betreibung > Technische Workflows > Kampagnenprozesse > MyWorkflow]**.

Die Aufgabe und der Workflow werden im selben Package wie die Kampagne exportiert, da die entsprechenden Schemata über Links mit einem `own` Typintegrität

Der Paketinhalt lautet:

```xml
<?xml version='1.0'?>
<package author="Administrator (admin)" buildNumber="7974" buildVersion="7.1" img=""
label="" name="" namespace="" vendor="">
 <desc></desc>
 <version buildDate="2013-01-09 10:30:18.954Z"/>
 <entities schema="nms:operation">
  <operation duration="432000" end="2013-01-14" internalName="OP1" label="MyCampaign"
  modelName="opEmpty" start="2013-01-09">
   <controlGroup>
    <where filteringSchema=""/>
   </controlGroup>
   <seedList>
    <where filteringSchema="nms:seedMember"></where>
    <seedMember internalName="SDM1"></seedMember>
   </seedList>
   <parameter useAsset="1" useBudget="1" useControlGroup="1" useDeliveryOutline="1"
   useDocument="1" useFCPValidation="0" useSeedMember="1" useTask="1"
   useValidation="1" useWorkflow="1"></parameter>
   <fcpSeed>
    <where filteringSchema="nms:seedMember"></where>
   </fcpSeed>
   <owner _operation="none" name="admin" type="0"/>
   <program _operation="none" name="nmsOperations"/>
   <task end="2013-01-17 10:07:51.000Z" label="MyTask" name="TSK2" start="2013-01-16 10:07:51.000Z"
   status="1">
    <owner _operation="none" name="admin" type="0"/>
    <operation _operation="none" internalName="OP1"/>
    <folder _operation="none" name="nmsTask"/>
   </task>
   <workflow internalName="WKF12" label="CampaignWorkflow" modelName="newOpEmpty"
   order="8982" scenario-cs="Notification of the workflow supervisor (notifySupervisor)"
   schema="nms:recipient">
    <scenario internalName="notifySupervisor"/>
    <desc></desc>
    <folder _operation="none" name="Folder4"/>
    <operation _operation="none" internalName="OP1"/>
   </workflow>
  </operation>
 </entities>
</package>   
```

Die Zugehörigkeit zu einem Package-Typ wird in einem Schema mit der Variablen `@pkgAdmin and @pkgPlatform` -Attribut. Diese beiden Attribute erhalten einen XTK-Ausdruck, der die Bedingungen der Zugehörigkeit zum Package festlegt.

```xml
<element name="offerEnv" img="nms:offerEnv.png" 
template="xtk:folder" pkgAdmin="@id != 0">
```

Schließlich wird die `@pkgStatus` -Attribut können Sie die Exportregeln für diese Elemente oder Attribute definieren. Entsprechend dem Wert des Attributs wird das Element oder das Attribut im exportierten Package vorhanden sein. Die drei für das Attribut @pkgStatus möglichen Werte sind:

* `never`: exportiert das Feld/die Verknüpfung nicht
* `always`: forciert den Export für dieses Feld
* `preCreate`: genehmigt die Erstellung der verknüpften Entität

>[!NOTE]
>
>Die `preCreate` -Wert wird nur bei Ereignissen vom Typ &quot;Link&quot;zugelassen. Damit können Sie eine Entität erstellen oder darauf verweisen, die noch nicht im exportierten Package geladen wurde.

## Package-Definitionen verwalten {#manage-package-definitions}

Mithilfe von Package-Definitionen können Sie eine Package-Struktur erstellen, in der Sie Entitäten hinzufügen, die später als einzelnes Package exportiert werden. Sie können dann dieses Package und alle hinzugefügten Entitäten in eine andere Campaign-Instanz importieren.

### Package-Definitionen erstellen {#create-a-package-definition}

Auf Package-Definitionen können Sie über das Menü **[!UICONTROL Administration > Konfiguration > Packageverwaltung > Package-Definition]** zugreifen.

Um eine Package-Definition zu erstellen, klicken Sie auf die Schaltfläche **[!UICONTROL Neu]** und geben Sie die allgemeinen Informationen für die Package-Definition ein.

![](assets/packagedefinition_create.png)

Anschließend können Sie Entitäten zur Package-Definition hinzufügen und diese in ein XML-Datei-Package exportieren.

**Verwandte Themen:**

* [Entitäten zu einer Package-Definition hinzufügen](#add-entities-to-a-package-definition)
* [Erzeugung von Package-Definitionen konfigurieren](#configure-package-definitions-generation)
* [Packages über eine Package-Definition exportieren](#export-packages-from-a-package-definition)

### Entitäten zu einer Package-Definition hinzufügen {#add-entities-to-a-package-definition}

Klicken Sie im Tab **[!UICONTROL Inhalt]** auf die Schaltfläche **[!UICONTROL Hinzufügen]**, um die Entitäten auszuwählen, die mit dem Package exportiert werden sollen. Best Practices bei der Auswahl von Entitäten werden im Abschnitt [diesem Abschnitt](#export-a-set-of-objects-in-a-package).

![](assets/packagedefinition_addentities.png)

Entitäten können direkt über ihren Speicherort in der Instanz zu einer Package-Definition hinzugefügt werden. Gehen Sie dazu wie folgt vor:

1. Klicken Sie mit der rechten Maustaste auf die gewünschte Entität und wählen Sie dann **[!UICONTROL Aktionen > In ein Package exportieren]** aus.

1. Wählen Sie **[!UICONTROL Einer Package-Definition hinzufügen]** und anschließend die Package-Definition, zu der Sie die Entität hinzufügen möchten.

1. Die Entität wird zur Package-Definition hinzugefügt und mit dem Package exportiert (siehe [diesen Abschnitt](#export-packages-from-a-package-definition)).

### Erzeugung von Package-Definitionen konfigurieren {#configure-package-definitions-generation}

Die Package-Erzeugung kann über den Tab **[!UICONTROL Inhalt]** der Package-Definition konfiguriert werden. Klicken Sie dazu auf den Link **[!UICONTROL Erzeugungsparameter]**.

![](assets/packagedefinition_generationparameters.png)

* Verwenden Sie die **[!UICONTROL Definition einschließen]** -Option, um die aktuell verwendete Definition in die Package-Definition aufzunehmen.
* Verwenden Sie die **[!UICONTROL Installationsskript einschließen]** -Option, um ein JavaScript-Skript hinzuzufügen, das beim Package-Import ausgeführt werden soll. Wenn ausgewählt, wird eine **[!UICONTROL Skript]** im Bildschirm zur Package-Definition hinzugefügt.
* Verwenden Sie die **[!UICONTROL Standardwerte einschließen]** -Option, um dem Paket die Werte aller Entitätsattribute hinzuzufügen.

  Diese Option ist nicht standardmäßig ausgewählt, um lange Exporte zu vermeiden. Das bedeutet, dass Attribute von Entitäten mit Standardwerten (&#39;empty string&#39;, &#39;0&#39; und &#39;false&#39;, falls im Schema nicht anders definiert) nicht zum Package hinzugefügt und daher nicht exportiert werden.

  >[!CAUTION]
  >
  >Wenn die Instanz, in die das Package importiert wird, Entitäten enthält, die mit denen des Pakets identisch sind (z. B. mit derselben externen ID), werden deren Attribute nicht aktualisiert. Dies kann vorkommen, wenn die Attribute der vorherigen Instanz Standardwerte aufweisen, da sie nicht im Paket enthalten sind. In diesem Fall würde durch Auswählen der Option **[!UICONTROL Standardwerte einschließen]** die Versionszusammenführung verhindert, da alle Attribute der vorherigen Instanz mit dem Package exportiert würden.

### Packages über eine Package-Definition exportieren {#export-packages-from-a-package-definition}

Gehen Sie wie folgt vor, um ein Package über eine Package-Definition zu exportieren:

1. Wählen Sie die zu exportierende Package-Definition aus und klicken Sie auf die Schaltfläche **[!UICONTROL Aktionen]** und wählen Sie **[!UICONTROL Package exportieren]**.
1. Überprüfen Sie den Namen und den Speicherort der exportierten Datei.
1. Klicken Sie auf **[!UICONTROL Starten]** -Schaltfläche, um den Export zu starten.

## Packages importieren {#import-packages}

Auf den Package-Import-Assistenten kann über das Hauptmenü zugegriffen werden **[!UICONTROL Tools > Erweitert > Package importieren]** der Client-Konsole.

### Package von einer Datei aus installieren {#install-a-package-from-a-file}

Gehen Sie wie folgt vor, um ein vorhandenes Datenpaket zu importieren:

1. Zugriff auf den Import-Assistenten über das Hauptmenü **[!UICONTROL Tools > Erweitert > Package importieren]** der Client-Konsole.
1. Wählen Sie die XML-Datei aus und klicken Sie auf **[!UICONTROL Öffnen]**.

Der Inhalt des zu importierenden Packages wird daraufhin im mittleren Bereich des Assistenten angezeigt.

Klicken Sie auf **[!UICONTROL Weiter]** und **[!UICONTROL Starten]**, um den Import zu beginnen.

### Native Packages installieren {#install-a-standard-package}

Integrierte Pakete (auch bekannt als -Standardpakete) installiert werden, wenn der Adobe Campaign konfiguriert ist. Je nach Ihren Berechtigungen, Ihrem Bereitstellungsmodell und Ihrem Produktangebot können Sie neue Standard-Packages importieren.

Entnehmen Sie Ihrem Lizenzvertrag, welche Packages Sie installieren können.

## Best Practices für Daten-Packages {#data-package-best-practices}

In diesem Abschnitt wird beschrieben, wie Sie Datenpackages während der ganzen Projektlaufzeit einheitlich organisieren können.


### Versionen

Importieren Sie immer in dieselbe Version der Plattform. Sie müssen Ihre Packages zwischen zwei Instanzen bereitstellen, die denselben Build aufweisen. Erzwingen Sie den Import niemals und aktualisieren Sie immer zuerst die Plattform (wenn der Build abweicht).

>[!IMPORTANT]
>
>Das Importieren zwischen verschiedenen Versionen wird von Adobe nicht unterstützt.

Achten Sie auf das Schema und die Datenbankstruktur. Auf den Import eines Packages mit Schema muss die Schemaerstellung folgen.

### Package-Typen {#package-types}

Definieren Sie zunächst verschiedene Package-Typen. Es werden nur vier Typen verwendet:

**Entitäten**

* Alle &quot;xtk&quot;- und &quot;nms&quot;-spezifischen Elemente in Adobe Campaign wie Schemata, Formulare, Ordner, Versandvorlagen usw.
* Sie können eine Entität sowohl als &quot;Admin&quot;- als auch als &quot;Plattform&quot;-Element betrachten.
* Sie sollten in ein Package, das Sie in eine Campaign-Instanz hochladen möchten, nicht mehr als eine Entität einschließen.

Wenn Sie Ihre Konfiguration in einer neuen Instanz bereitstellen müssen, können Sie alle Ihre Entitäts-Packages importieren.

**Funktionen**

Dieser Package-Typ:
* Ist eine Reaktion auf eine Kundenanfrage/Spezifikation.
* Enthält eine oder mehrere Funktionen.
* Sollte alle Abhängigkeiten enthalten, um die Funktionen ohne weitere Packages ausführen zu können.

**Kampagnen**

Dieses Package ist nicht obligatorisch. Manchmal ist es sinnvoll, einen bestimmten Typ für alle Kampagnen zu erstellen, selbst wenn eine Kampagne als Funktion betrachtet werden kann.

**Aktualisierungen**

Nach der Konfiguration kann eine Funktion in eine andere Umgebung exportiert werden. Beispielsweise kann das Package aus einer Entwicklungsumgebung in eine Testumgebung exportiert werden. Bei diesem Test wurde ein Fehler festgestellt. Zunächst muss er in der Entwicklungsumgebung behoben werden. Dann muss der Patch auf die Testplattform angewendet werden.

Die erste Lösung bestünde darin, die gesamte Funktion erneut zu exportieren. Um jedoch jegliches Risiko zu vermeiden (d. h. Aktualisieren unerwünschter Elemente), ist es sicherer, ein Package zu nutzen, das nur die Korrektur enthält.

Daher empfehlen wir, ein &quot;Aktualisierungs&quot;-Paket zu erstellen, das nur einen Entitätstyp der Funktion enthält.

Eine Aktualisierung kann nicht nur aus einer Fehlerbehebung, sondern auch aus einem neuen Element Ihrer Entität/Funktion bzw. Ihres Kampagnen-Packages bestehen. Um eine Bereitstellung des gesamten Packages zu vermeiden, können Sie ein Aktualisierungs-Package exportieren.

### Namenskonventionen {#data-package-naming}

Da die Typen jetzt definiert sind, sollte nun eine Namenskonvention festgelegt werden. Adobe Campaign erlaubt keine Erstellung von Unterordnern für Package-Spezifikationen, d. h. Zahlen sind die beste Lösung, um eine übersichtliche Struktur beizubehalten. Zahlen setzen Paketnamen voran.

Sie können beispielsweise die folgende Konvention verwenden:

* Entität: 1 bis 99
* Funktion: 100 bis 199
* Kampagne: von 200 bis 299
* Aktualisierung: 5000 bis 5999

#### Reihenfolge von Entitäts-Packages {#entity-packages-order}

Um den Import zu erleichtern, sollten Entitäts-Packages so angeordnet sein, wie sie importiert werden sollen.

Beispiel:

* 001 – Schema
* 002 – Formular
* 003 – Bilder
* etc.

>[!NOTE]
>
>Forms sollte nur importiert werden **after** Schemaaktualisierungen.


#### Package-Dokumentation {#package-documentation}

Wenn Sie ein Package aktualisieren, sollten Sie stets einen Kommentar in das Beschreibungsfeld eingeben, um sämtliche Änderungen und Gründe (z. B. &quot;Hinzufügen eines neuen Schemas&quot; oder &quot;Beheben eines Fehlers&quot;) genau zu dokumentieren.

Es empfiehlt sich auch, das Datum der Aktualisierung anzugeben.

>[!IMPORTANT]
>
>Das Beschreibungsfeld darf maximal 2.000 Zeichen enthalten.

