---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 6%
---
# DBEngine (Klasse)

Stellt eine Datenbankverbindung dar.

Mit diesem Objekt können Sie die Datenbank abfragen und zugehörige Vorgänge ausführen.

Die meisten Methoden in dieser Klasse erfordern „SQL“-Rechte. Wenn der Operator eine Methode aufruft und nicht über die entsprechenden Rechte verfügt, wird eine Ausnahme ausgelöst. Im Allgemeinen erfordern alle Methoden, die die Datenbank ändern, „SQL“-Rechte, während Methoden, die einfach Informationen anzeigen, dies nicht tun. In der Dokumentation zu den einzelnen Methoden finden Sie Informationen darüber, ob die Berechtigungen erforderlich sind.

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [batchDelete](m-dbengine-batchdelete.md) | Löscht die Datensätze einer Tabelle nach Paketen. |
| [dispose](m-dbengine-dispose.md) | Gibt die Verbindung von allen damit verbundenen Ressourcen frei. |
| [Ausführen](m-dbengine-execute.md) | Führt einen SQL-Befehl aus. |
| [exec](m-dbengine-exec.md) | Alias des Befehls „execute“. Diese Funktion ist veraltet. Verwenden Sie [execute()](m-dbengine-execute.md) |
| [Abfrage](m-dbengine-query.md) | Führt eine SQL-Abfrage vom Typ SELECT aus. |
| [queryWithTypes](m-dbengine-querywithtypes.md) | Führt eine SQL-Abfrage vom Typ SELECT mit der Spaltenspezifikation aus. |
| [begin](m-dbengine-begin.md) | Startet eine neue Transaktion für die Verbindung |
| [commit](m-dbengine-commit.md) | Validiert die laufende Transaktion für die Verbindung. |
| [rollback](m-dbengine-rollback.md) | Bricht die laufende Transaktion für die Verbindung ab. |

## Eigenschaften

| Eigenschaft | Beschreibung |
| --- | --- |
| [isOracle](p-dbengine-isoracle.md) | Gibt „true“ zurück, wenn die Datenbank Oracle ist. |
| [isDB2](p-dbengine-isdb2.md) | Gibt „true“ zurück, wenn die Datenbank vom Typ DB2 ist. |
| [isMySQL](p-dbengine-ismysql.md) | Gibt „true“ zurück, wenn die Datenbank vom Typ MySQL ist. |
| [isMSSQL](p-dbengine-ismssql.md) | Gibt „true“ zurück, wenn die Datenbank SQL Server ist. |
| [isPostgreSQL](p-dbengine-ispostgresql.md) | Gibt „true“ zurück, wenn die Datenbank PostgreSQL ist. |
| [isSybase](p-dbengine-issybase.md) | Gibt „true“ zurück, wenn die Datenbank Sybase ist. |
| [isSybaseIQ](p-dbengine-issybaseiq.md) | Gibt „true“ zurück, wenn die Datenbank Sybase IQ ist. |
| [isFDA](p-dbengine-isfda.md) | Gibt „true“ zurück, wenn über FDA auf die Datenbank zugegriffen wird. |
| [isBroken](p-dbengine-isbroken.md) | Gibt „true“ zurück, wenn die Verbindung nicht mehr verwendet werden kann. |
| [useUnicodeData](p-dbengine-useunicodedata.md) | Gibt „true“ zurück, wenn die Datenbank Unicode-Daten enthält. |
| [useNChar](p-dbengine-usenchar.md) | Gibt „true“ zurück, wenn Adobe Campaign Felder vom Typ „NCHAR“, „NVARCHAR“, „NCLOB“ oder „NTEXT“ verwendet. |

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
