---
title: Frühzeitige Versionshinweise zu Campain v8
description: Frühzeitige Veröffentlichung von Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 958d2e8acdb9edee74f55bc3ea808f5072bf8f4d
workflow-type: ht
source-wordcount: '586'
ht-degree: 100%

---

# Frühzeitige Versionshinweise {#e-new-release}

Auf dieser Seite werden Verbesserungen und Fehlerbehebungen beschrieben, die in der nächsten Version von Campaign v8 enthalten sein werden. Dieser Inhalt kann ohne vorherige Ankündigung bis zum Veröffentlichungsdatum geändert werden. Die offiziellen Versionshinweise finden Sie auf dieser [Seite](../start/release-notes.md).

## Version 8.5.1 {#release-8-5}

_30. Juni 2023_

**Neue Funktionen**

<table> 
<thead>
<tr> 
<th> <strong>Verbesserter Push-Benachrichtigungsdienst</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Campaign 8.5.1 führt die neue v8 unseres Push-Benachrichtigungsdienstes ein. Dieser basiert auf einem robusten Framework, das auf moderner Spitzentechnologie aufbaut. Dieser Dienst wurde entwickelt, um neue Ebenen der Skalierbarkeit zu erschließen und sicherzustellen, dass Ihre Benachrichtigungen eine größere Zielgruppe mit nahtloser Effizienz erreichen können. Mit unserer verbesserten Infrastruktur und optimierten Prozessen können Sie höhere Skalierbarkeit und Zuverlässigkeit erwarten, die es Ihnen ermöglicht, mit Ihren App-Nutzenden wie nie zuvor in Kontakt zu treten und Verbindungen herzustellen. Diese Funktion steht nur einer ausgewählten Kundengruppe zur Verfügung (eingeschränkte Verfügbarkeit).</p>
</td> 
</tr> 
</tbody> 
</table>

**Aktualisierungen zur Kompatibilität**

* Die 32-Bit-Version der Client-Konsole wird jetzt nicht mehr unterstützt. Ab 8.6. ist die Client-Konsole nur noch in 64 Bit verfügbar. Das Upgrade auf die 64-Bit-Version der Client-Konsole ist nahtlos. Weitere Informationen zum Upgrade Ihres Betriebssystems finden Sie in dieser [Technote](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=de).
* Sie können nun Ihre Campaign v8-Instanz mit Ihrer externen Azure Synapse-Datenbank verbinden. Diese Verbindung wird über ein neues externes Konto verwaltet.

**Verbesserungen**

* Der SMS-Durchsatz wurde durch die Implementierung einer Reihe von Optimierungen erheblich verbessert, was zu mehr Geschwindigkeit und Effizienz bei der SMS-Kommunikation führt.
* Ab Campaign v8.5.1 wurde der Authentifizierungsprozess für Campaign v8 verbessert. Technische Benutzerinnen bzw. Benutzer müssen Adobe Identity Management System (IMS) verwenden, um eine Verbindung mit Campaign herzustellen.
* Sie können jetzt Ziel- und Quellverbindungen nutzen, um Profilattribute wie Opt-out-Daten zwischen der Adobe Experience Platform- und der Campaign v8-Datenbank zu synchronisieren
* Die Versandvorbereitung wurde optimiert.
* Neben der vorhandenen Authentifizierungsmethode für Benutzername/Kennwort wurde für das externe SFTP-Konto eine neue schlüsselbasierte Authentifizierungsoption hinzugefügt. Benutzerinnen und Benutzer können sich jetzt sicher mit einem privaten Schlüssel authentifizieren, was die Sicherheit verbessert und einen alternativen Authentifizierungsmechanismus für den SFTP-Zugriff bietet.

**Verbesserungen bei der Sicherheit**

* Sie können keine Benutzenden mehr über die Client-Konsole erstellen. Sie müssen jetzt die Admin Console verwenden. [Weitere Informationen](../start/gs-permissions.md).
* Mehrere Drittanbieter-Tools wurden aktualisiert, um die Sicherheit zu optimieren.

**Patches**

* Fehlerkorrektur: Sonderzeichen im HTML-Inhalt eines Versands werden jetzt in mehreren Browsern korrekt codiert. (NEO-60081)
* Fehlerkorrektur: Berichte können jetzt in einer Campaign v8 Enterprise (FFDA)-Bereitstellung gespeichert werden. (NEO-56836)
* Fehlerkorrektur: Beim Einfügen oder Aktualisieren von Daten in ein benutzerdefiniertes FFDA-Schema über die Workflow-Aktivität „Daten-Update“ tritt jetzt kein Fehler mehr auf. (NEO-54708)
* Fehlerkorrektur: Der Datenbankbereinigungs-Workflow kann jetzt Adressen aus der Tabelle „nms:address“ in FFDA entfernen. (NEO-54460)
* Fehlerkorrektur: Der Abrechnungs-Workflow funktioniert jetzt mit dem Fehler „Kompilierungsspeicher ausgeschöpft“. (NEO-51137)
* Fehlerkorrektur: Die GPG-Entschlüsselung funktioniert jetzt in der Workflow-Aktivität „Laden (Datei)“ ordnungsgemäß. (NEO-50257)
* Fehlerkorrektur: Die Funktion `JSPContext.sqlExecWithOneParam` funktioniert jetzt. (NEO-50066)
* Fehlerkorrektur: Es treten keine Versandfehler mehr auf, wenn nicht druckbare Zeichen in Personalisierungsfeldern verwendet werden. (NEO-48588)
* Fehlerkorrektur: Beim Einfügen dynamischer Adobe Target-Bilder treten jetzt keine Versandfehler mehr auf. (NEO-62689)
* Fehlerkorrektur: Browser können jetzt zusätzliche Leerzeichen hinzufügen, wenn bedingte Inhalte in einem Versand verwendet werden. (NEO-62132)
* Fehlerkorrektur: Es wird kein Pop-up-Fenster mehr geöffnet, wenn auf ein Bild im E-Mail-Inhaltseditor geklickt wird. (NEO-60752)
* Fehlerkorrektur: Es tritt kein Fehler mehr auf, der das Scrollen beim Bearbeiten des Inhalts eines Versands verhinderte. (NEO-61364)
