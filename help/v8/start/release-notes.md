---
title: Versionshinweise zu Campaign v8
description: Neueste Version von Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: f72cd296e49a22b2ee8878084c7d9f252b98d29e
workflow-type: tm+mt
source-wordcount: '1455'
ht-degree: 90%

---

# Aktuelle Version{#latest-release}

Adobe Campaign wird regelmäßig aktualisiert. Dieser regelmäßige Aktualisierungsrhythmus zielt darauf ab, Ihnen die neuesten und besten Funktionen bereitzustellen, Ihre Umgebung sicher zu halten und Ihr Produkterlebnis zu verbessern. Adobe empfiehlt allen Kundinnen und Kunden dringend, ein Upgrade auf die neueste Version durchzuführen.

Wenn Sie Managed Cloud Services nutzen, wird Ihre Instanz von Adobe mit jeder neuen Version aktualisiert. Adobe wird Sie kontaktieren und Ihre Umgebungen aktualisieren. Die Campaign-Client-Konsole **muss auf dieselbe Version aktualisiert werden** wie die Campaign-Server. Auf dieser [Seite](../start/connect.md#upgrade-ac-console) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.

Außerdem sollten Sie als Kunde bzw. Kundin sicherstellen, dass Sie die neuesten unterstützten Versionen der in der [Kompatibilitätsmatrix](compatibility-matrix.md) aufgeführten Systeme verwenden. 

## Version 8.5.1 {#release-8-5}

_30. Juni 2023_


**Verbesserter Push-Benachrichtigungsdienst**

Campaign v8.5.1 führt unseren neuesten Push-Benachrichtigungsdienst ein. Dieser wird durch ein robustes Framework gestützt, das auf moderner Spitzentechnologie aufbaut. Dieser Dienst wurde entwickelt, um neue Ebenen der Skalierbarkeit zu erschließen und sicherzustellen, dass Ihre Benachrichtigungen eine größere Zielgruppe mit nahtloser Effizienz erreichen können. Mit unserer verbesserten Infrastruktur und optimierten Prozessen können Sie höhere Skalierbarkeit und Zuverlässigkeit erwarten, die es Ihnen ermöglicht, mit Ihren App-Nutzenden wie nie zuvor in Kontakt zu treten und Verbindungen herzustellen. Diese Funktion steht nur einer ausgewählten Kundengruppe zur Verfügung (eingeschränkte Verfügbarkeit).

Weitere Informationen finden Sie in der [entsprechenden Dokumentation](../send/push-data-collection.md).


**Verbesserter Durchsatz für mobile Kanäle**

<!--
The newly introduced Push notification service showcases significant improvements in throughput for both Push Android and Push iOS compared to our previous version (v8.4). Users will experience notably enhanced performance with the upgraded service in the latest version (v8.5).

* Push Notifications (Android): up to **5x** faster
* Push Notifications (iOS): up to **2.2x** faster

SMS throughput has undergone substantial enhancements through a series of optimizations, resulting in notable improvements in speed and efficiency for SMS communication. These upgrades have led to increased throughput from the previous version (v8.4) to the latest version (v8.5), encompassing both sending and feedback updates. Users can now experience the benefits of this enhanced SMS service.</p>

* SMS throughput: up to **5x** faster

These max throughput performances have been measured by Adobe testing teams, in lab conditions.
-->

<table style="table-layout:fixed" text-align="bottom"><tr style="border: 0;">
<td>
<img alt="Durchsatzverbesserungen" src="../start/assets/do-not-localize/improvements.jpeg">
<p>
</td>
<td>
<div>

<p>Der neu eingeführte Push-Benachrichtigungsdienst zeigt erhebliche Verbesserungen des Durchsatzes für Push-Android und Push-iOS im Vergleich zur vorherigen Version (v8.4). Die Leistung des aktualisierten Dienstes in der neuesten Version (v8.5) wurde den Benutzern deutlich verbessert. </p>
<ul>
<li>Push-Benachrichtigungen (Android): bis <strong>5x</strong> schneller </li>
<li>Push-Benachrichtigungen (iOS): bis <strong>2.2x</strong> schneller</li>
</ul>
<p>Der SMS-Durchsatz wurde durch eine Reihe von Optimierungen erheblich verbessert, was zu erheblichen Verbesserungen bei der Geschwindigkeit und Effizienz der SMS-Kommunikation führte. Diese Upgrades haben zu einem höheren Durchsatz von der vorherigen Version (v8.4) auf die neueste Version (v8.5) geführt, der sowohl Senden- als auch Feedback-Aktualisierungen umfasst. Benutzer können jetzt die Vorteile dieses erweiterten SMS-Dienstes nutzen.</p>
<ul>
<li>SMS-Durchsatz: bis <strong>5x</strong> schneller</li>
</ul>
<p><em>Diese maximale Durchsatzleistung wurde von Adobe-Testteams unter Laborbedingungen gemessen.</em></p>
</div>
<p></p>
</td>
</tr></table>


**Allgemeine Verbesserungen**

* Sie können jetzt die Adobe Experience Platform-Zielverbindung nutzen, um Profilattribute wie Opt-out-Daten zwischen der Adobe Experience Platform- und der Campaign v8-Datenbank zu synchronisieren.
* Die Versandvorbereitung wurde für alle Kanäle optimiert.
* Neben der vorhandenen Authentifizierungsmethode für Benutzername/Kennwort wurde für das externe SFTP-Konto eine neue schlüsselbasierte Authentifizierungsoption hinzugefügt. Benutzerinnen und Benutzer können sich jetzt sicher mit einem privaten Schlüssel authentifizieren, was die Sicherheit verbessert und einen alternativen Authentifizierungsmechanismus für den SFTP-Zugriff bietet. Weiterführende Informationen finden Sie in [diesem Abschnitt](../config/external-accounts.md).

**Verbesserungen bei der Sicherheit**

* Ab Campaign v8.5.1 wurde der Authentifizierungsprozess für Campaign v8 verbessert. Technische Benutzerinnen bzw. Benutzer müssen Adobe Identity Management System (IMS) verwenden, um eine Verbindung mit Campaign herzustellen. Erfahren Sie in [dieser Technote](../../technotes/upgrades/ims-migration.md), wie Sie Ihre vorhandenen technischen Konten migrieren können.
* Sie können Benutzerinnen und Benutzer nicht mehr über die Campaign-Client-Konsole erstellen. Die Benutzeroberfläche wurde entsprechend aktualisiert. Sie müssen jetzt die Adobe Admin Console verwenden. [Weitere Informationen](../start/gs-permissions.md).
* Mehrere Drittanbieter-Tools wurden aktualisiert, um die Sicherheit zu optimieren.

**Aktualisierungen zur Kompatibilität**

* Die 32-Bit-Version der Client-Konsole wird jetzt nicht mehr unterstützt. Ab 8.6. ist die Client-Konsole nur noch in 64 Bit verfügbar. Das Upgrade auf die 64-Bit-Version der Client-Konsole ist nahtlos. Weitere Informationen zum Upgrade Ihres Betriebssystems finden Sie in dieser [Technote](../../technotes/upgrades/console.md).
* Sie können nun Ihre Campaign v8-Instanz mit Ihrer externen Azure Synapse-Datenbank verbinden. Diese Verbindung wird über ein neues externes Konto verwaltet. Weiterführende Informationen finden Sie in der [Campaign-Kompatibilitätsmatrix](../start/compatibility-matrix.md#federated-data-access-fdafederateddataaccessfda).


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
* Der Adobe Analytics-Connector exportiert die Metriken jetzt mit dem richtigen Kanaltyp. Zuvor war er immer als „E-Mail“-Kanal eingestellt. (NEO-26340)
* Fehlerkorrektur – Bei der Verwendung des Big Query-Connectors mit Datum-/Uhrzeit-Feldern treten jetzt keine Fehler mehr auf. (NEO-49768)


## Version 8.4.5 {#release-8-4-5}

_3. April 2023_

**Patches**

* Fehlerkorrektur – Wenn mehrere Genehmigungs-Workflows auf denselben Zeitplan eingestellt sind, gibt es keine Einschränkung aufgrund von doppelten Schlüsseln mehr. (NEO-48968)
* Fehlerkorrektur – Das Stilattribut des Body-Tags wird jetzt beim Hochladen eines Bildes im Digital Content Editor (DCE) nicht mehr geändert, nachdem der durch NEO-54474 (8.4.4) eingeführte Regressionsfehler behoben wurde. (NEO-57697)
* Fehlerkorrektur – Beim Exportieren von Daten über einen CRM-Connector tritt jetzt kein Fehler mehr auf, wenn der Primärschlüssel der temporären Tabelle als „long“ anstelle von „uuid“ definiert ist. (NEO-54153)
* Fehlerkorrektur – Es kommt jetzt nicht mehr zu Fehlern bei Paket-Export, FDA über HTTP und Reporting, nachdem der in 8.4.1 eingeführte Regressionsfehler behoben wurde. (NEO-57731)
* Fehlerkorrektur – Der Versandstatus für Sendungen mit negativen IDs wird jetzt korrekt aktualisiert, nachdem der in Version 8.3.8 eingeführte Regressionsfehler behoben wurde. (NEO-54675)
* Fehlerkorrektur – Beim Importieren von Daten mit dem Big Query Connector tritt jetzt kein Problem mehr mit booleschen Feldern auf (NEO-49181).


## Version 8.4.4 {#release-8-4-4}

_8. März 2023_

**Sicherheitsverbesserung**

* Um die Sicherheit zu verbessern, wurde Tomcat von Version 8.5.81 auf 8.5.85 aktualisiert. (NEO-50530)

**Patches**

* Das Scrollen in der Registerkarte **Bearbeiten** des Digital Content Editor (DCE) ist jetzt problemlos möglich. (NEO-54474)
* Bei der Replikation stürzt der Webserver jetzt nicht mehr ab. (NEO-53670)


## Version 8.4.3 {#release-8-4-3}


_27. Januar 2023_

**Verbesserungen**

* Fehlerkorrektur: Es wurde ein Synchronisierungsproblem von Versandindikatoren zwischen dem Marketing-Server und dem Mid-Sourcing-Server behoben. (NEO-50724) <!--OKKKK-->
* Fehlerkorrektur: Es wurde ein Problem behoben, das beim Export eines Workflows zu einem Fehler führen konnte. (NEO-50555) <!--OKKKK-->
* Fehlerkorrektur: Es wurde ein Problem beim Erweitern eines zuvor erweiterten Schemas behoben. (NEO-49118) <!--OKKKK-->
* Fehlerkorrektur: Es wurde ein Problem bei der Verwendung von zwei Anreicherungsaktivitäten mit derselben Kennung in der Link-Definition behoben. (NEO-48851)
* Fehlerkorrektur: Es wurden zwei Fehler bei der Versandvorbereitung behoben. Die Versandvorbereitung konnte fehlschlagen, wenn die Anzahl der bearbeiteten potenziellen Angebote zu hoch war. Das zweite Problem trat auf, wenn die Bild-URLs als URLs definiert waren, die in einem Versand im Textformat nachverfolgt werden sollten. (NEO-48807) <!--OKKKK-->
* Fehlerkorrektur: Es wurde ein Problem behoben, das zu Workflow-Fehlern führen konnte, wodurch der im externen Konto definierte Warehouse-Name für Nicht-FFDA-Konten von einem Workflow überschrieben werden konnte. (NEO-43209) <!--OKKKK-->
* Fehlerkorrektur: Verbesserte Sicherheit für Webanwendungen, um DDoS-Angriffe zu verhindern. (NEO-50757) <!--OKKKK-->
* Fehlerkorrektur: Die Verwaltung konsolidierter Tracking-Daten wurde in der FFDA-Tabelle für **[!UICONTROL konsolidiertes Tracking]** (nms:trackingStats) verbessert, um Duplikate zu vermeiden. (NEO-46409)
* Fehlerkorrektur: Ein Problem mit dem logischen Operator in Workflow-Abfragen bei der Verwendung von `enableIf` in einer logischen Operator-Bedingung wurde behoben. Die vorherige logische Bedingung wurde überschrieben. (NEO-45815)  <!--OKKKK-->
* Fehlerkorrektur: Die Erstellung aktiver Profile wurde im Abrechnungs-Workflow optimiert, um die Leistung zu verbessern. (NEO-47658) <!--OKKKK-->
* Fehlerkorrektur: Beim HTML-Dateiimport tritt jetzt kein Fehler mehr auf, wenn Bildknoten (img) URLs mit Personalisierungsfeldern enthalten. (NEO-48396)
* Fehlerkorrektur: Es wurde ein Problem bei der Verwendung des Sortierparameters in der Workflow-Aktivität **Aufspaltung** bei Snowflake (alle Bereitstellungen) behoben. (NEO-45899) <!--OKKKK-->
* Fehlerkorrektur: Jetzt tritt kein Fehler mehr auf, wenn ein Benutzer bzw. eine Benutzerin mit Lesezugriffsrechten für den Ordner &quot;nmsDeliveryMapping&quot; versucht, eine Kampagne oder einen Workflow auszuführen. (NEO-48230)
* Fehlerkorrektur: Bei umfangreichem HTML-Code in der HTML-Tabelle eines Versands tritt jetzt kein Leistungsproblem mehr auf. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* Fehlerkorrektur: Es wurde ein Problem behoben, das Benutzende davon abhielt, die Workflow-Option **Ausgewählte Zeilen zusammenführen** zu verwenden. (NEO-48488)
* Fehlerkorrektur: Es wurde ein Problem im Snowflake FDA-Connector behoben, das dazu führte, dass Einträge bei Verwendung der Option &quot;Einfache Relation mit Kardinalität 0 oder 1&quot; während der Anreicherung gelöscht wurden. (NEO-48737)
* Die verbleibenden Verweise auf die log4j-Bibliothek wurden aus der Campaign-Installation unter Windows entfernt. (NEO-44851)
* Fehlerkorrektur: Beim Hinzufügen des Indikators **Empfänger, die geöffnet haben** (estimatedRecipientOpen) zu den Zusatzdaten einer **Abfrage**-Workflow-Aktivität tritt kein Fehler mehr auf. (NEO-46665)
* Fehlerkorrektur: Die Verwaltung von Tracking-URLs wurde in Workflows mit mehreren Sendungen verbessert, um die Leistung zu verbessern. (NEO-50894) <!--OKKKK-->
* Fehlerkorrektur: Es wurde ein Problem behoben, das zum Scheitern der Replikation von Schemata führen konnte, die Xtkfolder verwenden. (NEO-46787) <!--OKKKK-->
* Fehlerkorrektur: Es wurde ein Problem behoben, dass dazu führen konnte, dass die benutzerdefinierte Spalte &quot;lastModified&quot; in der NmsSubscription-Tabelle gelöscht wurde. (NEO-48402)


