---
title: Mit Campaign und Twitter arbeiten
description: Erfahren Sie, wie Sie Ihre Campaign-Umgebung mit Twitter integrieren.
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 100%

---

# Mit Campaign und Twitter arbeiten{#tw-ac-ovv}

Das Modul **Verwalten sozialer Netzwerke (Social Marketing)** ermöglicht die Interaktion mit Ihren Kunden über Twitter. Verwenden Sie diese Funktion, um:

* Nachrichten zu senden – Verwenden Sie Adobe Campaign Social-Media-Marketing, um Nachrichten auf Twitter zu senden. Sie können auch Direktnachrichten an all Ihre Follower senden.

* Neue Kontakte zu sammeln – Mit Adobe Campaign Social-Media-Marketing können Sie auch einfach neue Kontakte über Facebook sammeln: Kontaktieren Sie die Benutzer und fragen Sie sie, ob sie ihre Profilinformationen weitergeben möchten. Wenn sie zustimmen, ruft Adobe Campaign die Daten automatisch ab, sodass Sie zielgerichtete Kampagnen durchführen und kanalübergreifende Strategien implementieren können.

![](../assets/do-not-localize/speech.png)  Wenn Sie Benutzer von Managed Cloud Services sind, [kontaktieren Sie Adobe](../start/campaign-faq.md#support), um Campaign mit Twitter zu verbinden. Das Modul **Verwalten sozialer Netzwerke (Social Marketing)** muss über das dedizierte Package in Ihrer Umgebung installiert werden.


Um Adobe Campaign so zu konfigurieren, dass Tweets in Ihren Twitter-Konten veröffentlicht werden, delegieren Sie Schreibzugriff für diese Konten an Adobe Campaign. Gehen Sie dazu wie folgt vor:

1. Erstellen Sie ein Twitter-Konto.
1. Erstellen Sie ein Twitter-Testkonto für den Testversand.
1. Erstellen Sie eine Twitter-Anwendung (eine App pro Twitter-Konto).
1. Erstellen Sie einen neuen Service für **[!UICONTROL Twitter]** (ein Service pro Twitter-Konto).

## Erstellen eines Testkontos auf Twitter {#tw-test-account}

Erstellen Sie zusätzlich zum Twitter-Konto ein privates Twitter-Konto, das zum Senden von [Tweet-Testsendungen](../send/twitter.md#send-tw-proofs) verwendet werden kann. Gehen Sie dazu wie folgt vor:

1. Erstellen Sie ein neues Twitter-Konto.
1. Öffnen Sie die **Einstellungen** des Kontos.
1. Gehen Sie zu **Einstellungen und Datenschutz** und **Zielgruppe und Markieren** und setzen Sie ein Häkchen neben der Option **Schütze deine Tweets**. Ihre Tweets und andere Kontoinformationen sind dann nur für Personen sichtbar, die Ihnen folgen.

![](assets/social_tw_test_page.png)

## Erstellen einer Anwendung auf Twitter {#create-an-app-on-twitter}

Erstellen Sie eine Twitter-Anwendung, damit Adobe Campaign Tweets für Ihr Twitter-Konto posten kann.  Gehen Sie dazu wie folgt vor:

1. Melden Sie sich bei Ihrem Twitter-Konto an.
1. Stellen Sie eine Verbindung mit dem [Twitter-Entwicklerportal](https://developer.twitter.com/en/apps) her.
1. Wählen Sie **App erstellen** aus.
1. Der Twitter-Assistent führt Sie durch den Prozess.

   Damit die Anwendung Adobe Campaign erlaubt, Tweets an Ihr Konto zu senden, rufen Sie den Tab **Berechtigungen** der Anwendung auf und wählen Sie die Option **Lesen und Schreiben** im Bereich **Zugriff**. Auf dem Tab **Einstellungen** müssen Sie außerdem das Feld **Callback-URL** leer lassen.

   ![](assets/social_tw_app.png)

>[!NOTE]
>
>Pro Twitter-Konto benötigen Sie eine Anwendung. Daher müssen Sie eine weitere Testanwendung erstellen, um Testsendungen an Ihr Testkonto durchzuführen.

## Erstellen eines Twitter-Service in Campaign. {#create-tw-service}

Um Ihre Campaign-Instanz mit Ihrem Twitter-Konto zu verknüpfen, erstellen Sie einen **Twitter**-Service und delegieren Sie Schreibzugriff an Campaign.

Um in die Einstellungen zu gelangen, müssen Sie sowohl auf Ihre Adobe Campaign-Konsole als auch auf Ihr Twitter-Konto zugreifen:

1. Öffnen Sie **Twitter** und wählen Sie auf der Seite [Projekt und Apps](https://developer.twitter.com/en/portal/projects-and-apps) die zuvor erstellte App aus. Greifen Sie auf **App-Berechtigungen** zu.

   ![](assets/social_tw_service.png)

   Bearbeiten Sie die Registerkarte **Schlüssel und Token**, um auf die Details Ihrer Anwendung zuzugreifen.

1. Gehen Sie in **Adobe Campaign** zur Registerkarte **[!UICONTROL Profile und Zielgruppen]** und klicken Sie auf den Link **[!UICONTROL Services und Abonnements]**.
1. Erstellen Sie einen neuen Service.
1. Wählen Sie den Typ **[!UICONTROL Twitter]**.

   >[!NOTE]
   >
   >Die Option **[!UICONTROL Abonnements synchronisieren]** ist standardmäßig aktiviert: Diese Option ruft automatisch die Liste Ihrer Twitter-Follower ab, damit Sie ihnen [Direktnachrichten senden](../send/twitter.md#direct-tw-messages) können. Die Synchronisation wird von einem [dedizierten technischen Workflow](#synchro-tw-accounts) ausgeführt.

1. Geben Sie den Titel und den internen Namen des Services ein.

   >[!CAUTION]
   >
   >Der **[!UICONTROL Interne Name]** des Services muss mit dem Namen des Twitter-Kontos identisch sein.

   Um Ihre Einstellungen zu überprüfen, können Sie:

   * Auf den Button **[!UICONTROL Speichern]** klicken.
   * In der Übersicht der Services auf den soeben erstellten **Twitter**-Service klicken.
   * Die Registerkarte **[!UICONTROL Twitter-Seite]** durchsuchen: Ihr Twitter-Konto sollte angezeigt werden.

1. Standardmäßig werden Follower im Ordner **[!UICONTROL Besucher]** gespeichert. Sie können über das Feld **[!UICONTROL Besucherordner]** eine andere Position auswählen. [Weitere Informationen](../send/twitter.md#direct-tw-messages)

1. Kopieren Sie aus Ihrer Twitter-App den Inhalt der Felder **[!UICONTROL Consumer Key (API Key)]** und **[!UICONTROL Consumer Secret (API Secret)]** und fügen Sie ihn in die Felder **[!UICONTROL Consumer Key]** und **[!UICONTROL Consumer Secret]** Ihres Campaign-**Twitter**-Services ein.

1. Kopieren Sie in Ihrer Twitter-App den Inhalt der Felder **[!UICONTROL Zugriffs-Token]** und **[!UICONTROL Zugriffs-Token-Geheimnis]** und fügen Sie ihn in die Felder **[!UICONTROL Zugriffs-Token]** und **[!UICONTROL Zugriffs-Token-Geheimnis]** Ihres Campaign-**Twitter**-Services ein.

1. Klicken Sie in der Client-Konsole von Campaign auf **[!UICONTROL Speichern]**. Sie haben jetzt den Schreibzugriff an Adobe Campaign delegiert.


>[!NOTE]
>
>Erstellen Sie einen **Twitter**-Service pro Twitter-Konto. Daher müssen Sie einen weiteren Test-Service erstellen, um Testsendungen an Ihr Testkonto durchzuführen.

## Synchronisieren Ihres Twitter-Kontos {#synchro-tw-accounts}

Die Synchronisation zwischen Campaign und Twitter wird mithilfe dedizierter technischer Workflows verwaltet. Diese Workflows werden im Ordner **[!UICONTROL Administration > Produktion > Technische Workflows > Social Marketing]** verwaltet.

Sie werden standardmäßig angehalten: Sie müssen sie manuell starten, wenn Sie mit der Verwendung des Moduls **Social Marketing** beginnen.

Der technische Workflow für die **[!UICONTROL Twitter-Konto-Synchronisation]** synchronisiert Twitter-Konten in Adobe Campaign. Durch diesen Workflow wird die Liste der Twitter-Follower abgerufen, sodass Sie ihnen Direktnachrichten senden können. [Weitere Informationen](../send/twitter.md#direct-tw-messages)

Standardmäßig wird dieser Workflow jeden Donnerstag um 7.30 Uhr ausgelöst. Sie können die Option **[!UICONTROL Ausstehende Aufgabe(n) jetzt ausführen]** verwenden, um den Workflow bei der Implementierung dieser Integration jederzeit zu starten.  Sie können auch die Planung bearbeiten, um die Häufigkeit der Auslösung des Workflows zu ändern. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/scheduler.html?lang=de){target=&quot;_blank&quot;}.

>[!CAUTION]
>
>Um die Liste der Twitter-Abonnenten abzurufen, muss die **[!UICONTROL Synchronisation von Twitter-Konten]** für den mit dem Konto verknüpften Service aktiviert sein. [Weitere Informationen](#create-tw-service)

Die Follower werden in einer spezifischen Tabelle gespeichert: der Besuchertabelle. Um die Liste der Twitter-Follower anzuzeigen, gehen Sie zu **[!UICONTROL Profile und Zielgruppen > Besucher]**.

Für jeden Follower speichert Adobe Campaign die folgenden Informationen:

* **[!UICONTROL Herkunft]**: Name des sozialen Netzwerks (Twitter)
* **[!UICONTROL Externe Kennung]**: Benutzerkennung
* **[!UICONTROL Benutzername]**: Kontoname des Benutzers
* **[!UICONTROL Vollständiger Name]**: Name des Benutzers
* **[!UICONTROL Sprache]**: Benutzersprache
* **[!UICONTROL Anzahl Freunde]**: Anzahl der Follower
* **[!UICONTROL Zeitzone]**: Zeitzone des Benutzers
* **[!UICONTROL Bestätigt]**: Dieses Feld gibt an, ob der Benutzer über ein bestätigtes Twitter-Konto verfügt

Sobald diese Konfiguration abgeschlossen ist, können Sie Tweets in Ihren Twitter-Konten posten und Direktnachrichten an Ihre Follower senden. [Weitere Informationen](../send/twitter.md)
