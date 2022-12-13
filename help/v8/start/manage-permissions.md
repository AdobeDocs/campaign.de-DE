---
title: Berechtigungen für Campaign v8 erteilen
description: Erfahren Sie, wie Sie Berechtigungen für Campaign v8 erteilen Benutzer
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 90154f84-b6a7-407c-93b7-9731dc94d9de
source-git-commit: b96ac3bd2365c548d071e626721d606dd33200b5
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Verwalten von Benutzerberechtigungen{#manage-permissions}

## Benutzer hinzufügen {#add-users}

Als Produktadministrator können Sie Benutzer hinzufügen und Zugriff auf Campaign gewähren.

Gehen Sie wie folgt vor, um einen Benutzer hinzuzufügen:

1. Wählen Sie auf der Startseite der [Admin Console](https://adminconsole.adobe.com/enterprise){target=&quot;_blank&quot;} die Option **Benutzer hinzufügen** aus.

   ![](assets/add-a-user.png)

1. Geben Sie die E-Mail-Adresse des Benutzers ein.
1. Verwenden Sie das Pluszeichen (+), um die Produktprofile oder Benutzergruppen auszuwählen, die dem Benutzer zugewiesen werden sollen.

   ![](assets/add-a-product-profile.png)

   Die in Campaign integrierten Produktprofile werden in [diesem Abschnitt](#ootb-productprofiles) aufgelistet.

   Erfahren Sie in [diesem Abschnitt](#user-groups), wie Sie Benutzergruppen erstellen können

1. Klicken Sie auf **Speichern**. Der Benutzer wird hinzugefügt und in der Benutzerliste angezeigt. Wenn Sie Benutzenden eine Administratorrolle oder ein Produktprofil zuweisen, erhalten diese eine E-Mail-Benachrichtigung. Benutzende müssen dem Link folgen, um ihr Profil auszufüllen.

Weitere Informationen zur Benutzererstellung finden Sie in der Admin Console auf [diese Seite](https://helpx.adobe.com/de/enterprise/using/manage-users-individually.html){target=&quot;_blank&quot;}.

Wenn sich neue Benutzende mit ihrer Adobe ID [bei Campaign anmelden](connect.md), werden sie der Liste der Campaign-Benutzenden in der Client-Konsole hinzugefügt. Campaign-Benutzende werden im Ordner **[!UICONTROL Administration > Zugriffsverwaltung > Benutzer]** des Campaign-Explorers gespeichert.

## Arbeiten mit externen Profilen{#product-profiles}

Verwenden Sie Produktprofile, um Benutzer mit den Fähigkeiten auszustatten, die das Produkt beinhaltet.

* Für jedes Produkt in der Admin Console können Sie ein oder mehrere Produktprofile erstellen.
* In jedem Produktprofil weisen Sie Benutzende und Benutzergruppen (in Ihrer Organisation) zu.
* Wenn sich ein Benutzer mit seinen im Produktprofil angegebenen Anmeldeinformationen anmeldet, erhält er Zugriff auf die Apps und Services des Produkts, auf dem das Produktprofil basiert.

Diese Produktprofile stimmen mit den Benutzergruppen überein, die im Ordner **[!UICONTROL Administration > Zugriffsverwaltung > Benutzergruppen]** des Campaign-Explorers gespeichert sind.

In der Admin Console verwenden Produktprofile die folgende Syntax:

Kampagne – `<your instance>` – interner Name der Benutzergruppe

Beispielsweise lautet für die Gruppe der **Versandverantwortlichen** in der Testinstanz das Produktprofil in der Admin Console:

Kampagne – Test – Versand

Sie können Standardproduktprofile verwenden oder neue erstellen.

### Erstellen eines Produktprofils{#create-product-profile}

Um ein neues Produktprofil zu Adobe hinzuzufügen, müssen Sie es zunächst in der Client-Konsole von Campaign erstellen und dann der Admin Console hinzufügen.

Gehen Sie wie folgt vor, um beispielsweise ein Produktprofil „Validierungsverantwortliche“ zu erstellen.

#### Erstellen der Benutzergruppe in Campaign{#create-op-group}

1. Stellen Sie eine Verbindung zu Campaign her, öffnen Sie den Explorer und navigieren Sie zu **[!UICONTROL Administration > Zugriffsverwaltung > Benutzergruppen]**.
1. Klicken Sie auf **[!UICONTROL Neu]** und legen Sie den Namen der Benutzergruppe sowie deren internen Namen („Validierungsverantwortliche“) fest.
   ![](assets/new-op-group.png)
1. Definieren Sie die zugehörigen Berechtigungen durch Auswahl von spezifischen Berechtigungen. Die spezifischen Berechtigungen werden in [diesem Abschnitt](#use-named-rights) beschrieben
1. Speichern Sie die neue Benutzergruppe.

#### Erstellen des Produktprofils in der Admin Console{#create-profile-in-admin-console}

1. Stellen Sie eine Verbindung zur [Admin Console](https://adminconsole.adobe.com/enterprise){target=&quot;_blank&quot;} her.
1. Öffnen Sie vom Abschnitt **Produkt und Dienstleistungen** auf der Startseite aus das Campaign-Produkt.
1. Klicken Sie auf **Neues Profil** und geben Sie den Namen des zu erstellenden Produktprofils mit der exakt korrekten Syntax wie [hier](#product-profiles) beschrieben ein. In unserem Beispiel geben wir Folgendes ein: Kampagne – `<your-instance-name>` – Validierungsverantwortliche

   ![](assets/new-product-profile-ui.png)

1. Speichern Sie Ihre Änderungen.

Sie können jetzt Benutzende zu diesem neuen Produktprofil hinzufügen, wie in [diesem Abschnitt](#add-users) beschrieben.

Es empfiehlt sich, Benutzergruppen Produktprofile zuzuweisen. Die Verwaltung von Berechtigungen pro Benutzer ist kein nachhaltiges Modell.


### Standardproduktprofile und Benutzergruppen {#ootb-productprofiles}

Adobe Campaign verfügt über integrierte **Produktprofile** die definiert werden, wenn Adobe Ihre Umgebung aktiviert.

![](assets/ootb-product-profiles.png)

Diese Produktprofile stimmen mit den **Benutzergruppen** von Campaign überein. Standardbenutzergruppen und ihre [spezifische Berechtigungen](#use-named-rights) werden im Folgenden aufgeführt:

1. **[!UICONTROL Administrator]** (Admin)

   Die Benutzenden in dieser Gruppe haben vollen Zugriff auf die Instanz. Admins sind Benutzer, die Zugriff auf die meisten technischen Elemente der Benutzeroberfläche haben.

   Die Gruppe beinhaltet die folgende spezifische Berechtigung:

   * **[!UICONTROL ADMINISTRATION]**: Berechtigt zum Ausführen, Erstellen, Bearbeiten und Löschen von Objekten wie Workflows, Sendungen, Skripten usw.

1. **[!UICONTROL Versandverantwortliche Benutzer]** (Versand)

   Die Benutzer dieser Gruppe sind für die Versandverwaltung verantwortlich. Die Gruppe verleiht Zugriff auf die für die Erstellung und Vorbereitung von Sendungen notwendigen Hauptressourcen (Kampagnentypologien, Versandmappings, Standardvorlagen, Gestaltungsbausteine etc.).

   Die Gruppe beinhaltet folgende spezifische Berechtigungen:

   * **[!UICONTROL SENDUNGEN VORBEREITEN]**: Berechtigt zum Erstellen, Bearbeiten und Starten der Versandanalyse;
   * **[!UICONTROL SENDUNGEN STARTEN]**: Berechtigt zur Validierung von zuvor analysierten Sendungen.

1. **[!UICONTROL Kampagnenverantwortliche Benutzer]** (operation)

   Die Benutzer dieser Gruppe können Marketing-Kampagnen verwalten. Diese Berechtigung verleiht Zugriff auf mit Kampagnen verbundene Elemente (Pläne, Programme, Workflows, Budgets etc.) im Rahmen von **[!UICONTROL Campaign]** (optionales Adobe Campaign-Modul).

   Die Gruppe beinhaltet folgende spezifische Berechtigungen:

   * **[!UICONTROL EINFÜGEN VON ORDNERN]**: Berechtigt zum Einfügen von Ordnern in den Adobe Campaign-Navigationsbaum (erfordert Schreibzugriff für betroffene Zweige);
   * **[!UICONTROL WORKFLOW]**: Berechtigt zur Nutzung von Workflows.

   >[!NOTE]
   >
   >Benutzer dieser Gruppe können keine Sendungen starten.

1. **[!UICONTROL Autoren]** (content)

   Benutzer dieser Gruppe können auf die Inhaltsordner im Kontext des Add-ons **[!UICONTROL Content-Management]** zugreifen. Diese Gruppe erteilt keine zusätzlichen Berechtigungen.

1. **[!UICONTROL Berichtzugriff]** (Bericht)

   Diese Gruppe ermöglicht es externen Benutzenden, über einen [Web-Zugriff](../start/campaign-ui.md#web-browser) Versandberichte einzusehen.

1. **[!UICONTROL Workflow-Ausführung]** (Workflow)

   Die Gruppe **[!UICONTROL Workflow-Ausführung]** dient der Ausführungs- und Validierungskontrolle von Zielgruppen-Workflows. Die Benutzer dieser Gruppe verfügen automatisch über die spezifische Berechtigung WORKFLOW. Diese ist neben den Datenzugriffsrechten Voraussetzung für alle Workflow-bezogenen Aktionen. Die Gruppe **[!UICONTROL Workflow-Ausführung]** verfügt standardmäßig über Lesezugriff auf die Standard-Ordner der Zielgruppen-Workflows und der Workflow-Vorlagen. Die Benutzer dieser Gruppe haben des Weiteren Lese- und Schreibzugriff auf den Ordner der ausstehenden Validierungen.

1. **[!UICONTROL Workflow-Verwantwortliche]** (workflowSupervisor)

   Benutzer dieser Gruppe verwalten Workflow-Genehmigungen und erhalten im Falle von Warnungen bezüglich Kampagnen-Workflows eine E-Mail-Benachrichtigung.

1. **Lokale/Zentrale Verwaltung** (zentral/lokal)

   Benutzende dieser Gruppe können das Add-on **[!UICONTROL Verteiltes Marketing]** verwenden.

1. **[!UICONTROL Angebotsverantwortliche Benutzer]** (offer)

   Die Benutzer dieser Gruppe können Angebote mithilfe des Add-ons Interaktion erstellen und verwalten. [Weitere Informationen](../interaction/interaction-operators.md).

   Die Gruppe beinhaltet folgende spezifische Berechtigungen:

   * **[!UICONTROL EINFÜGEN VON ORDNERN]**: Berechtigt zum Einfügen von Ordnern in den Adobe Campaign-Navigationsbaum (erfordert Schreibzugriff für betroffene Zweige);
   * **[!UICONTROL BEARBEITUNG VON ORDNERN]**: Berechtigt zum Ändern von Ordnereigenschaften wie interner Name, Titel, verknüpftes Bild, Reihenfolge der Unterordner usw.

   Angebotsverantwortliche Benutzer können mit den ihnen zugewiesenen Rechten die folgenden Aufgaben ausführen:

   * Änderung von **[!UICONTROL Design-Umgebungen]**;
   * Ansicht von **[!UICONTROL Live-Umgebungen]**;
   * Konfiguration von administrativen Funktionen (vordefinierte Platzierungen und Filter);
   * Kategorien erstellen und aktualisieren.
   * Erstellung und Änderung von Angeboten;
   * Konfiguration von Angebotseignungen;
   * Validierung von Angeboten.

   >[!NOTE]
   >
   >**Angebotsverantwortliche Benutzer** können ein Angebot nur genehmigen, wenn kein Validierungsverantwortlicher angegeben ist oder wenn sie in der Angebotsvorlage als Validierungsverantwortliche deklariert wurden.

   Die Berechtigungsmatrix des angebotsverantwortlichen Benutzers ist verfügbar auf [dieser Seite](../interaction/interaction-operators.md#recap-of-rights-according-to-operator).

## Arbeiten mit Benutzergruppen{#user-groups}

Sie können die Admin Console verwenden, um Benutzergruppen zu erstellen und ihnen Benutzende zuzuweisen.

Eine Benutzergruppe ist eine Sammlung verschiedener Benutzender, denen ein gemeinsamer Berechtigungssatz erteilt werden muss. Erfahren Sie in [diesem Abschnitt](https://helpx.adobe.com/de/enterprise/using/user-groups.html){target=&quot;_blank&quot;}, wie Sie Benutzergruppen erstellen.

Sie können Produktprofile an Benutzergruppen zuweisen. Alle Benutzenden in dieser Gruppe erhalten also denselben Satz von Produktberechtigungen.

## Spezifische Berechtigungen{#use-named-rights}

Adobe Campaign verfügt über eine Reihe von spezifischen Berechtigungen, mit denen Sie die den Benutzenden und den Benutzergruppen zugewiesenen Berechtigungen definieren können. Diese Berechtigungen können über den Ordner **[!UICONTROL Administration > Zugriffsverwaltung > Spezifische Berechtigungen]** des Campaign-Explorers bearbeitet werden.

Spezifische Berechtigungen gewähren Berechtigungen für:

* Vorgänge ausführen
Zum Beispiel ist die Schaltfläche **Analysieren** im Versand-Editor für Mitglieder der Gruppe **Versandoperatoren** aktiviert, die die spezifische Berechtigung **Versand vorbereiten** besitzen.

* Zugriff auf Ordner
Mitglieder von Operatorgruppen können Zugriffsrechte auf Ordner gewähren oder einschränken, indem sie die Sicherheitseinstellungen von Ordnern ändern. [Weitere Informationen](folder-permissions.md#restrict-access-to-a-folder).

   Zum Beispiel kann es diese Auswirkungen haben: **Schreibzugriff** zum Erstellen neuer Entitäten (wie Sendungen, Profile usw.), **Lesezugriff** zum Verwenden von Entitäten, **Löschzugriff** zum Löschen von Entitäten.

Standardmäßige spezifische Berechtigungen in Adobe Campaign sind:

* **[!UICONTROL ADMINISTRATION]**: Benutzer mit **[!UICONTROL ADMINISTRATORRECHTEN]** haben vollen Zugriff auf die Instanz. Administratoren können Objekte wie Workflows, Sendungen, Skripte usw. ausführen, erstellen, bearbeiten und löschen.

* **[!UICONTROL VALIDIERUNGSADMINISTRATION]**: Sie können verschiedene Validierungsschritte innerhalb von Workflows und Sendungen festlegen, um sicherzustellen, dass der aktuelle Status durch einen zugewiesenen Benutzer oder eine zugewiesene Gruppe validiert wurde. Benutzer mit der Berechtigung **[!UICONTROL VALIDIERUNGSADMINISTRATION]** können Validierungsschritte festlegen und auch einen Benutzer oder eine Benutzergruppe zuweisen, der bzw. die diese Schritte validieren soll.

* **[!UICONTROL ZENTRAL]**: Berechtigt zur zentralen Verwaltung (Dezentrales Marketing).

* **[!UICONTROL LÖSCHEN VON ORDNERN]**: Berechtigt zum Löschen von Ordnern. Mit dieser Berechtigung können Benutzer Ordner aus der Explorer-Ansicht löschen.

* **[!UICONTROL BEARBEITUNG VON ORDNERN]**: Berechtigt zum Ändern von Ordnereigenschaften wie interner Name, Titel, verknüpftes Bild, Reihenfolge der Unterordner usw.

* **[!UICONTROL EXPORTIEREN]**: Mit der Workflow-Aktivität **[!UICONTROL EXPORTIEREN]** können Benutzer Daten aus ihren Adobe Campaign-Instanzen in eine Datei auf einem Server oder lokalen Computer exportieren.

* **[!UICONTROL ZUGRIFF AUF DATEIEN]**: Berechtigung für Lese- und Schreibzugriff auf Dateien über ein Skript, das in die **[!UICONTROL JavaScript]**-Workflow-Aktivität geschrieben werden kann, um Dateien auf einem Server zu lesen und zu schreiben.

* **[!UICONTROL ALLGEMEINER IMPORT]**: Berechtigt zum allgemeinen Import von Daten. Mit **[!UICONTROL ALLGEMEINER IMPORT]** können Sie Daten in eine andere Tabelle importieren, während die Berechtigung **[!UICONTROL BERECHTIGT ZUM IMPORT VON EMPFÄNGERN]** nur den Import in die Empfängertabelle erlaubt.

* **[!UICONTROL EINFÜGEN VON ORDNERN]**: Berechtigt zum Einfügen von Ordnern. Benutzer mit der Berechtigung **[!UICONTROL EINFÜGEN VON ORDNERN]** können in der Ordnerstruktur der Explorer-Ansicht neue Ordner erstellen.

* **[!UICONTROL LOKAL]**: Berechtigt zur lokalen Verwaltung (Dezentrales Marketing).

* **[!UICONTROL FUSION]**: Berechtigt zum Verbinden der ausgewählten Datensätze zu einem Datensatz. Wenn Empfänger als Duplikate vorhanden sind, kann der Benutzer mit der Berechtigung **[!UICONTROL FUSION]** die Duplikate auswählen und zu einem primären Empfänger vereinen.

* **[!UICONTROL SENDUNGEN VORBEREITEN]**: Berechtigung zum Erstellen, Bearbeiten und Speichern einer Sendung. Benutzer mit der Berechtigung **[!UICONTROL SENDUNGEN VORBEREITEN]** können auch den Prozess der Versandanalyse starten.

* **[!UICONTROL DATENSCHUTZRECHT]**: Berechtigt dazu, Datenschutzdaten zu sammeln und zu löschen. [Weitere Informationen](privacy.md).

* **[!UICONTROL AUSFÜHRUNG VON PROGRAMMEN]**: Berechtigt dazu, Befehle in verschiedenen Programmiersprachen auszuführen.

* **[!UICONTROL IMPORT VON EMPFÄNGERN]**: Berechtigt zum Import von Empfängern. Benutzer mit der Berechtigung **[!UICONTROL IMPORT VON EMPFÄNGERN]** können eine lokale Datei in eine Empfängertabelle importieren.

* **[!UICONTROL AUSFÜHRUNG VON SQL-SCRIPTS]**: Berechtigt zur Ausführung von SQL-Befehlen direkt in der Datenbank.

* **[!UICONTROL SENDUNGEN STARTEN]**: Berechtigt zur Validierung von zuvor analysierten Sendungen. Nach der Versandanalyse wird der Versand bei verschiedenen Validierungsschritten angehalten und muss validiert werden, damit er wieder aufgenommen werden kann. Benutzer mit der Berechtigung **[!UICONTROL SENDUNGEN STARTEN]** können Sendungen validieren.

* **[!UICONTROL SQL-DATEN-MANAGEMENT-AKTIVITÄT VERWENDEN]**: Berechtigt zum Schreiben Ihrer eigenen SQL-Scripts unter Verwendung der SQL-Daten-Management-Aktivität, um Arbeitstabellen zu erstellen und zu füllen. [Weitere Informationen](../../automation/workflow/sql-data-management.md).

* **[!UICONTROL WORKFLOW]**: Diese spezifische Berechtigung gilt für Workflows: Damit können Sie Workflows erstellen, starten und stoppen. Leserechte für die Workflow-Datei sind erforderlich, damit die spezifische Berechtigung angewendet werden kann. Bei Zielgruppen-Workflows ist die Leseberechtigung für den Ordner **[!UICONTROL Profile und Zielgruppen]** erforderlich.


* **[!UICONTROL WEBAPP]**: Berechtigt zur Nutzung von Web-Anwendungen.

>[!NOTE]
>
>Diese Liste kann je nach den Add-ons, die in Ihrer Umgebung installiert sind, unterschiedlich aussehen.



## Zusätzliche Ressourcen{#additional-res}

* [Berechtigungen für Workflows verwalten](../../automation/workflow/managing-rights.md)
* [Berechtigungen für verteiltes Marketing verwalten](../../automation/distributed-marketing/about-distributed-marketing.md#operators)
* [Berechtigungen für das Interaktionsmodul verwalten](../interaction/interaction-operators.md)
* [Filterzugriff auf Schemata](../dev/filter-schema.md)
* [Einschränken der Anzeige von personenbezogenen Daten](../dev/restrict-pi-view.md)
