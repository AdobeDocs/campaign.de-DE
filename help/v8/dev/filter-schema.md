---
title: Filtern von Campaign-Schemata
description: Erfahren Sie, wie Sie Campaign-Schemata filtern
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: ht
source-wordcount: '424'
ht-degree: 100%

---

# Filtern von Schemata{#filter-schemas}

## Systemfilter {#system-filters}

Sie können den Schema-Zugriff abhängig von Berechtigungen nach bestimmten Benutzern filtern. Mit Systemfiltern können Sie die Lese- und Schreibberechtigungen von Entitäten verwalten, die in Schemas beschrieben sind. Dabei verwenden Sie die Parameter **readAccess** und **writeAccess**.

>[!NOTE]
>
>Diese Einschränkung gilt nur für nicht-technische Benutzer: Ein technischer Benutzer mit entsprechenden Berechtigungen oder unter Verwendung eines Workflows kann die Daten abrufen und aktualisieren.

* **readAccess**: bietet schreibgeschützten Zugriff auf Schemadaten.

   **Warnung**  - Alle verknüpften Tabellen müssen mit derselben Einschränkung versehen werden. Diese Konfiguration kann die Leistung beeinträchtigen.

* **writeAccess**: bietet Schreibzugriff auf Schemadaten.

Diese Filter werden auf der **Hauptelementebene** der Schemata eingegeben und können, wie in den folgenden Beispielen gezeigt, zur Einschränkung des Zugriffs gebildet werden.

* SCHREIB-Berechtigungen beschränken

   Hier wird der Filter verwendet, um Betreibern ohne ADMINISTRATOR-Berechtigung die SCHREIB-Berechtigung für das Schema zu verweigern. Das bedeutet, dass nur Administratoren Schreibrechte für Entitäten haben, die durch dieses Schema beschrieben werden.

   ```
   <sysFilter name="writeAccess">      
    <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
   </sysFilter>
   ```

* Schränken Sie die LESE- und SCHREIB-Berechtigungen ein:

   Hier wird der Filter verwendet, um sowohl LESE- als auch SCHREIB-Berechtigungen für das Schema für alle Operatoren zu verbieten. Nur das **interne** Konto, dargestellt durch den Ausdruck &quot;$(loginId)!=0&quot;, hat diese Berechtigungen.

   ```
   <sysFilter name="readAccess"> 
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   
   <sysFilter name="writeAccess">  
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   ```

   Mögliche **expr**-Attributwerte, die zur Definition der Bedingung verwendet werden, sind TRUE oder FALSE.

>[!NOTE]
>
>Wenn kein Filter angegeben ist, verfügen alle Benutzer über Lese- und Schreibberechtigungen für das Schema.

## Integrierte Schemata schützen

Standardmäßig sind integrierte Schemata nur mit SCHREIB-Berechtigungen für Benutzer mit ADMINISTRATOR-Rechten zugänglich:

* ncm:publishing
* nl:monitoring
* nms:calendar
* xtk:builder
* xtk:connections
* xtk:dbInit
* xtk:entityBackupNew
* xtk:entityBackupOriginal
* xtk:entityOriginal
* xtk:form
* xtk:funcList
* xtk:fusion
* xtk:image
* xtk:javascript
* xtk:jssp
* xtk:jst
* xtk:navtree
* xtk:operatorGroup
* xtk:package
* xtk:queryDef
* xtk:resourceMenu
* xtk:rights
* xtk:schema
* xtk:scriptContext
* xtk:specFile
* xtk:sql
* xtk:sqlSchema
* xtk:srcSchema
* xtk:strings
* xtk:xslt

>[!CAUTION]
>
>LESE- und SCHREIB-Berechtigungen für das Schema **xtk:sessionInfo** sind nur über das interne Konto einer Adobe Campaign-Instanz zugänglich.

## Systemfilter der integrierten Schemata ändern

Integrierte Schemata sind geschützt, um Kompatibilitätsprobleme mit älteren Versionen zu vermeiden. Adobe empfiehlt Ihnen, die Standard-Schemaparameter nicht zu ändern, um optimale Sicherheit zu gewährleisten.

In bestimmten Kontexten kann es jedoch erforderlich sein, die Systemfilter der integrierten Schemata zu ändern. Gehen Sie dazu wie folgt vor:

1. Erstellen Sie eine Erweiterung für das integrierte Schema oder öffnen Sie eine vorhandene Erweiterung.
1. Fügen Sie ein untergeordnetes Element **`<sysfilter name="<filter name>" _operation="delete"/>`** im Hauptelement hinzu, um den Filter unter demselben Element im integrierten Schema zu ignorieren.
1. Sie können einen neuen Filter hinzufügen, wie im Abschnitt [Systemfilter](#system-filters) beschrieben.
