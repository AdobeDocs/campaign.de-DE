---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 73%
---
# Erbauer

Erzeugungsdienste des Anwendungs-Servers

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [BuildOutputNavTree](sm-builder-buildoutputnavtree.md) | Führt die Navigationsbaum-Definitionen der Datenbank mit der als Parameter übermittelten Definition zusammen. |
| [BuildOutputSchema](sm-builder-buildoutputschema.md) | Erstellt ein Schema basierend auf einem Quellschema. |
| [buildSchema](sm-builder-buildschema.md) | Erstellt ein Schema basierend auf einem Quellschema. |
| [buildSchemaFromId](sm-builder-buildschemafromid.md) | Erzeugt ein Schema basierend auf der Kennung eines Quellschemas. |
| [BuildSqlSchemaDiff](sm-builder-buildsqlschemadiff.md) | Erzeugt ein Dokument, das die Unterschiede zwischen der physischen Datenbank und ihrer logischen Beschreibung aufzeigt. |
| [BuildUpdateOneSchemaDiff](sm-builder-buildupdateoneschemadiff.md) | Erzeugt ein Dokument, das die Unterschiede zwischen einer Tabelle der physischen Datenbank und der logischen Beschreibung dieser Tabelle aufzeigt. |
| [BuildUpdateSchemaDiff](sm-builder-buildupdateschemadiff.md) | Erzeugt ein Dokument, das die Unterschiede zwischen der physischen Datenbank und ihrer logischen Beschreibung aufzeigt. |
| [CheckTableExists](sm-builder-checktableexists.md) | Prüft, ob eine Tabelle in der Datenbank existiert |
| [CreateDb](sm-builder-createdb.md) | Erstellt die Datenbank |
| [JavaScript auswerten](sm-builder-evaluatejavascript.md) | Auswertung eines JavaScript-Codes |
| [EvaluateJavaScriptTemplate](sm-builder-evaluatejavascripttemplate.md) | Auswertung eines JavaScript-Templates (JST) |
| [ExecSql](sm-builder-execsql.md) | Führt einen SQL-Befehl aus |
| [ExecSqlScript](sm-builder-execsqlscript.md) | Führt ein SQL-Script aus |
| [GenCreateDbDDL](sm-builder-gencreatedbddl.md) | Erzeugt das SQL-Script zur Datenbankerstellung. |
| [GenCreateOrUpdateSchemaSequenceDDL](sm-builder-gencreateorupdateschemasequenceddl.md) | Erzeugt das SQL-Script, mit dem die autopk-Schemasequenz erstellt oder aktualisiert wird |
| [GenerateNavTree](sm-builder-generatenavtree.md) | Fusioniert alle Navigationsbaum-Definitionen und speichert das Ergebnis als &#39;xtk:merged&#39;. |
| [GenerateSchema](sm-builder-generateschema.md) | Erzeugt den Code eines Schemas basierend auf High-Level-Parametern. |
| [GetDbParams](sm-builder-getdbparams.md) | Ruft aktuelle Parameter der Datenquelle ab. |
| [GetDefaultNamespace](sm-builder-getdefaultnamespace.md) | Abrufen des Standard-Namespace |
| [InstallPackage](sm-builder-installpackage.md) | Package installieren |
| [InstallPackageImpl](sm-builder-installpackageimpl.md) | Package installieren (interne Methode, bitte nicht benutzen). |
| [InstallVendorPackages](sm-builder-installvendorpackages.md) | Standard-Package(s) installieren |
| [RemoveSchemaLinkRef](sm-builder-removeschemalinkref.md) | Löscht das Schema und Bezüge zu Umkehrrelationen. |
| [ResolvePackageReferences](sm-builder-resolvepackagereferences.md) | Löst die im Package enthaltenen Abhängigkeiten |
| [UpdateDb](sm-builder-updatedb.md) | Datenbank aktualisieren |
| [UpdateSchemaFromDatabase](sm-builder-updateschemafromdatabase.md) | Aktualisiert ein Schema ausgehend von seiner physischen Darstellung in der Datenbank. |
| [UpdateTempSchemasFromDatabase](sm-builder-updatetempschemasfromdatabase.md) | Aktualisiert eine Schematasammlung ausgehend von ihrer physischen Darstellung in der Datenbank. |

## Generische Methoden

| Methode | Beschreibung |
| --- | --- |
| [Erstellen](f-create.md) | Erstellt eine neue Entität, die einem bestimmten Schema entspricht. |
| [LOAD](f-load.md) | Lädt eine Entität, die einem bestimmten Schema und Schlüssel entspricht, und gibt sie zurück. |
| [Speichern](m-entity-save.md) | Speichert eine Entität in der Datenbank |
