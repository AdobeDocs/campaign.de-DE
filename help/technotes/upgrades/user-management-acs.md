---
title: Migration von technischen Benutzerinnen und Benutzern zur Adobe Developer Console
description: Erfahren Sie, wie Sie die Benutzerzugriffsverwaltung von Campaign Standard zu Campaign V8 migrieren.
feature: Technote
role: Admin
source-git-commit: ccd60b7ff54bb538ae21693eff41a3943f1c6c88
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 4%

---

# Benutzerzugriffsverwaltung von Campaign Standard zu Campaign V8 {#user-management-acs}

Sowohl Adobe Campaign Standard als auch Adobe Campaign V8 ermöglichen es Benutzern, Berechtigungen für verschiedene Benutzer/Benutzer zu definieren und zu verwalten. Diese Berechtigungen bestehen aus bestimmten Berechtigungen, die Benutzern Zugriff auf verschiedene Funktionen des Produkts gewähren. Die beiden Produkte verwenden jedoch unterschiedliche Ansätze und Implementierungen zum Verwalten des Benutzerzugriffs.

Die folgenden Konzepte werden in Adobe Campaign Standard und Campaign V8 verwendet, um die Benutzerzugriffsverwaltung zu ermöglichen:

| Campaign Standard | Campaign v8 |
|---------|----------|
| Benutzer | Operator |
| Rolle | Benannte Berechtigung |
| Sicherheitsgruppe | Benutzergruppe |
| Organizational unit | Ordnerberechtigungen |

## Migrationsansatz von Sicherheitsgruppe zu Benutzergruppe

>[!CAUTION]
>
>Die Funktionen dieser Rollen/spezifischen Berechtigungen können bei der Implementierung variieren und möglicherweise Autorisierungsprobleme verursachen (z. B. Berechtigungshöhe oder Funktionsstörungen). Wir empfehlen Benutzern, diese Zuordnungen nach der Umstellung zu überprüfen, um eine ordnungsgemäße Zugriffskontrolle sicherzustellen. [Weitere Informationen zu Berechtigungen](../../v8/start/manage-permissions.md)

In der folgenden Tabelle wird der Migrationsprozess für Benutzergruppen bei der Umstellung von Adobe Campaign Standard auf Campaign V8 beschrieben. Im Campaign Standard wird eine **Sicherheitsgruppe**, die in Campaign V8 als **Benutzergruppe** bezeichnet wird, verwendet, um einem Benutzer eine Reihe von Rollen zuzuweisen. Einige Sicherheitsgruppen/Benutzergruppen sind zwar standardmäßig verfügbar, Benutzer können jedoch bei Bedarf neue Gruppen erstellen oder vorhandene Gruppen ändern.

| | **Campaign Standard** | **Kampagne V8** |
|---------|----------|---------|
| **Terminologie**  | Sicherheitsgruppe | Benutzergruppe |

Sowohl in Adobe Campaign Standard als auch in Campaign V8 werden **Sicherheitsgruppen** und **Benutzergruppen** Produktprofilen in der Admin Console zugeordnet. Wenn Sie einem Benutzer eine **Sicherheitsgruppe** oder eine **Benutzergruppe** zuweisen möchten, können Sie das entsprechende **Produktprofil** in der Admin Console verknüpfen. Diese Zuordnung wird synchronisiert, wenn sich der Benutzer anmeldet. [Weitere Informationen zum Produktprofil](../../v8/start/manage-permissions.md)

| **Campaign Standard-Sicherheitsgruppe** | **Benutzer der Kampagne V8** |
|----------|---------|
| Administratoren | Administratoren |
| Versand-Verantwortliche | Administratoren |
| Workflow-Verantwortliche | Workflow-Supervisoren  |

## Migrationsansatz von Benutzerrollen zu spezifischen Berechtigungen

In Adobe Campaign Standard wird der Begriff **Benutzerrolle** in Campaign V8 als **Spezifisches Recht** bezeichnet. In der folgenden Tabelle finden Sie die Terminologie für **Spezifische Berechtigungen** in Campaign V8, die **Benutzerrollen** in Campaign Standard entspricht.

| **Benutzerrolle &quot;Campaign Standard&quot;** | **Kampagne V8 Benannte Berechtigung** | **Beschreibung**  |
|----------|---------|---------|
| Administration | Administration | Benutzer mit Administratorrechten haben vollen Zugriff auf die Instanz. |
| Datenmodell  | Administration | Berechtigung zum Ausführen von Veröffentlichungen und Erstellen benutzerdefinierter Ressourcen. Funktionen zur Schemaerstellung, die Administratoren in Campaign V8 zur Verfügung stehen.  |
| Zustellbarkeit  | Administration  | Validierung von zuvor analysierten Sendungen.  |
| Exportieren | Exportieren | Recht auf Export von Daten.  |
| Dateizugriff  | Dateizugriff  | Validierung von zuvor analysierten Sendungen.  |
| Allgemeiner Import  | Import  | Recht auf allgemeinen Datenimport |
| Sendungen vorbereiten | Sendungen vorbereiten | Berechtigung zum Erstellen, Ändern, Vorbereiten und Löschen von Sendungen.  |
| SQL Script-Ausführung | SQL Script-Ausführung | Berechtigt zur Ausführung von SQL-Befehlen direkt in der Datenbank. |
| Sendungen starten  | Sendungen starten  | Validierung von zuvor analysierten Sendungen.  |
| Ausführung des Systembefehls | Programmausführung | Berechtigung zum Ausführen von Systembefehlen auf dem Server. |
| Workflow | Workflow | Berechtigung zum Verwalten der Ausführung von Workflows: Start, Stopp, Pause usw. |

## Migrationsansatz von Organisationseinheiten

In Adobe Campaign Standard wird die **Organisationseinheit** t dem vorhandenen **Ordner**-Hierarchiemodell in Campaign V8 zugeordnet, um eine ähnliche Zugriffskontrolle zu gewährleisten. [Weitere Informationen zur Ordnerverwaltung](../../v8/start/folder-permissions.md)

| | **Campaign Standard** | **Kampagne V8** |
|---------|----------|---------|
| **Terminologie**  | Organizational unit | Ordner |

## Migrationsansatz aus dem Programm

In Campaign V8 werden **Programme** als **Ordner** dargestellt. Campaign V8 ermöglicht die Erstellung von Ordnern und die Beschränkung des Zugriffs auf diese Ordner.

Durch die Verwendung von **Gruppen** und **Spezifische Berechtigungen** können **Benutzer** Zugriff auf bestimmte **Ordner** innerhalb der Navigationshierarchie erhalten, mit der Möglichkeit, Lese-, Schreib- und Löschberechtigungen zuzuweisen. [Weitere Informationen zur Ordnerverwaltung](../../v8/start/folder-permissions.md)

Da ein **Programm** in Campaign V8 als **Ordner** behandelt wird, kann sein Zugriff auf dieselbe Weise wie jeder andere Ordner verwaltet werden. Nach der Migration können Campaign Standard-Administratoren die folgenden Schritte ausführen:

1. Klicken Sie im Explorer mit der rechten Maustaste auf einen beliebigen Ordner und wählen Sie **[!UICONTROL Eigenschaften...]**.
1. Navigieren Sie zur Registerkarte **[!UICONTROL Sicherheit]** .
1. Ändern Sie die Benutzergruppenberechtigungen gemäß dem gewünschten Zugriffsmodell. 

## Produktprofilzuordnung für den Zugriff auf REST-APIs 

Für den Zugriff auf Transaktions-APIs über die Ausführungsinstanz in Campaign V8 ist zusätzlich zu den Produktprofilen **Administrator** und **Message Center** ein neues **Produktprofil** erforderlich. Dieses neue **Produktprofil** wird vorhandenen oder vorab erstellten technischen Konten in Campaign Standard hinzugefügt.

Nach der Migration sollten Campaign Standard ihre **Produktprofilzuordnungen** überprüfen und das entsprechende **Produktprofil** zuweisen, wenn sie ihre **technischen Konten** nicht mit dem Produktprofil **Administrator** verknüpfen möchten. Für zukünftige Integrationen wird empfohlen, die Campaign V8 **Mandanten-ID** in der **REST-URL** anstelle des vorherigen Campaign Standards **Mandanten-ID** zu verwenden.

## Migration des Zugriffs auf native Campaign-Ressourcen für Campaign Standard-Benutzer

Benutzer, die von Campaign Standard migriert werden, erhalten Lesezugriff auf bestimmte integrierte Ressourcen in Campaign V8.

## Nicht migrierte Sicherheitsgruppen und Rollen {#non-migrated-groups-roles}

Im Folgenden finden Sie eine Liste der Campaign Standard-Rollen, die noch nicht umgestellt wurden:

* Standard-Relais-Konto 

* Message Center Push 

Unten finden Sie eine Liste der Campaign Standard-Sicherheitsgruppen-Mappings, die noch nicht übergeben wurden.

* Message Center Agents

* Message Center Push Agents

* Anwendungsverantwortlicher für Adobe Experience Manager

* Relais-Konto
 


 

 


