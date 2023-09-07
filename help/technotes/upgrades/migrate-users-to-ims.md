---
title: Migrieren von Campaign-Benutzern zum Adobe Identity Management System (IMS)
description: Erfahren Sie, wie Sie Campaign-Benutzer zu Adobe Identity Management System (IMS) migrieren.
hide: true
hidefromtoc: true
source-git-commit: 11128dcb26119383b86aa62561ec0ce1a3c138ad
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 10%

---

# Migrieren von Campaign-Benutzern zum Adobe Identity Management System (IMS) {#migrate-users-to-ims}

Ab Campaign v8.6 wird der Authentifizierungsprozess für Campaign v8 verbessert. Alle Benutzer verwenden [Adobe Identity Management System (IMS)](https://helpx.adobe.com/de/enterprise/using/identity.html){target="_blank"} nur zur Verbindung mit Campaign. Die Verbindung mit dem Benutzer/Kennwort wird nicht mehr zugelassen. Adobe empfiehlt, diese Migration in Campaign v8.5.2 durchzuführen, um eine reibungslose Migration zu Campaign v8.6 zu ermöglichen.

In diesem Artikel werden die Schritte beschrieben, die zum Migrieren einer technischen Benutzerin bzw. eines technischen Benutzers zu einem technischen Konto in der Adobe Developer Console erforderlich sind.

## Was hat sich geändert?{#move-to-ims-changes}

Alle regulären Campaign-Benutzer sollten über Adobe Identity Management System (IMS) bereits über ihre Adobe ID eine Verbindung zur Adobe Campaign-Clientkonsole herstellen. Bei einigen älteren Konfigurationen waren jedoch noch Benutzer-/Kennwortverbindungen verfügbar. Dies ist ab Campaign v8.6 nicht mehr zulässig.

Darüber hinaus ruft die Adobe Campaign Client-Anwendung im Rahmen der Bemühungen zur Verbesserung des Sicherheits- und Authentifizierungsprozesses jetzt Campaign-APIs direkt mithilfe des Tokens für das technische IMS-Konto auf. Die Migration technischer Operatoren wird in einem speziellen Artikel beschrieben, der unter [diese Seite](ims-migration.md).

Diese Änderung gilt ab Campaign v8.5.2 und wird ab Campaign v8.6 **obligatorisch**.


## Sind Sie betroffen?{#migrate-ims-impacts}

Wenn Benutzer in Ihrer Organisation über ihr Login/Passwort eine Verbindung zur Campaign-Clientkonsole herstellen (auch bekannt als nativer Authentifizierung), sind Sie betroffen und müssen diese Operatoren wie unten beschrieben zu Adobe IMS migrieren.

Die IMS-Migration ist eine Sicherheitsanforderung, um Ihre Umgebungen sicher und standardisiert zu machen, da die meisten anderen Adobe DX-Apps bereits auf IMS installiert sind.

## Wie wird die Migration durchgeführt?{#ims-migration-procedure}

### Voraussetzungen{#ims-migration-prerequisites}

Bevor Sie mit dem Migrationsprozess beginnen, müssen Sie sich an Ihren Adobe-Support-Mitarbeiter (Transition Manager) wenden, damit Adobe-Techniker Ihre bestehenden Benutzergruppen und spezifischen Berechtigungen zum Adobe Identity Management System (IMS) migrieren können.

### Die wichtigsten Schritte {#ims-migration-steps}

Die wichtigsten Schritte für diese Migration sind unten aufgeführt:

1. Adobe aktualisiert Ihre Umgebungen auf Campaign v8.5.2.
1. Nach dem Upgrade können Sie weiterhin neue Benutzer mit beiden Methoden erstellen, als nativen Benutzer oder mit IMS.
1. Ihr interner Campaign-Administrator muss allen nativen Benutzern in der Campaign-Clientkonsole eindeutige E-Mails hinzufügen und nach Abschluss dieses Vorgangs Ihrem Adobe Transition Manager bestätigen. Dieser Schritt wird im Abschnitt [diesem Abschnitt](#ims-migration-id).
1. Arbeiten Sie mit Adobe, um ein Datum zu sichern, an dem Adobe die automatisierte Migration von nicht-technischen Benutzern (Benutzern) und Produktprofilen durchführen kann. Für diesen Schritt ist ein Stundenfenster ohne Ausfallzeiten für Ihre Instanzen erforderlich.
1. Ihr interner Campaign-Administrator validiert diese Änderung und gibt die Abmeldung an. Nach dieser Migration dürfen Sie keinen weiteren Benutzer mehr erstellen, der sich mit seinem Login und Passwort authentifiziert.

Sie können jetzt die Migration technischer Benutzer auf IMS gemäß [diese Technote](ims-migration.md)und bestätigen Sie nach Abschluss des Vorgangs mit Ihrem Adobe Transition Manager.
Adobe markiert dann die Migration als abgeschlossen und aktiviert die Flags, um die Erstellung neuer nativer Benutzer und die Anmeldung nativer Benutzer zu blockieren.

## Häufig gestellte Fragen? {#ims-migration-faq}

### Wann können Sie mit der Migration beginnen? {#ims-migration-start}

Voraussetzung für die Migration auf das Adobe Identity Management-System (IMS) ist die Aktualisierung Ihrer Umgebung auf Campaign v8.5.2.

Sie können die IMS-Migration in Ihrer Staging-Umgebung starten, sobald sie auf Campaign v8.5.2 aktualisiert wurde, und entsprechend für die Produktionsumgebung planen.

### Was passiert nach der Build-Aktualisierung auf Version 8.5.2? {#ims-migration-after-upgrade}

Nachdem Ihre Umgebungen auf Campaign v8.5.2 aktualisiert wurden, können Sie die Migration des Adobe Identity Management-Systems (IMS) durchführen.

Die neue native Benutzererstellung ist weiterhin zulässig, bis die IMS-Migration abgeschlossen ist.

### Wann ist die Migration abgeschlossen? {#ims-migration-end}

Sobald die Migration der Endbenutzer und die technische Benutzermigration zum Adobe Identity Management System (IMS) abgeschlossen sind, müssen Sie sich an Ihren Adobe Transition Manager wenden, damit Adobe Ihre Migration als abgeschlossen kennzeichnen und die Benutzererstellung über die Clientkonsole und die native Benutzeranmeldung blockieren kann.


### Wie werden Benutzer nach der Migration erstellt? {#ims-migration-native}

Sobald die vollständige IMS-Migration abgeschlossen ist, wendet Adobe die Einschränkungen an, die die Erstellung neuer nativer Benutzer blockieren. Diese Einschränkungen werden erst nach Abschluss der IMS-Migration angewendet.

Für neue Kunden ist die Erstellung neuer nativer Benutzer von Anfang an nicht erlaubt.

Als Campaign-Administrator können Sie den Benutzern Ihrer Organisation über Adobe Admin Console und die Campaign Client Console Berechtigungen erteilen. Benutzer melden sich mit ihrer Adobe ID bei Adobe Campaign an. Weitere Informationen finden Sie unter [diese Dokumentation](../../v8/start/gs-permissions.md).

### Wie kann ich E-Mails für aktuelle native Benutzer hinzufügen? {#ims-migration-id}

Als Campaign-Administrator müssen Sie allen nativen Benutzern über die Clientkonsole E-Mail-IDs hinzufügen. Gehen Sie dazu wie folgt vor:

1. Stellen Sie eine Verbindung zur Client-Konsole her und navigieren Sie zu **Administration > Zugriffe > Benutzer**
1. Wählen Sie in der Benutzerliste den zu aktualisierenden Operator aus.
1. Geben Sie die E-Mail-Adresse des Benutzers im **Kontaktstellen** Abschnitt des Formulars des Benutzers.
1. Speichern Sie Ihre Änderungen.


### Wie meldet man sich über IMS bei Campaign an? {#ims-migration-log}

Erfahren Sie, wie Sie mit Ihrer Adobe ID eine Verbindung zu Campaign herstellen können in [diesem Abschnitt](../../v8/start/connect.md).