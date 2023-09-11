---
title: Migrieren von Campaign-Benutzern zum Adobe Identity Management System (IMS)
description: Erfahren Sie, wie Sie Campaign-Benutzer zu Adobe Identity Management System (IMS) migrieren.
hide: true
hidefromtoc: true
source-git-commit: 53412ab167721c8a8f9d84e07112b0f410d4785d
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 10%

---

# Migrieren von Campaign-Benutzern zum Adobe Identity Management System (IMS) {#migrate-users-to-ims}

Ab Campaign v8.6 wird der Authentifizierungsprozess für Campaign v8 verbessert. Alle Benutzer verwenden [Adobe Identity Management System (IMS)](https://helpx.adobe.com/de/enterprise/using/identity.html){target="_blank"} **only** , um eine Verbindung mit Campaign herzustellen. Die Verbindung mit Benutzer/Kennwort (auch als native Authentifizierung bezeichnet) ist nicht mehr zulässig. Adobe empfiehlt, diese Migration in Campaign v8.5.2 durchzuführen, um eine reibungslose Migration zu Campaign v8.6 zu ermöglichen.

Wenn Sie als Campaign Classic v7 Managed Services-Kunde zu Campaign v8 migrieren, gilt dieses Verfahren auch für Sie.

In diesem Artikel werden die Schritte beschrieben, die zum Migrieren einer technischen Benutzerin bzw. eines technischen Benutzers zu einem technischen Konto in der Adobe Developer Console erforderlich sind.

## Was hat sich geändert?{#move-to-ims-changes}

Ab Campaign v8 sollten alle normalen Benutzer über Adobe Identity Management System (IMS) bereits über ihre Adobe ID eine Verbindung zur Adobe Campaign-Clientkonsole herstellen. Bei einigen älteren Konfigurationen waren jedoch noch Benutzer-/Kennwortverbindungen verfügbar. **Dies ist ab Campaign v8.6 nicht mehr zulässig.**

Darüber hinaus ruft die Adobe Campaign-Clientanwendung im Rahmen der Bemühungen zur Verbesserung des Sicherheits- und Authentifizierungsprozesses jetzt Campaign-APIs direkt mithilfe des Tokens für das technische IMS-Konto auf. Die Migration für technische Benutzer wird in einem speziellen Artikel beschrieben, der unter [diese Seite](ims-migration.md).

Diese Änderung gilt ab Campaign v8.5.2 und wird ab Campaign v8.6 **obligatorisch**.

## Sind Sie betroffen?{#migrate-ims-impacts}

Wenn Benutzer in Ihrer Organisation über ihr Login/Passwort eine Verbindung zur Campaign-Clientkonsole herstellen (auch bekannt als nativer Authentifizierung), sind Sie betroffen und müssen diese Operatoren wie unten beschrieben zu Adobe IMS migrieren.

Migration zu [Adobe Identity Management System (IMS)](https://helpx.adobe.com/de/enterprise/using/identity.html){target="_blank"} ist eine Sicherheitsanforderung, um Ihre Umgebungen sicher und standardisiert zu gestalten, da die meisten anderen Adobe Experience Cloud-Lösungen und -Apps bereits auf IMS installiert sind.

## Wie wird die Migration durchgeführt?{#ims-migration-procedure}

### Voraussetzungen{#ims-migration-prerequisites}

Bevor Sie mit dem Migrationsprozess beginnen, müssen Sie sich an Ihren Adobe-Support-Mitarbeiter (Transition Manager) wenden, damit Adobe-Techniker Ihre bestehenden Benutzergruppen und spezifischen Berechtigungen zum Adobe Identity Management System (IMS) migrieren können.

### Die wichtigsten Schritte {#ims-migration-steps}

Die wichtigsten Schritte für diese Migration sind unten aufgeführt:

1. Adobe aktualisiert Ihre Umgebungen auf Campaign v8.5.2.
1. Nach dem Upgrade können Sie weiterhin neue Benutzer mit beiden Methoden erstellen, als nativen Benutzer oder mit IMS.
1. Ihr interner Campaign-Administrator muss allen nativen Benutzern in der Campaign-Clientkonsole eindeutige E-Mails hinzufügen und nach Abschluss dieses Vorgangs Ihrem Adobe Transition Manager bestätigen. Dieser Schritt wird im Abschnitt [diesem Abschnitt](#ims-migration-id).
1. Arbeiten Sie mit Adobe zusammen, um ein Datum zu sichern, an dem Adobe die automatisierte Migration für Ihre nicht-technischen Anwender (Benutzer) und Produktprofile durchführen kann. Für diesen Schritt ist ein Stundenfenster ohne Ausfallzeiten für Ihre Instanzen erforderlich.
1. Ihr interner Campaign-Administrator validiert diese Änderungen und stellt eine Abmeldung bereit. Nach dieser Migration dürfen Sie keinen weiteren Benutzer mehr erstellen, der sich mit seinem Login und Passwort authentifiziert.

Sie können jetzt Ihren/Ihre technischen Benutzer zur Adobe Developer Console migrieren, wie im Abschnitt [diese Technote](ims-migration.md). Dieser Schritt ist bei der Verwendung von Campaign-APIs obligatorisch.

Bestätigen Sie nach Abschluss dieser Migration Ihren Adobe Transition Manager: Adobe markiert die Migration als abgeschlossen und blockiert die neue native Benutzererstellung und die native Benutzeranmeldung. Ihre Umgebung wird dann gesichert und standardisiert.

## Häufig gestellte Fragen {#ims-migration-faq}

### Wann kann ich die Migration starten? {#ims-migration-start}

Voraussetzung für die Migration zu [Adobe Identity Management System (IMS)](https://helpx.adobe.com/de/enterprise/using/identity.html){target="_blank"} ist, Ihre Umgebung auf Campaign v8.5.2 zu aktualisieren.

Sie können die IMS-Migration in Ihrer Staging-Umgebung starten, sobald sie auf Campaign v8.5.2 aktualisiert wurde, und entsprechend für die Produktionsumgebung planen.

### Was passiert nach einem Build-Upgrade auf Campaign v8.5.2? {#ims-migration-after-upgrade}

Nachdem Ihre Umgebungen auf Campaign v8.5.2 aktualisiert wurden, können Sie mit der Umstellung auf [Adobe Identity Management System (IMS)](https://helpx.adobe.com/de/enterprise/using/identity.html){target="_blank"}.

Die neue native Benutzererstellung ist weiterhin zulässig, bis die IMS-Migration abgeschlossen ist.

### Wann ist die Migration abgeschlossen? {#ims-migration-end}

Sobald die Migration der Endbenutzer und die technische Benutzermigration auf das Adobe Identity Management System (IMS) abgeschlossen sind, müssen Sie sich an Ihren Adobe Transition Manager wenden, damit Adobe Ihre Migration als abgeschlossen kennzeichnen und die Benutzererstellung über die Clientkonsole blockieren und die native Benutzeranmeldung deaktivieren kann.


### Wie werden Benutzer nach der Migration erstellt? {#ims-migration-native}

Sobald die vollständige IMS-Migration abgeschlossen ist, wendet Adobe die Einschränkungen an, die die Erstellung neuer nativer Benutzer blockieren. Diese Einschränkungen werden erst nach Abschluss der IMS-Migration angewendet.

Für neue Kunden ist die Erstellung neuer nativer Benutzer von Anfang an nicht erlaubt.

Als Campaign-Administrator können Sie den Benutzern Ihrer Organisation über Adobe Admin Console und die Campaign Client Console Berechtigungen erteilen. Benutzer melden sich mit ihrer Adobe ID bei Adobe Campaign an. Weitere Informationen finden Sie unter [diese Dokumentation](../../v8/start/gs-permissions.md).

### Wie kann ich E-Mails für aktuelle native Benutzer hinzufügen? {#ims-migration-id}

Als Campaign-Administrator müssen Sie allen nativen Benutzern über die Clientkonsole E-Mail-IDs hinzufügen. Gehen Sie dazu wie folgt vor:

1. Stellen Sie eine Verbindung zur Client-Konsole her und navigieren Sie zu **Administration > Zugriffe > Benutzer**.
1. Wählen Sie in der Benutzerliste den zu aktualisierenden Operator aus.
1. Geben Sie die E-Mail-Adresse des Benutzers im **Kontaktstellen** Abschnitt des Formulars des Benutzers.
1. Speichern Sie Ihre Änderungen.

Sie können auch eine CSV-Datei importieren, um alle Ihre Benutzerprofile mit ihrer E-Mail zu aktualisieren.


### Wie meldet man sich über IMS bei Campaign an? {#ims-migration-log}

Erfahren Sie, wie Sie mit Ihrer Adobe ID eine Verbindung zu Campaign herstellen können in [diesem Abschnitt](../../v8/start/connect.md).

### Wird es während dieser Migration zu Ausfallzeiten kommen? {#ims-migration-downtime}

Um die Migration abzuschließen (Benutzer und Produktprofile migrieren), erfordert die Adobe ein stündiges Fenster ohne Ausfallzeiten in Ihre Instanzen (Workflows usw.).

Während dieses Zeitraums müssen sich alle Campaign-Benutzer ab- und wieder mit ihrer Adobe ID anmelden, sobald die Migration auf IMS abgeschlossen ist.

### Was passiert mit Benutzern, die während der IMS-Benutzermigration angemeldet sind? {#ims-migration-log-off}

Adobe empfiehlt dringend, dass alle Benutzer während des Migrationsfensters abgemeldet werden.

### Benutzer in meinem Unternehmen verwenden IMS bereits. Muss ich trotzdem IMS-Migration durchführen?{#ims-migration-needed}

Diese Migration umfasst zwei Aspekte: die Migration von Endbenutzern und die Migration technischer Benutzer (wird in APIs in Ihrem benutzerspezifischen Code verwendet).

Wenn alle Benutzer (Campaign-Benutzer) IMS verwenden, müssen Sie diese Migration nicht durchführen. Sie müssen jedoch weiterhin technische Benutzer migrieren, die Sie möglicherweise in benutzerdefiniertem Code verwendet haben. Weitere Informationen finden Sie auf [dieser Seite](ims-migration.md).

Sobald diese Migration abgeschlossen ist, müssen Sie sich an Ihren Adobe Transition Manager wenden, damit Adobe die Migration abschließt.

## Nützliche Links {#ims-useful-links}

* [Migration von technischen Benutzerinnen und Benutzern zur Adobe Developer Console](ims-migration.md)
* [Herstellen einer Verbindung zu Adobe Campaign v8](../../v8/start/connect.md)
* [Zugriff und Berechtigungen in Adobe Campaign v8](../../v8/start/gs-permissions.md)
* [Versionshinweise zu Adobe Campaign v8](../../v8/start/release-notes.md)
* [Was ist Adobe Identity Management System (IMS)?](https://helpx.adobe.com/de/enterprise/using/identity.html){target="_blank"}

