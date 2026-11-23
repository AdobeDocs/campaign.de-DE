---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 74%
---
# Sitzung

Anwendungs-Server-Sitzungen

## Methoden

| Methode | Beschreibung |
| --- | --- |
| [ApplyDuplicateRules](sm-session-applyduplicaterules.md) | Wendet die Duplizierungsregeln (u. a. Standardwerte) auf das als Parameter übergebene Dokument an. |
| [BearerTokenLogon](sm-session-bearertokenlogon.md) | Verbindungstoken |
| [ChangePassword](sm-session-changepassword.md) | Ändert das Kennwort des aktuellen Kontos |
| [DeleteCollection](sm-session-deletecollection.md) | Löscht eine Entitätenliste nach einer bestimmten Bedingung |
| [Differenz](sm-session-diff.md) | Gibt die aktuelle und die Originalversion eines Dokuments aus. |
| [Duplikat](sm-session-duplicate.md) | Dupliziert ein Quelldokument |
| [DuplicateTo](sm-session-duplicateto.md) | Dupliziert ein Quelldokument in einen bestimmten Ordner |
| [DuplicateWithMappingId](sm-session-duplicatewithmappingid.md) | Dupliziert ein Quelldokument und führt ein ID-Mapping durch |
| [Verschlüsseln](sm-session-encrypt.md) | Verschlüsselt den String mit dem Instanzschlüssel. |
| [EncryptServerPassword](sm-session-encryptserverpassword.md) | Verschlüsselt den String mit dem Serverschlüssel. |
| [FormatDataPolicy](sm-session-formatdatapolicy.md) | Wendet eine Transformation auf die Zeichenfolge gemäß der als Parameter übergebenen Datenrichtlinie an. Belässt die Zeichenfolge bei einem Fehler unverändert. |
| [GetActiveApplicationMenus](sm-session-getactiveapplicationmenus.md) | Gibt ein Dokument aus, das die Menüs der aktiven Anwendungen für den aktuellen Login enthält. |
| [GetCnxInfo](sm-session-getcnxinfo.md) | Ruft die aktuellen Verbindungsinformationen ab |
| [GetDefaultEntity](sm-session-getdefaultentity.md) | Gibt ein Dokument mit einer leeren Entität und ihren Standardwerten aus |
| [GetDirtyCacheEntities](sm-session-getdirtycacheentities.md) | Gibt die im Cache enthaltenen, nicht aktualisierten Entitäten aus |
| [GetEntityIfMoreRecent](sm-session-getentityifmorerecent.md) | Lädt eine Entität, wenn ihr MD5-Schlüssel vom als Parameter übergebenen Schlüssel abweicht |
| [GetImages](sm-session-getimages.md) | Lädt eine Bilderliste |
| [GetNewIds](sm-session-getnewids.md) | Erstellt eine Liste mit Kennungen der internen Schlüssel der Datenbank |
| [GetNewIdsEx](sm-session-getnewidsex.md) | Erstellt unter Angabe der anzuwendenden Sequenz eine Liste der eindeutigen Kennungen der Datenbank |
| [GetOption](sm-session-getoption.md) | Ausgabe des Werts einer Datenbankoption |
| [GetPkList](sm-session-getpklist.md) | Erstellt die Liste der Instanzkennungen |
| [GetServerTime](sm-session-getservertime.md) | Gibt die Uhrzeit des Servers aus |
| [GetUserInfo](sm-session-getuserinfo.md) | Zugriff auf die Informationen des aktuellen Benutzers |
| [HashPassword](sm-session-hashpassword.md) | Erzeugt den Hashwert eines Passworts mit dem Serverschlüssel. |
| [ImportCollection](sm-session-importcollection.md) | Aktualisiert eine Entitätenimportliste |
| [KillSession](sm-session-killsession.md) | Beendet die im Parameter bezeichnete Sitzung |
| [LOAD](sm-session-load.md) | Entität laden |
| [LoadAsText](sm-session-loadastext.md) | Abrufen des Entitätsinhalts als Text |
| [LoadIfExists](sm-session-loadifexists.md) | Lädt die Entität, wenn sie existiert |
| [Abmelden](sm-session-logoff.md) | Schließt die aktuelle Sitzung |
| [Anmelden](sm-session-logon.md) | Eröffnet eine Sitzung |
| [NewInstance](sm-session-newinstance.md) | Erstellt ein neues, vorinitialisiertes, aber nicht gespeichertes Dokument |
| [Entfernen](sm-session-remove.md) | Löscht die Entität |
| [ServerShutdown](sm-session-servershutdown.md) | Fährt den Server herunter |
| [SetDefaultValues](sm-session-setdefaultvalues.md) | Standardwerte ausgehend vom XPath definieren |
| [SetDefaults](sm-session-setdefaults.md) | Standardwerte definieren |
| [TestCnx](sm-session-testcnx.md) | Testet die Verbindung |
| [Write](sm-session-write.md) | Aktualisiert eine Entität |
| [WriteCollection](sm-session-writecollection.md) | Aktualisiert eine Entitätenliste |

## Generische Methoden

| Methode | Beschreibung |
| --- | --- |
| [Erstellen](f-create.md) | Erstellt eine neue Entität, die einem bestimmten Schema entspricht. |
| [LOAD](f-load.md) | Lädt eine Entität, die einem bestimmten Schema und Schlüssel entspricht, und gibt sie zurück. |
| [Speichern](m-entity-save.md) | Speichert eine Entität in der Datenbank |
