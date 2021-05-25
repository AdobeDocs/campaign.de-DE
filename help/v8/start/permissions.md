---
solution: Campaign v8
product: Adobe Campaign
title: Berechtigungen für Campaign v8 gewähren
description: Erfahren Sie, wie Sie Campaign v8 Berechtigungen erteilen.
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 2%

---

# Erste Schritte mit Berechtigungen

In Adobe Campaign sind Benutzer **Operatoren** und **Benutzergruppen** repräsentieren Benutzerrollen.

Adobe Campaign verfügt über integrierte Benutzergruppen wie Campaign-Manager oder Workflow-Supervisoren. Alle integrierten Gruppen sind auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups) aufgeführt

Als Mitglied einer Benutzergruppe hat ein Benutzer die Berechtigung zum Ausführen von Vorgängen mit der Bezeichnung &quot;Spezifische Berechtigungen&quot;und Zugriff auf Daten, die in Ordnern in der Ansicht **Explorer** enthalten sind. Ein Benutzer kann mehreren Benutzergruppen angehören: -Berechtigungen und -Zugriffsberechtigungen sind additiv.

Spezifische Berechtigungen gewähren Berechtigungen für:

* Vorgänge durchführen
Beispielsweise ist die Schaltfläche **Analysieren** im Versand-Editor für Mitglieder der Gruppe **Versand-Operator** aktiviert, die über die Gruppe **Versand vorbereiten** mit der Bezeichnung &quot;Right&quot;verfügen

* Ordnerzugriff
Die Mitgliedschaft in Benutzergruppen kann Zugriffsberechtigungen für Ordner gewähren oder beschränken, indem die [Sicherheitseinstellungen für Ordner](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder) geändert werden. Dies kann sich beispielsweise auf Folgendes auswirken: **Schreibzugriff** zum Erstellen neuer Entitäten (wie Sendungen, Profile usw.), **Lesezugriff** zum Verwenden von Entitäten, **Löschzugriff** zum Löschen von Entitäten.

**Mehr dazu**

* [Integrierte spezifische Berechtigungen](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html)

* [Integrierte Benutzergruppen](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

* [Schritte zum Einrichten von Berechtigungen](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html)
