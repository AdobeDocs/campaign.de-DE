---
title: Mit Campaign und Twitter arbeiten
description: Erfahren Sie, wie Sie Ihre Campaign-Umgebung mit Twitter integrieren.
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: true
hide: true
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 137dba3461a82621af7d2e5f54442bf87422ad47
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 29%

---

# Mit Campaign und Twitter arbeiten{#tw-ac-ovv}

Die **Verwalten sozialer Netzwerke (Social Marketing)** ermöglicht die Interaktion mit Ihren Kunden über Twitter. Verwenden Sie diese Funktion, um:

* Nachrichten senden - Verwenden Sie Adobe Campaign Social Marketing, um Nachrichten auf Twitter zu posten. Sie können auch Direktnachrichten an all Ihre Follower senden.

* Neue Kontakte sammeln - Adobe Campaign Social Marketing erleichtert auch den Erwerb neuer Kontakte: Kontaktieren Sie Benutzer und fragen Sie sie, ob sie ihre Profilinformationen teilen möchten. Wenn sie zustimmen, stellt Adobe Campaign die Daten automatisch wieder her, sodass Sie zielgerichtete Kampagnen durchführen und nach Möglichkeit kanalübergreifende Strategien implementieren können.

![](../assets/do-not-localize/speech.png)  Als Benutzer von Managed Cloud Services [Adobe kontaktieren](../start/campaign-faq.md#support) , um Campaign mit Twitter zu verbinden. Die  **Verwalten sozialer Netzwerke (Social Marketing)** -Modul muss in Ihrer Umgebung über das dedizierte Paket installiert werden.


Um Adobe Campaign so zu konfigurieren, dass Tweets in Ihren Twitter-Konten veröffentlicht werden, delegieren Sie Schreibzugriff für diese Konten an Adobe Campaign. Gehen Sie dazu wie folgt vor:

1. Erstellen Sie ein Twitter-Konto
1. Erstellen Sie ein Twitter-Testkonto für den Testversand
1. Erstellen einer Twitter-Anwendung (eine App pro Twitter-Konto)
1. Erstellen Sie einen neuen Dienst für **[!UICONTROL Twitter]** (ein Dienst pro Twitter-Konto)

## Erstellen eines Testkontos auf Twitter {#tw-test-account}

Erstellen Sie zusätzlich zum Twitter-Konto ein privates Twitter-Konto, das zum Senden verwendet werden kann. [Tweet-Testsendungen](../send/twitter.md#send-tw-proofs). Gehen Sie dazu wie folgt vor:

1. Erstellen Sie ein neues Twitter-Konto.
1. Öffnen Sie die **Einstellungen** des Kontos.
1. Gehen Sie zu **Einstellungen und Datenschutz** und **Zielgruppe und Markieren** und setzen Sie ein Häkchen neben der Option **Schütze deine Tweets**. Ihre Tweets und andere Kontoinformationen sind dann nur für Personen sichtbar, die Ihnen folgen.

![](assets/social_tw_test_page.png)

## Erstellen einer Anwendung auf Twitter {#create-an-app-on-twitter}

Erstellen Sie eine Twitter-Anwendung, damit Adobe Campaign Tweets für Ihr Twitter-Konto posten kann.  Gehen Sie dazu wie folgt vor:

1. Melden Sie sich bei Ihrem Twitter-Konto an.
1. Verbinden mit [Twitter-Entwicklerportal](https://developer.twitter.com/en/apps).
1. Auswählen **App erstellen**.
1. Lassen Sie sich von der Twitter-Assistenzkraft durch den Prozess führen.

   Damit Adobe Campaign Tweets in Ihrem Konto posten kann, bearbeiten Sie das **Berechtigungen** Registerkarte der Anwendung und wählen Sie **Lesen und Schreiben** für **Zugriff** Abschnitt. Auf dem Tab **Einstellungen** müssen Sie außerdem das Feld **Callback-URL** leer lassen.

   ![](assets/social_tw_app.png)

>[!NOTE]
>
>Pro Twitter-Konto benötigen Sie eine Anwendung. Daher müssen Sie eine weitere Testanwendung erstellen, um Testsendungen an Ihr Testkonto zu senden.

## Erstellen eines Twitter-Dienstes in Campaign {#create-tw-service}

Um Ihre Campaign-Instanz mit Ihrem Twitter-Konto zu verknüpfen, erstellen Sie eine **Twitter** Dienst und delegieren Sie Schreibzugriff an Campaign.

Um Einstellungen zu erfassen, müssen Sie sowohl auf Ihre Adobe Campaign-Konsole als auch auf Ihr Twitter-Konto zugreifen:

1. Öffnen **Twitter** und von [die Seite &quot;Projekt und Apps&quot;](https://developer.twitter.com/en/portal/projects-and-apps)wählen Sie die zuvor erstellte App aus. Zugriff auf **App-Berechtigungen**.

   ![](assets/social_tw_service.png)

   Bearbeiten Sie die Registerkarte **Schlüssel und Token**, um auf die Details Ihrer Anwendung zuzugreifen.

1. In **Adobe Campaign**, navigieren Sie zum **[!UICONTROL Profile und Zielgruppen]** und wählen Sie die **[!UICONTROL Dienste und Abonnements]** link
1. Erstellen Sie einen neuen Dienst.
1. Wählen Sie den Typ **[!UICONTROL Twitter]**.

   >[!NOTE]
   >
   >Die **[!UICONTROL Abonnements synchronisieren]** ist standardmäßig aktiviert: Diese Option stellt die Liste Ihrer Twitter-Follower automatisch wieder her, damit Sie [Direktnachrichten senden](../send/twitter.md#direct-tw-messages). Die Synchronisierung wird von einer [dedizierter technischer Workflow](#synchro-tw-accounts).

1. Geben Sie den Titel und den internen Namen des Dienstes ein.

   >[!CAUTION]
   >
   >Die **[!UICONTROL Interner Name]** des Dienstes muss mit dem exakten Namen Ihres Twitter-Kontos übereinstimmen. Um Ihre Einstellungen zu überprüfen, können Sie:

   * Wählen Sie die Schaltfläche **[!UICONTROL Speichern]** aus.
   * Wählen Sie in der Übersicht über Dienste die **Twitter** -Dienst, den Sie gerade erstellt haben.
   * Durchsuchen Sie die **[!UICONTROL Twitter-Seite]** tab: Ihr Twitter-Konto angezeigt werden.

1. Standardmäßig werden Follower im Ordner **[!UICONTROL Besucher]** gespeichert. Sie können eine andere Position im **[!UICONTROL Besucherordner]** -Feld. [Weitere Informationen](../send/twitter.md#direct-tw-messages)

1. Kopieren Sie in Ihre Twitter-App den Inhalt der **[!UICONTROL Consumer Key (API Key)]** und **[!UICONTROL Kundengeheimnis (API-Geheimnis)]** und fügen Sie sie in das **[!UICONTROL Consumer key]** und **[!UICONTROL Verbrauchergeheimnis]** Felder Ihrer Kampagne **Twitter** Dienst.

1. Kopieren Sie in Ihre Twitter-App den Inhalt der **[!UICONTROL Zugriffstoken]** und **[!UICONTROL Geheimer Zugriffstoken]** und fügen Sie sie in das **[!UICONTROL Zugriffstoken]** und **[!UICONTROL Zugriffstoken-Geheimnis]** Felder Ihrer Kampagne **Twitter** Dienst.

1. Klicken Sie in der Client-Konsole von Campaign auf **[!UICONTROL Speichern]**. Sie haben jetzt den Schreibzugriff an Adobe Campaign delegiert.


>[!NOTE]
>
>Erstellen einer **Twitter** -Dienst pro Twitter-Konto. Daher müssen Sie einen weiteren Testdienst erstellen, um Testsendungen an Ihr Testkonto zu senden.

## Twitter-Konto synchronisieren {#synchro-tw-accounts}

Die Synchronisierung zwischen Campaign und Twitter wird mithilfe spezieller technischer Workflows verwaltet. Diese Workflows werden im **[!UICONTROL Administration > Betreibung > Technische Workflows > Social Networks verwalten]** Ordner.

Sie werden standardmäßig angehalten: Sie müssen sie manuell starten, wenn Sie mit der Verwendung des **Social Marketing** -Modul.

Die **[!UICONTROL Synchronisierung von twitter-Konten]** Der technische Workflow synchronisiert Twitter-Konten in Adobe Campaign. Ruft die Liste der Twitter-Follower ab, damit Sie ihnen Direktnachrichten senden können. [Weitere Informationen](../send/twitter.md#direct-tw-messages)

Standardmäßig wird dieser Workflow jeden Donnerstag um 7.30 Uhr ausgelöst. Sie können die **[!UICONTROL Ausstehende Aufgabe(n) jetzt ausführen]** -Option, um den Workflow bei der Implementierung dieser Integration jederzeit zu starten.  Sie können auch die Planung bearbeiten, um die Häufigkeit der Auslösung des Workflows zu ändern. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/scheduler.html){target=&quot;_blank&quot;}.

>[!CAUTION]
>
>Um die Liste der Twitter-Abonnenten abzurufen, muss die **[!UICONTROL Synchronisierung von twitter-Konten]** muss für den mit dem Konto verknüpften Dienst aktiviert sein. [Weitere Informationen](#create-tw-service)

Die Follower werden in einer bestimmten Tabelle gespeichert: die Besuchertabelle. Um die Liste der Twitter-Follower anzuzeigen, navigieren Sie zum **[!UICONTROL Profile und Zielgruppen > Besucher]**.

Für jeden Follower speichert Adobe Campaign die folgenden Informationen:

* **[!UICONTROL Origin]**: Name des sozialen Netzwerks (Twitter)
* **[!UICONTROL Externe Kennung]**: Benutzerkennung
* **[!UICONTROL Benutzername]**: Kontoname des Benutzers
* **[!UICONTROL Vollständiger Name]**: Name des Benutzers
* **[!UICONTROL Sprache]**: Benutzersprache
* **[!UICONTROL Anzahl Freunde]**: Anzahl der Follower
* **[!UICONTROL Zeitzone]**: Zeitzone des Benutzers
* **[!UICONTROL Bestätigt]**: Dieses Feld gibt an, ob der Benutzer über ein bestätigtes Twitter-Konto verfügt

Sobald diese Konfiguration abgeschlossen ist, können Sie Tweets in Ihren Twitter-Konten posten und Direktnachrichten an Ihre Follower senden. [Weitere Informationen](../send/twitter.md)
