---
solution: Campaign v8
product: Adobe Campaign
title: Neues Schema in Campaign erstellen
description: Erfahren Sie, wie Sie in Campaign ein neues Schema erstellen
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 2%

---

# Neues Schema erstellen{#create-new-schema}

Um die Schemata zu bearbeiten, zu erstellen und zu konfigurieren, klicken Sie auf den Knoten **[!UICONTROL Administration > Konfiguration > Datenschemata]** der Adobe Campaign-Clientkonsole.

>[!NOTE]
>
>Integrierte Datenschemata können nur von einem Administrator Ihrer Adobe Campaign Classic-Konsole gelöscht werden.

![](assets/schema_navtree.png)

Der Tab **[!UICONTROL Bearbeiten]** zeigt den XML-Inhalt eines Schemas an:

![](assets/schema_edition.png)

>[!NOTE]
>
>Im Eingabefeld &quot;Name&quot; können Sie den Schemaschlüssel eingeben, der aus Name und Namespace besteht. Die Attribute &quot;name&quot;und &quot;namespace&quot;des Stammelements des Schemas werden automatisch im XML-Bearbeitungsbereich des Schemas aktualisiert. Beachten Sie, dass einige Namespaces nur intern sind. [Weitere Informationen](schemas.md#reserved-namespaces).

Der Tab **[!UICONTROL Vorschau]** generiert automatisch das erweiterte Schema:

![](assets/schema_edition2.png)

>[!NOTE]
>
>Beim Speichern des Quellschemas wird die Generierung des erweiterten Schemas automatisch gestartet.

Wenn Sie die vollständige Struktur eines Schemas überprüfen müssen, können Sie die Registerkarte **[!UICONTROL Vorschau]** verwenden. Wenn das Schema erweitert wurde, können Sie alle seine Erweiterungen visualisieren. Als Ergänzung werden im Tab **[!UICONTROL Dokumentation]** alle Schemaattribute und -elemente sowie deren Eigenschaften (SQL-Feld, Typ/Länge, Titel, Beschreibung) angezeigt. Die Registerkarte **[!UICONTROL Dokumentation]** gilt nur für erstellte Schemata.

## Anwendungsfall: Erstellen einer Vertragstabelle {#example--creating-a-contract-table}

Im folgenden Beispiel erstellen Sie eine neue Tabelle für **Contracts** in der Datenbank. In dieser Tabelle können Sie für jeden Vertrag Vor- und Nachnamen sowie E-Mail-Adressen von Inhabern und Mitinhabern speichern.

Erstellen Sie dazu das Schema der Tabelle und aktualisieren Sie die Datenbankstruktur, um die entsprechende Tabelle zu erstellen. Die detaillierten Schritte sind unten aufgeführt.

1. Bearbeiten Sie den Knoten **[!UICONTROL Administration > Konfiguration > Datenschemata]** des Adobe Campaign-Baums und klicken Sie auf **[!UICONTROL Neu]**.
1. Wählen Sie die Option **[!UICONTROL Neue Tabelle in der Datenvorlage erstellen]** und klicken Sie auf **[!UICONTROL Weiter]** .

   ![](assets/create_new_schema.png)

1. Geben Sie einen Namen für die Tabelle und einen Namespace an.

   ![](assets/create_new_param.png)

   >[!NOTE]
   >
   >Standardmäßig werden von Benutzern erstellte Schemata im Namespace &quot;cus&quot;gespeichert. Weitere Informationen hierzu finden Sie unter [Identifizierung eines Schemas](extend-schema.md#identification-of-a-schema).

1. Erstellen Sie den Inhalt der Tabelle. Es wird empfohlen, den dedizierten Assistenten zu verwenden, um sicherzustellen, dass keine Einstellungen fehlen. Klicken Sie dazu auf die Schaltfläche **[!UICONTROL Einfügen]** und wählen Sie den hinzuzufügenden Einstellungstyp aus.

   ![](assets/create_new_content.png)

1. Definieren Sie die Einstellungen für die Vertragstabelle:

   ```
   <srcSchema created="YYYY-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" lastModified="YYYY-MM-DD HH:MM:SS.TZ"
           mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
      <element dataSource="nms:extAccount:ffda" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" name="Contracts">
           <attribute name="holderName" label="Holder last name" type="string"/>
           <attribute name="holderFirstName" label="Holder first name" type="string"/>
           <attribute name="holderEmail" label="Holder email" type="string"/>
           <attribute name="co-holderName" label="Co-holder last name" type="string"/>           
           <attribute name="co-holderFirstName" label="Co-holder first name" type="string"/>           
           <attribute name="co-holderEmail" label="Co-holder email" type="string"/>    
           <attribute name="date" label="Subscription date" type="date"/>     
           <attribute name="noContract" label="Contract number" type="long"/> 
      </element>
   </srcSchema>
   ```

   Fügen Sie den Typ der Auflistung des Vertrags hinzu.

   ```
   <srcSchema created="AA-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png" label="Contracts" labelSingular="Contract" AA-MM-DD HH:MM:SS.TZ"mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
      <enumeration basetype="byte" name="typeContract">
         <value label="Home" name="home" value="0"/>
         <value label="Car" name="car" value="1"/>
         <value label="Health" name="health" value="2"/>
         <value label="Pension fund" name="pension fund" value="2"/>
      </enumeration>
      <element dataSource="nms:extAccount:ffda" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" name="Contracts">
           <attribute name="holderName" label="Holder last name" type="string"/>
           <attribute name="holderFirstName" label="Holder first name" type="string"/>
           <attribute name="holderEmail" label="Holder email" type="string"/>
           <attribute name="co-holderName" label="Co-holder last name" type="string"/>           
           <attribute name="co-holderFirstName" label="Co-holder first name" type="string"/>           
           <attribute name="co-holderEmail" label="Co-holder email" type="string"/>    
           <attribute name="date" label="Subscription date" type="date"/>     
           <attribute name="noContract" label="Contract number" type="long"/> 
      </element>
   </srcSchema>
   ```

1. Speichern Sie das Schema und klicken Sie auf die Registerkarte **[!UICONTROL Struktur]** , um die Struktur zu generieren:

   ![](assets/configuration_structure.png)

1. Aktualisieren Sie die Datenbankstruktur, um die Tabelle zu erstellen, mit der das Schema verknüpft werden soll. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](update-database-structure.md).

