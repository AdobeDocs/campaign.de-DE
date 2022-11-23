---
title: Erste Schritte mit Berechtigungen in Campaign v8
description: Erfahren Sie mehr über die Schritte zum Definieren von Berechtigungen in Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: b63dc1616bc7ce1387a7bd0590c289b59f11b33f
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 12%

---

# Erste Schritte mit Berechtigungen{#gs-permissions}

Mit Adobe Campaign können Sie die den Benutzern zugewiesenen Rechte definieren und verwalten. Dies sind verschiedene Rechte und Einschränkungen, die Folgendes zulassen oder verweigern:

* Zugriff auf bestimmte Funktionen
* Zugriff auf bestimmte Daten
* Zugriff auf bestimmte Aktionen (Erstellen, Ändern, Löschen)

Diese Berechtigungen werden durch die Kombination von Benutzergruppenberechtigungen, spezifischen Berechtigungen und Berechtigungen für Ordner definiert.

In Adobe Campaign sind Benutzer **Operatoren** und **Operatorgruppen** stehen für Benutzerrollen. Ein(e) Benutzende(r) hat in Adobe Campaign die Berechtigung, sich anzumelden und Aktionen durchzuführen. Benutzer werden in der Admin Console erstellt. Die Berechtigungen gelten für Benutzerprofile oder Benutzergruppen. Es gibt zwei Arten von Berechtigungen, die Sie gewähren können:

* Sie können Benutzergruppen definieren, denen Sie Berechtigungen zuweisen, und die Benutzer dann mit einer oder mehreren Gruppen verknüpfen. Auf diese Weise können Sie Berechtigungen wiederverwenden und die Konsistenz von Benutzerprofilen verbessern. Außerdem wird die Verwaltung und Pflege von Benutzerprofilen erleichtert.
* Sie können Benutzern direkt spezifische Berechtigungen zuweisen, in einigen Fällen, um über Gruppen zugewiesene Rechte zu überschreiben.

## Wichtige Schritte zum Gewähren von Berechtigungen{#key-steps-permissions}

Als Produkt-Administrator können Sie den Benutzern Ihrer Organisation Berechtigungen erteilen. Berechtigungen werden über die Adobe Admin Console- und Campaign-Clientkonsole gewährt. Benutzer melden sich mit ihrer Adobe ID bei Adobe Campaign an. Erfahren Sie, wie Sie in eine Verbindung mit Adobe Campaign herstellen. [diese Seite](connect.md).

Die wichtigsten Schritte sind:

* **Schritt 1**: Definieren Sie Ihre Benutzergruppen und weisen Sie ihnen Berechtigungen in der Campaign-Clientkonsole zu. [Weitere Informationen](manage-permissions.md#create-product-profile).
Beachten Sie, dass Sie auch integrierte Benutzergruppen verwenden können, um mit zu beginnen. Diese Standardgruppen und ihre Berechtigungen werden in [diesem Abschnitt](manage-permissions.md#ootb-productprofiles).
* **Schritt 2**: Erstellen Sie Produktprofile in der Admin Console, die mit diesen Gruppen übereinstimmen. [Weitere Informationen](manage-permissions.md#create-product-profile).
Sie können integrierte Produktprofile verwenden, um mit zu beginnen. [Weitere Informationen](manage-permissions.md#ootb-productprofiles).
* **Schritt 3**: Erstellen Sie Benutzer in der Admin Console und weisen Sie sie einem Produktprofil zu. [Weitere Informationen](manage-permissions.md#add-users).
* **Schritt 4** (optional): Weisen Sie Berechtigungen für Ordner zu. [Weitere Informationen](manage-permissions.md#ootb-productprofiles).

## Über die Admin Console{#gs-admin-console}

Die Adobe Admin Console ist ein zentraler Ort für die Verwaltung der Berechtigungen für Adoben in Ihrem Unternehmen. Sie steht nur Produktadministratoren zur Verfügung.

Verwenden Sie die Admin Console, um Benutzer hinzuzufügen, Produktprofile zu erstellen und zuzuweisen (d. h. Benutzergruppen).

Erfahren Sie, wie Sie Benutzer hinzufügen in [diese Seite](manage-permissions.md#add-users).

## Über Produktprofile{#ootb-product-profiles}

Produktprofile sind Gruppen von Produkten und Diensten, die Sie Benutzern zuweisen können. In Adobe Experience Cloud basieren die Berechtigungen auf dem Profil eines Produkts und nicht auf dem Benutzer. Sie können jedoch bestimmten Benutzern Administratorrechte zuweisen.

In der Admin Console wird jede Adobe Experience Cloud **Produktprofil** für Campaign mit einer **Benutzergruppe** in der Campaign-Clientkonsole.

Erfahren Sie, wie Sie in Produktprofile erstellen und zuweisen [diese Seite](manage-permissions.md#create-a-product-profile).

## Campaign - spezifische Berechtigungen{#named-rights}

Als Mitglied eines Produktprofils (d. h. Benutzergruppe) hat ein Benutzer die Berechtigung zum Ausführen von Vorgängen mit der Bezeichnung &quot;Spezifische Berechtigungen&quot;und hat Lese- und/oder Schreibzugriff auf Daten. Ein Operator kann Mitglied in mehreren Operatorgruppen sein: Rechte und Zugriffsberechtigungen sind additiv.

Weitere Informationen zu spezifischen Berechtigungen finden Sie unter [diesem Abschnitt](manage-permissions.md#use-named-rights).
