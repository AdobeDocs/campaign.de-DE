---
title: Filtern von Kampagnenschemata
description: Erfahren Sie, wie Sie Campaign-Schemata filtern
source-git-commit: e0faeda87d5b84309524a72d9f021c381ac4619e
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 1%

---

# Filterschemata{#filter-schemas}

## Systemfilter {#system-filters}

Sie können den Schemazugriff nach bestimmten Benutzern filtern, abhängig von deren Berechtigungen. Mit Systemfiltern können Sie die Lese- und Schreibberechtigungen von Entitäten verwalten, die in Schemas beschrieben sind, und dabei die Parameter **readAccess** und **writeAccess** verwenden.

>[!NOTE]
>
>Diese Einschränkung gilt nur für nicht technische Benutzer: Ein technischer Benutzer mit entsprechenden Berechtigungen oder mithilfe eines Workflows kann Daten abrufen und aktualisieren.

* **readAccess**: bietet schreibgeschützten Zugriff auf Schemadaten.

   **Warnung**  - Alle verknüpften Tabellen müssen mit derselben Einschränkung versehen werden. Diese Konfiguration kann sich auf die Leistung auswirken.

* **writeAccess**: bietet Schreibzugriff auf Schemadaten.

Diese Filter werden auf der Hauptseite **element** der Schemas eingegeben und können, wie in den folgenden Beispielen gezeigt, gebildet werden, um den Zugriff zu beschränken.

* SCHREIBberechtigungen beschränken

   Hier wird der Filter verwendet, um WRITE-Berechtigungen für das Schema für Benutzer ohne ADMINISTRATION zu verweigern. Dies bedeutet, dass nur Administratoren Schreibberechtigungen für Entitäten haben, die von diesem Schema beschrieben werden.

   ```
   <sysFilter name="writeAccess">      
    <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
   </sysFilter>
   ```

* READ- und WRITE-Berechtigungen beschränken:

   Hier wird der Filter verwendet, um die LESE- und WRITE-Berechtigungen für das Schema für alle Operatoren zu deaktivieren. Nur das Konto **internal**, dargestellt durch den Ausdruck &quot;$(loginId)!= 0&quot;, hat diese Berechtigungen.

   ```
   <sysFilter name="readAccess"> 
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   
   <sysFilter name="writeAccess">  
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   ```

   Mögliche **expr** Attributwerte, die zur Definition der Bedingung verwendet werden, sind TRUE oder FALSE.

>[!NOTE]
>
>Wenn kein Filter angegeben ist, verfügen alle Benutzer über Lese- und Schreibberechtigungen für das Schema.

## Integrierte Schemata in Protect

Standardmäßig sind integrierte Schemata nur mit WRITE-Berechtigungen für Benutzer mit ADMINISTRATION-Rechten zugänglich:

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
>Lese- und WRITE-Berechtigungen für das Schema **xtk:sessionInfo** sind nur für das interne Konto einer Adobe Campaign-Instanz zugänglich.

## Systemfilter integrierter Schemata ändern

Integrierte Schemata sind geschützt, um Kompatibilitätsprobleme mit älteren Versionen zu vermeiden. Adobe empfiehlt, die Standardschemaparameter nicht zu ändern, um eine optimale Sicherheit zu gewährleisten.

In bestimmten Kontexten müssen Sie jedoch möglicherweise die Systemfilter der integrierten Schemas ändern. Gehen Sie dazu wie folgt vor:

1. Erstellen Sie eine Erweiterung für das integrierte Schema oder öffnen Sie eine vorhandene Erweiterung.
1. Fügen Sie ein untergeordnetes Element **`<sysfilter name="<filter name>" _operation="delete"/>`** im Hauptelement hinzu, um den Filter im integrierten Schema unter demselben zu ignorieren.
1. Sie können einen neuen Filter hinzufügen, wie im Abschnitt [Systemfilter](#system-filters) beschrieben.
