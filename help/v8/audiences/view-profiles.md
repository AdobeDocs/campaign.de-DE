---
title: Vorhandene Profile in Campaign anzeigen
description: Erfahren Sie, wie Sie in Campaign auf Kontaktdaten zugreifen können.
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
source-git-commit: c316da3c431e42860c46b5a23c73a7c129abf3ac
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 28%

---

# Vorhandene Profile anzeigen{#view-profiles}

Navigieren Sie zu **[!UICONTROL Profile und Zielgruppen]** , um auf in der Adobe Campaign-Datenbank gespeicherte Empfänger zuzugreifen.

Auf dieser Seite können Sie [Neuen Empfänger erstellen](create-profiles.md), bearbeiten Sie einen vorhandenen Empfänger und greifen Sie auf seine Profildetails zu.

![](assets/profiles-and-targets.png)

Erweiterte Profilmanipulationen erhalten Sie, wenn Sie den Campaign-Navigationsbaum über **[!UICONTROL Explorer]** auf der Adobe Campaign-Startseite.

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>Der integrierte Bildschirm Empfänger wird durch ein XML-Schema und das zugehörige Formular definiert. Das XML-Schema wird im **[!UICONTROL Administration > Konfiguration > Datenschemata]** Knoten des Adobe Campaign-Explorer-Baums. Nur erfahrene Benutzer können Änderungen an diesen Schemas vornehmen.

## Bearbeiten von Profilen{#edit-a-profiles}

Wählen Sie ein Profil aus, um Details auf einer neuen Registerkarte anzuzeigen.

![](assets/edit-a-profile.png)

In verschiedenen Tabs werden die Informationen bezüglich eines Profils nach Themen geordnet. Diese Tabs und ihr Inhalt hängen von Ihren spezifischen Einstellungen und installierten Packages ab.

Für einen typischen integrierten Empfänger haben Sie Zugriff auf die folgenden Registerkarten:

* **[!UICONTROL Allgemein]** für alle allgemeinen Profildaten. Insbesondere enthält es den Nachnamen, Vornamen, die E-Mail-Adresse, das E-Mail-Format usw.

   Auf dieser Registerkarte wird auch **Opt-out** Markierung für das Profil: wenn die **[!UICONTROL No longer contact (by any channel)]** aktiviert ist, befindet sich das Profil auf der Blockierungsliste. Diese Informationen werden den Kontaktdaten hinzugefügt, wenn der Empfänger beispielsweise auf einen Abmelde-Link in einem Newsletter geklickt hat. Auf einen solchen Empfänger werden keine Kanäle (E-Mail, Briefpost usw.) mehr abgefragt. Weitere Informationen hierzu finden Sie auf [dieser Seite](../send/quarantines.md).

* **Kontaktangaben**, die die Briefpost-Adresse des ausgewählten Profils enthält.

   Sie können in diesem Bildschirm den Qualitätsindex der Adresse und die Anzahl der Fehler in der Adresse überprüfen. Diese Informationen werden direkt vom Briefpost-Dienstleister verwendet, basierend auf der Anzahl der bei früheren Sendungen gefundenen Fehler. Sie können nicht manuell geändert werden.

* **Sonstiges**, für spezifische Felder, die je nach Bedarf personalisiert und ausgefüllt werden können.

   Verwenden Sie die **[!UICONTROL Feldeigenschaften...]** Kontextmenü, um die Namen der Felder zu ändern und ihr Format zu definieren.

   ![](assets/other-tab-field-properties.png)

   Geben Sie die neuen Einstellungen wie folgt ein:

   ![](assets/change-field-properties.png)

   Überprüfen Sie die Aktualisierung in der Benutzeroberfläche:

   ![](assets/other-tab-updated.png)


   >[!CAUTION]
   >Änderungen gelten für alle Empfänger.


* **Abonnements** für alle aktiven Abonnements für Dienste. Verwenden Sie die **Geschichte** -Tab, um die Details der An- und Abmeldungen für diesen Kontakt aufzurufen.

   ![](assets/subscription-tab.png)

   Weitere Informationen zu Abonnements [in diesem Abschnitt](../start/subscriptions.md).

* **Sendungen**, für alle Versandlogs für das ausgewählte Profil. In diesem Tab können Sie auf den Marketingverlauf des Kontakts zugreifen: Titel, Daten und Status aller an das Profil adressierten Versandaktionen über alle Kanäle.


* **Tracking**, für alle Trackinglogs für das ausgewählte Profil. Diese Informationen werden verwendet, um das Profil-Verhalten nach Sendungen zu verfolgen. Dieser Tab zeigt alle in Sendungen getrackten URLs an. In der Regel enthält die anpassbare Liste folgende Daten: die geklickte URL, Datum und Uhrzeit des Klicks, das Dokument, in dem die URL enthalten war

   Weitere Informationen zum Tracking [in diesem Abschnitt](../start/tracking.md).


## Aktive Profile {#active-profiles}

Aktive Profile sind die Profile, die zu Fakturierungszwecken berücksichtigt werden.

Für die Fakturierung werden nur **aktive** Profile berücksichtigt. Ein Profil wird als aktiv betrachtet, wenn es in den vergangenen zwölf Monaten über einen beliebigen Kanal angesprochen wurde oder mit ihm kommuniziert wurde.

Ein Profil, das für mehrere Sendungen ausgewählt wurde, wird nur einmal gezählt.

Die Anzahl der aktiven Profile ist nur für **Marketing-Instanzen** verfügbar. Sie ist nicht für Ausführungsinstanzen verfügbar, d. h. MID (Mid-Sourcing)- und RT (Message Center-/Echtzeit-Messaging)-Instanzen.

>[!NOTE]
>
>Sie können auch die Anzahl der aktiven Profile in Ihrer Instanz direkt über das Control Panel von Campaign überwachen. Weitere Informationen hierzu finden Sie in der [Dokumentation zu Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=de).
