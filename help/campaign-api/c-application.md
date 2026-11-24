---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 7%
---
# application (class)

Diese Klasse verfügt über eine einzige Instanz, die Zugriff auf bestimmte Eigenschaften des Anwendungsservers bietet. Auf dieses Singleton kann über die globale Variable `application` zugegriffen werden.

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [hasPackage](m-application-haspackage.md) | Testet, ob ein Paket installiert ist. |
| [getSchema](m-application-getschema.md) | Gibt eine Zuordnung zu einem Adobe Campaign-Schema zurück oder null, wenn das Schema nicht vorhanden ist. |
| [getDBMSType](m-application-getdbmstype.md) | Gibt den Servertyp der Datenbank zurück. |
| [getNewIds](m-application-getnewids.md) | Gibt eine Liste der IDs der internen Datenbankschlüssel zurück. |
| [getConnection](m-application-getconnection.md) | Gibt eine neue Verbindung zum Datenbankserver zurück. |
| [getTimezoneJson](m-application-gettimezonejson.md) | Gibt eine Zeichenfolge zurück, die die JSON-Darstellung der Liste der Zeitunterschiede mit UTC-Zeit und ihrem Startdatum im Vergleich zum UNIX-Zeitraum für eine Zeitzone ist. |
| [onLog](m-application-onlog.md) | Fügt eine Abfangfunktion für die in das Protokoll geschriebenen Nachrichten hinzu oder löscht sie. |
| [onTrace](m-application-ontrace.md) | Fügt eine Abfangfunktion für Ablaufverfolgungsmeldungen hinzu oder löscht sie. |

## Eigenschaften

| Eigenschaft | Beschreibung |
| --- | --- |
| [buildNumber](p-application-buildnumber.md) | Gibt die Build-Nummer des Anwendungs-Servers aus |
| [instanceName](p-application-instancename.md) | Name der Instanz, in der das Skript ausgeführt wird. |
| [instanceVarDir](p-application-instancevardir.md) | Vollständiger Pfad des &#39;var&#39;-Verzeichnisses für die Instanz, in der das Script ausgeführt wird |
| [instanceUploadDir](p-application-instanceuploaddir.md) | Vollständiger Pfad des &#39;upload&#39;-Verzeichnisses für die Instanz, in der das Script ausgeführt wird. |
| [Operator](p-application-operator.md) | Gibt ein -Objekt zurück, das Informationen zum aktuellen Operator enthält (Name, Kennungen, Rechte usw.). |
| [locale](p-application-locale.md) | Gibt einen String zurück, der der lokalen Instanz entspricht. |

## Funktionen

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
