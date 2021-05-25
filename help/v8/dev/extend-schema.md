---
solution: Campaign v8
product: Adobe Campaign
title: Campaign-Schemata erweitern
description: Erfahren Sie, wie Sie Campaign-Schemata erweitern
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 2%

---

# Erweitern eines Schemas{#extend-schemas}

Als technischer Benutzer können Sie das Datenmodell von Campaign an die Bedürfnisse Ihrer Implementierung anpassen: Elemente zu einem vorhandenen Schema hinzufügen, ein Element in einem Schema ändern oder Elemente löschen.

Die wichtigsten Schritte zur Anpassung des Campaign-Datenmodells sind:

1. Erstellen eines Erweiterungsschemas
1. Campaign-Datenbank aktualisieren
1. Anpassen des Eingabeformulars

>[!CAUTION]
>Das integrierte Schema darf nicht direkt geändert werden. Wenn Sie ein integriertes Schema anpassen müssen, müssen Sie es erweitern.

:bulb: Ein besseres Verständnis der in Campaign integrierten Tabellen und ihrer Interaktion finden Sie auf [dieser Seite](datamodel.md).

Gehen Sie wie folgt vor, um ein Schema zu erweitern:

1. Navigieren Sie im Explorer zum Ordner **[!UICONTROL Administration > Konfiguration > Datenschemata]** .
1. Klicken Sie auf die Schaltfläche **Neu** und wählen Sie **[!UICONTROL Erweitern Sie die Daten in einer Tabelle mit einem Erweiterungsschema]** aus.

   ![](assets/extend-schema-option.png)

1. Identifizieren Sie das zu erweiternde integrierte Schema und wählen Sie es aus.

   ![](assets/extend-schema-select.png)

   Benennen Sie das Erweiterungsschema standardmäßig mit dem integrierten Schema und verwenden Sie einen benutzerdefinierten Namespace.  Beachten Sie, dass einige Namespaces nur intern sind. [Weitere Informationen](schemas.md#reserved-namespaces).

   ![](assets/extend-schema-validate.png)

1. Fügen Sie im Schemaeditor mithilfe des Kontextmenüs die benötigten Elemente hinzu und speichern Sie sie.

   ![](assets/extend-schema-edit.png)

   Im folgenden Beispiel fügen wir das Attribut MembershipYear hinzu, legen eine Längenbegrenzung für den Nachnamen fest (diese Grenze überschreibt die standardmäßige) und entfernen das Geburtsdatum aus dem integrierten Schema.

   ![](assets/extend-schema-sample.png)

   ```
   <srcSchema created="YYYY-MM-DD" desc="Recipient table" extendedSchema="nms:recipient"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient" lastModified="YYYY-MM-DD"
           mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:srcSchema">
    <element desc="Recipient table" img="nms:recipient.png" label="Recipients" labelSingular="Recipient" name="recipient">
       <attribute label="Member since" name="MembershipYear" type="long"/>
       <attribute length="50" name="lastName"/>
       <attribute _operation="delete" name="birthDate"/>
   </element>
   </srcSchema>
   ```

1. Trennen Sie die Verbindung zu Campaign und stellen Sie die Verbindung wieder her, um die Aktualisierung der Schemastruktur im Tab **[!UICONTROL Struktur]** zu überprüfen.

   ![](assets/extend-schema-structure.png)

1. Aktualisieren Sie die Datenbankstruktur, um Ihre Änderungen anzuwenden. [Mehr dazu](update-database-structure.md)

1. Sobald die Änderungen in der Datenbank implementiert wurden, können Sie das Formular für die Empfängereingabe anpassen, um Ihre Änderungen sichtbar zu machen. [Mehr dazu](forms.md)
