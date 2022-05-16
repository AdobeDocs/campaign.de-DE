---
title: Campaign und Microsoft Dynamics verwenden
description: Erfahren Sie, wie Sie mit Campaign und Microsoft Dynamics arbeiten.
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '1399'
ht-degree: 42%

---

# Campaign und Microsoft Dynamics 365 verwenden{#crm-ms-dynamics}

Aktivieren Sie Ihre CRM-Daten für die kanalübergreifende Kommunikation: Erfahren Sie, wie Sie Kontakte von **Microsoft Dynamics 365** und teilen Sie die Kampagnenleistungsdaten (Sendungen, Öffnungen, Klicks und Bounces) von Adobe Campaign nach Microsoft Dynamics 365 zurück.

Nach der Konfiguration erfolgt die Datensynchronisation zwischen Systemen über eine spezielle Workflow-Aktivität. [Weitere Informationen](crm-data-sync.md).

>[!NOTE]
>
>Die unterstützten Microsoft Dynamics-Versionen werden in Campaign erläutert. [Kompatibilitätsmatrix](../start/compatibility-matrix.md).

Gehen Sie wie folgt vor, um ein dediziertes externes Konto für den Import und Export von Microsoft Dynamics 365-Daten in Adobe Campaign zu konfigurieren.

Für jedes System müssen diese Schritte von einem Administrator ausgeführt werden.

>[!CAUTION]
> Die Schritte in dieser Dokumentation helfen Ihnen beim Erstellen von Integrationen/Registrierungen, die die Zuweisung von Berechtigungen und/oder Administratorzugriff erfordern. Sie müssen vor der Ausführung sicherstellen, dass diese Schritte den Richtlinien Ihres Unternehmens entsprechen, und die Schritte dann sorgfältig durchführen.

## Microsoft Dynamics 365 konfigurieren {#config-crm-microsoft}

So verbinden Sie Microsoft Dynamics 365 mit Adobe Campaign über **Web-API**, melden Sie sich bei [Microsoft Azure Directory](https://portal.azure.com) mit **Globaler Administrator** Anmeldedaten und führen Sie die folgenden Schritte aus:

1. Rufen Sie Ihre Dynamics 365-Anwendungs-ID (Client) ab. [Weitere Informationen](#get-client-id-microsoft)
1. Microsoft Dynamics-Zertifikatschlüsselkennung und Schlüssel-ID generieren. [Weitere Informationen](#config-certificate-key-id)
1. Berechtigungen konfigurieren. [Weitere Informationen](#config-permissions-microsoft)
1. Anwender erstellen. [Weitere Informationen](#create-app-user-microsoft)
1. Privaten Schlüssel kodieren. [Weitere Informationen](#configure-acc-for-microsoftt)


### Dynamics 365-Client-ID abrufen {#get-client-id-microsoft}

Um die Anwendungs-ID (Client) zu erhalten, müssen Sie eine App in Azure Active Directory registrieren.

1. Navigieren Sie zu **Azure Active Directory > App-Registrierungen** und wählen Sie **Neue Registrierung**.
1. Geben Sie einen eindeutigen Namen ein, der zur Identifizierung einer Instanz beitragen kann, z. B. **adobecampaign`<instance identifier>`**.

Nach dem Speichern weist Microsoft Azure Directory eine eindeutige **Anwendungs-ID (client)** auf Ihre App. Sie benötigen diese ID später bei der Konfiguration von Dynamics 365 in Adobe Campaign.

Weitere Informationen finden Sie unter [Dokumentation zu Microsoft Dynamics 365](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory).

### Microsoft Dynamics-Zertifikatschlüsselkennung und Schlüssel-ID generieren {#config-certificate-key-id}

So rufen Sie die **Zertifikatschlüsselkennung (customKeyIdentifier)** und **Schlüssel-ID (keyId)**, müssen Sie ein Zertifikat hochladen. Zertifikate können als Geheimnisse zum Nachweis der Identität der Anwendung beim Anfordern eines Tokens verwendet werden. Sie können auch als öffentliche Schlüssel bezeichnet werden.

Gehen Sie wie folgt vor:

1. Navigieren Sie zu **Azure Active Directory > App-Registrierungen** und wählen Sie die zuvor erstellte Anwendung aus.
1. Wählen Sie aus **Zertifikate und Geheimnis**.
1. Aus dem **Zertifikate** Registerkarte, klicken Sie auf **Zertifikat hochladen**
1. Laden Sie Ihr öffentliches Zertifikat hoch.
1. Navigieren Sie zum **Manifest** Link zum Abrufen der **Zertifikatschlüsselkennung (customKeyIdentifier)** und **Schlüssel-ID (keyId)**.

Die **Zertifikatschlüsselkennung (customKeyIdentifier)** und **Schlüssel-ID (keyId)** in Campaign benötigt werden, um Ihr externes Microsoft Dynamics 365 CRM-Konto mithilfe des Zertifikats zu konfigurieren **[!UICONTROL CRM-O-Auth-Typ]**.

+++ Generieren des öffentlichen Zertifikats

Um das Zertifikat zu generieren, können Sie openssl verwenden.

Beispiel:

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>Sie können die Anzahl der Tage, hier `-days 365`, im Code-Beispiel ändern, sodass der Gültigkeitszeitraum des Zertifikats verlängert wird.

Anschließend müssen Sie das Zertifikat in base64 kodieren. Dazu können Sie einen Base64-Encoder oder die Befehlszeile `base64 -w0 private.key` für Linux verwenden.

+++

### Berechtigungen konfigurieren {#config-permissions-microsoft}

**Schritt 1**: Konfigurieren Sie die **erforderlichen Berechtigungen** für die erstellte Anwendung.

1. Navigieren Sie zu **Azure Active Directory > App-Registrierungen** und wählen Sie die zuvor erstellte Anwendung aus.
1. Klicken Sie oben links auf **Einstellungen**.
1. Klicken Sie unter **Erforderliche Berechtigungen** auf **Hinzufügen** und **wählen Sie eine API > Dynamics CRM Online**.
1. Klicken Sie auf **Auswählen**, aktivieren Sie die Checkbox **Zugriff auf Dynamics 365 als Organisationsbenutzer** und klicken Sie erneut auf **Auswählen**.
1. Wählen Sie dann aus Ihrer Anwendung das **Manifest** unter dem Menü **Verwalten** aus.
1. Ändern Sie im **Manifest**-Editor die Eigenschaft `allowPublicClient` von `null` auf `true` und klicken Sie auf **Speichern**.

**Schritt 2**: Erteilen Sie die Zustimmung durch den Administrator

1. Gehen Sie zu **Azure Active Directory > Enterprise-Anwendungen**.
1. Wählen Sie die Anwendung aus, der Sie eine mandantenweite Administrator-Zustimmung erteilen möchten.
1. Wählen Sie im Menü im linken Fensterbereich unter **Sicherheit** die Option **Berechtigungen** aus.
1. Klicken Sie auf **Administratorzustimmung erteilen**.

Weiterführende Informationen dazu finden Sie in der [Dokumentation zu Azure](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### Anwender erstellen {#create-app-user-microsoft}

>[!NOTE]
>
> Dieser Schritt ist bei der Authentifizierung mit **[!UICONTROL einem Passwort]** optional.

Der Anwendungsbenutzer ist derjenige Benutzer, den die oben registrierte Anwendung verwenden wird. Alle Änderungen, die mit der oben registrierten Anwendung an Microsoft Dynamics vorgenommen werden, erfolgen über diesen Benutzer.

**Schritt 1**: Einen nicht interaktiven Benutzer in Azure Active Directory erstellen

1. Klicken Sie auf **Azure Active Directory > Benutzer** und dann auf **Neuer Benutzer**.
1. Geben Sie einen geeigneten Namen ein, den Sie verwenden möchten; der Benutzername sollte im E-Mail-Format vorliegen.
1. Wählen Sie **Dynamics 365-Administrator** in der **Verzeichnisrolle**.

**Schritt 2**: Dem erstellten Benutzer eine ordnungsgemäße Lizenz zuweisen

1. Klicken Sie in [Microsoft Azure](https://portal.azure.com) auf **Admin-App**.
1. Navigieren Sie zu **Benutzer > Aktive Benutzer** und klicken Sie auf den neu erstellten Benutzer.
1. Klicken Sie auf **Produktlizenzen bearbeiten** und wählen Sie **Dynamics 365 Customer Engagement-Plan**.
1. Klicken Sie auf **Schließen**.

**Schritt 3**: Anwendungsbenutzer in Dynamics CRM erstellen

1. Navigieren Sie von [Microsoft Azure](https://portal.azure.com) zu **Einstellungen > Sicherheit > Benutzer**.
1. Klicken Sie auf Dropdown, wählen Sie **Anwendungsbenutzer** und klicken Sie auf **Neu**.
1. Verwenden Sie denselben Benutzernamen wie der Benutzer, der oben im aktiven Verzeichnis erstellt wurde.
1. Weisen Sie die **Anwendungs-ID** für [die zuvor erstellte Anwendung zu](#get-client-id-microsoft).
1. Klicken Sie auf **Rollen verwalten** und wählen Sie den Benutzer die Rolle **Systemadministrator** für aus.

## Campaign konfigurieren {#configure-acc-for-microsoft}

### Verbindung erstellen{#new-ms-dyn-external-account}

Zunächst müssen Sie das externe Microsoft Dynamics 365-Konto erstellen.

1. Durchsuchen Sie die **[!UICONTROL Administration > Plattform > Externe Konten]** und erstellen Sie ein externes Konto.
1. Auswählen **[!UICONTROL Microsoft Dynamics CRM]** externes Konto im **Typ** Abschnitt.
1. Wählen Sie die Authentifizierungsmethode im **[!UICONTROL CRM-O-Auth-Typ]** Dropdown-Liste.

   ![](assets/ms-dyn-external-account.png)

   1. So konfigurieren Sie das externe Microsoft Dynamics CRM-Konto für die Verbindung mit Adobe Campaign mit **Kennwortberechtigungen** Geben Sie die folgenden Details an:

      * **Server**: URL Ihres Microsoft CRM-Servers Um Ihre Microsoft CRM-Server-URL zu finden, rufen Sie Ihr Microsoft Dynamics CRM-Konto auf, klicken Sie dann auf Dynamics 365 und wählen Sie Ihre App aus. Ihre Server-URL finden Sie dann in der Adressleiste Ihres Browsers, z. B. https://myserver.crm.dynamics.com/.
      * **Konto**: Konto, mit dem die Anmeldung bei Microsoft CRM erfolgt
      * **Passwort**: Konto, mit dem die Anmeldung bei Microsoft CRM erfolgt
      * **Client-Kennung**: Anwendungs-ID (Client), die über das Verwaltungsportal von Microsoft Azure im Feld Code-Kategorie aktualisieren, Client-ID gefunden werden kann.
      * **CRM-Version**: Wählen Sie die CRM-Version Dynamics CRM 365 aus.
   1. So konfigurieren Sie das externe Microsoft Dynamics CRM-Konto für die Verbindung mit Adobe Campaign mit einem **Zertifikat** Geben Sie die folgenden Details an:

      * **Server**: URL Ihres Microsoft CRM-Servers Um Ihre Microsoft CRM-Server-URL zu finden, rufen Sie Ihr Microsoft Dynamics CRM-Konto auf, klicken Sie dann auf Dynamics 365 und wählen Sie Ihre App aus. Ihre Server-URL finden Sie dann in der Adressleiste Ihres Browsers, z. B. https://myserver.crm.dynamics.com/.
      * **Privater Schlüssel**: Kopieren/Einfügen Sie den privaten Schlüssel, kodiert base64, wie hier beschrieben: [diesem Abschnitt](#config-certificate-key-id).
      * **Schlüssel-ID**: Schlüssel verfügbar im **Manifest** Registerkarte Ihrer Anwendung, wie hier beschrieben: [diesem Abschnitt](#config-certificate-key-id).
      * **Benutzerdefinierte Schlüsselkennung**: Kennung verfügbar im **Manifest** Registerkarte Ihrer Anwendung, wie hier beschrieben: [diesem Abschnitt](#config-certificate-key-id).
      * **Client-Kennung**: Anwendungs-ID (Client), die Sie über das Verwaltungsportal von Microsoft Azure finden, wie hier beschrieben: [diesem Abschnitt](#get-client-id-microsoft).
      * **CRM-Version**: Wählen Sie die CRM-Version Dynamics CRM 365 aus.


1. Wählen Sie die **Aktivieren** aktivieren, um das Konto in Campaign zu aktivieren.

>[!NOTE]
>
>Um das Setup zu genehmigen, melden Sie sich ab und wieder bei der Adobe Campaign-Konsole an.

### Zu synchronisierende Tabellen auswählen{#ms-dyn-create-tables}

Sie können jetzt Tabellen zur Synchronisierung konfigurieren.

1. Klicken Sie auf **[!UICONTROL Konfigurationsassistent für Microsoft CRM ...]**.
1. Wählen Sie die zu synchronisierenden Tabellen aus und starten Sie den Prozess.
1. Prüfen Sie unter dem Knoten **[!UICONTROL Administration > Konfiguration > Datenschema]** das in Adobe Campaign erzeugte Schema.

>[!NOTE]
>
>Stellen Sie sicher, dass Sie der Zulassungsliste zwei URLs hinzufügen: die Server-URL und `login.microsoftonline.com`. Wenden Sie sich dazu an Ihren Kundenbetreuer bei der Adobe.

## Synchronisation der Auflistungen,{#sfdc-enum-sync}

Nach der Erstellung des Schemas können Sie Auflistungen automatisch von Dynamics 365 nach Adobe Campaign synchronisieren.

1. Öffnen Sie die Assistenzkraft über die  **[!UICONTROL Auflistungen synchronisieren...]** Link.
1. Wählen Sie die Adobe Campaign-Auflistung aus, die der Dynamics 365-Auflistung entspricht.
Sie können alle Werte einer Adobe-Campaign-Auflistung durch die des CRM-Systems ersetzen: Wählen Sie hierzu in der Spalte **[!UICONTROL Ersetzen]** die Option **[!UICONTROL Ja]**.
1. Klicken **[!UICONTROL Nächste]** und dann **[!UICONTROL Starten]** um mit dem Import der Auflistungen zu beginnen.
1. Durchsuchen Sie die **[!UICONTROL Administration > Plattform > Auflistungen]** Knoten zur Überprüfung der importierten Werte.

Adobe Campaign und Microsoft Dynamics 365 sind jetzt verbunden. Sie können eine Datensynchronisation zwischen den beiden Systemen einrichten.

Um Daten zwischen Adobe Campaign-Daten und Microsoft CRM zu synchronisieren, erstellen Sie einen Workflow und verwenden Sie die **[!UICONTROL CRM-Connector]** Aktivität.

Weitere Informationen zur Datensynchronisation finden Sie [auf dieser Seite](crm-data-sync.md).

### Unterstützte Felddatentypen {#ms-dyn-supported-types}

Bei Microsoft Dynamics 365 werden folgende Attributtypen unterstützt/nicht unterstützt:


| Attributtyp | Unterstützt |
| --------------------------------------------------------------------------------- | --------- |
| Basistypen: Boolesch, Datum + Uhrzeit, Dezimalzahl, Gleitkommazahl, Dublette, Integer, Bigint, Zeichenfolge | Ja |
| Geld (als Dublette) | Ja |
| memo, entityname, primarykey, uniqueidentifier (als Zeichenfolgen) | Ja |
| Status, Auswahlliste (wir speichern die möglichen Werte in Auflistungen), Status (Zeichenfolge) | Ja |
| owner (als Zeichenfolge) | Ja |
| Suche (nur Referenzsuche einzelner Entitäten) | Ja |
| customer | Nein |
| Regarding | Nein |
| PartyList | Nein |
| ManagedProperty | Nein |
