---
title: Erste Schritte mit Berechtigungen in Campaign v8
description: Erfahren Sie mehr über die Schritte zum Definieren von Berechtigungen in Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: ht
source-wordcount: '515'
ht-degree: 100%

---

# Erste Schritte mit Berechtigungen{#gs-permissions}

Mit Adobe Campaign können Sie die den Benutzern zugewiesenen Rechte definieren und verwalten. Diese sind ein Satz von Rechten und Einschränkungen, die Folgendes ermöglichen oder verweigern:

* Zugriff auf bestimmte Fähigkeiten
* Zugriff auf bestimmte Daten
* Zugriff auf bestimmte Aktionen (Erstellen, Ändern, Löschen)

Diese Berechtigungen werden durch die Kombination von Benutzergruppenberechtigungen, spezifischen Berechtigungen und Berechtigungen für Ordner definiert.

In Adobe Campaign sind Anwender **Benutzer** und **Benutzergruppen** stehen für Benutzerrollen. Ein Benutzer ist in Adobe Campaign ein Anwender mit der Berechtigung, sich anzumelden und Aktionen durchzuführen. Benutzer werden in der Admin Console erstellt. Die Berechtigungen gelten für Benutzerprofile oder Benutzergruppen. Es gibt zwei Arten von Berechtigungen, die Sie gewähren können:

* Sie können Benutzergruppen bestimmen, denen Sie Berechtigungen einräumen, und dann die Benutzer einer oder mehreren Gruppen zuweisen. Diese Vorgehensweise ermöglicht eine gemeinsame Nutzung der Rechte und eine Vereinheitlichung der Benutzerprofile. Außerdem wird die Verwaltung und Pflege von Benutzeprofilen erleichtert.
* Sie können den Benutzern direkt spezifische Berechtigungen einräumen, um gegebenenfalls die über Gruppen eingeräumten Berechtigungen zu überschreiben.

## Wichtige Schritte zum Gewähren von Berechtigungen{#key-steps-permissions}

Als Produkt-Administrator können Sie den Benutzern Ihrer Organisation Berechtigungen erteilen. Berechtigungen werden über die Adobe Admin Console und die Client-Konsole in Campaign gewährt. Benutzer melden sich mit ihrer Adobe ID bei Adobe Campaign an. Erfahren Sie auf [dieser Seite](connect.md), wie Sie eine Verbindung zu Adobe Campaign herstellen können.

Die wichtigsten Schritte sind:

* **Schritt 1**: Definieren Sie Ihre Benutzergruppen und weisen Sie ihnen Berechtigungen in der Client-Konsole in Campaign zu. [Weitere Informationen](manage-permissions.md#create-product-profile).
Beachten Sie, dass Sie zu Beginn auch integrierte Benutzergruppen verwenden können. Diese Standardgruppen und ihre Berechtigungen werden in [diesem Abschnitt](manage-permissions.md#ootb-productprofiles) aufgeführt.
* **Schritt 2**: Erstellen Sie Produktprofile in der Adobe Admin Console, die mit diesen Gruppen übereinstimmen. [Weitere Informationen](manage-permissions.md#create-product-profile).
Sie können zu Beginn integrierte Produktprofile verwenden. [Weitere Informationen](manage-permissions.md#ootb-productprofiles).
* **Schritt 3**: Erstellen Sie Benutzende in der Adobe Admin Console und weisen Sie sie einem Produktprofil zu. [Weitere Informationen](manage-permissions.md#add-users).
* **Schritt 4** (optional): Weisen Sie Berechtigungen für Ordner zu. [Weitere Informationen](manage-permissions.md#ootb-productprofiles).

## Über die Admin Console{#gs-admin-console}

Die Adobe Admin Console ist ein zentraler Ort für die Verwaltung der Berechtigungen für Adobe-Berechtigungen in Ihrem Unternehmen. Sie steht nur Produktadministratoren zur Verfügung.

Verwenden Sie die Admin Console, um Benutzer hinzuzufügen und Produktprofile zu erstellen und zuzuweisen (d. h. Gruppen von Benutzerrollen).

Erfahren Sie auf [dieser Seite](manage-permissions.md#add-users), wie Sie Benutzer hinzufügen.

## Über Produktprofile{#ootb-product-profiles}

Produktprofile sind Gruppen von Produkten und Services, die Sie Benutzern zuweisen können. In Adobe Experience Cloud basieren die Berechtigungen auf dem Profil eines Produkts und nicht auf der Benutzerin bzw. dem Benutzer. Sie können jedoch Administratorrechte an bestimmte Benutzende delegieren.

In der Admin Console wird jedes **Produktprofil** von Adobe Experience Cloud für Campaign mit einer **Benutzergruppe** in der Client-Konsole von Campaign verknüpft.

Erfahren Sie auf [dieser Seite](manage-permissions.md#create-a-product-profile), wie Sie Produktprofile erstellen und zuweisen.

## Spezifische Berechtigungen für Campaign{#named-rights}

Als Mitglied eines Produktprofils (d. h. einer Benutzergruppe) hat ein Benutzer die Berechtigungen zum Ausführen von Vorgängen (die als „spezifische Berechtigungen“ bezeichnet werden) und hat Lese- und/oder Schreibzugriff auf Daten. Ein Benutzer kann Mitglied in mehreren Benutzergruppen sein: Rechte und Zugriffsberechtigungen sind additiv.

Weitere Informationen zu spezifischen Berechtigungen finden Sie in [diesem Abschnitt](manage-permissions.md#use-named-rights).
