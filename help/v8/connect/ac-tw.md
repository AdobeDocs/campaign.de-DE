---
title: Mit Campaign und Twitter arbeiten
description: Erfahren Sie, wie Sie Ihre Campaign-Umgebung mit Twitter integrieren.
role: User, Admin
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 97%

---

# Mit Campaign und Twitter arbeiten{#tw-ac-ovv}

Das Modul **Verwalten sozialer Netzwerke (Social Marketing)** ermöglicht die Interaktion mit Ihren Kunden über Twitter. Verwenden Sie diese Funktion, um:

* Nachrichten zu posten und Direct Messages zu senden – Verwenden Sie Adobe Campaign Social-Media-Marketing, um Nachrichten auf Twitter zu posten. Sie können auch Direktnachrichten an all Ihre Follower senden.

* Neue Kontakte zu sammeln – Mit Adobe Campaign Social-Media-Marketing können Sie auch einfach neue Kontakte über Facebook sammeln: Kontaktieren Sie die Benutzer und fragen Sie sie, ob sie ihre Profilinformationen weitergeben möchten. Wenn sie zustimmen, ruft Adobe Campaign die Daten automatisch ab, sodass Sie zielgerichtete Kampagnen durchführen und kanalübergreifende Strategien implementieren können.

![](../assets/do-not-localize/speech.png) Wenn Sie Benutzender von Managed Cloud Services sind, [kontaktieren Sie Adobe](../start/campaign-faq.md#support), um Campaign mit Twitter zu verbinden. Das Add-on **Verwaltung sozialer Netzwerke (Social-Media-Marketing)** muss über das entsprechende Package in Ihrer Umgebung installiert und das externe Twitter-Konto konfiguriert werden.


Um Adobe Campaign so zu konfigurieren, dass Tweets in Ihren Twitter-Konten veröffentlicht werden, delegieren Sie Schreibzugriff für diese Konten an Adobe Campaign. Gehen Sie dazu folgendermaßen vor:

1. Erstellen Sie ein Twitter-Konto und melden Sie sich für ein Entwicklerkonto an. [Weitere Informationen](#dev-account)
1. (Optional) Erstellen Sie ein Twitter-Testkonto für den Testversand. [Weitere Informationen](#tw-test-account)
1. Erstellen Sie eine Twitter-Anwendung (eine Anwendung pro Twitter-Konto). [Weitere Informationen](#create-an-app-on-twitter)
1. Erstellen Sie einen neuen Service für **[!UICONTROL Twitter]** (ein Service pro Twitter-Konto). [Weitere Informationen](#create-tw-service)
1. Synchronisieren Sie Ihr Twitter-Konto mit Campaign. [Weitere Informationen](#synchro-tw-accounts)

## Twitter-Entwicklerkonto {#dev-account}

Um mit dieser Integration zu beginnen, müssen Sie sich für eine [Twitter-Entwicklerkonto](https://developer.twitter.com){target="_blank"}.

Campaign verwendet die Twitter-API-Version 1.1. Um sie verwenden zu können, müssen Sie über das Entwicklerportal einen erweiterten Zugriff beantragen. Erfahren Sie mehr über den erweiterten Zugriff auf Twitter [auf dieser Seite](https://developer.twitter.com/en/portal/products/elevated){target="_blank"}.

## Erstellen einer Anwendung auf Twitter {#create-an-app-on-twitter}

Nachdem Sie den erweiterten Zugriff erhalten haben, erstellen Sie eine Twitter-Anwendung, damit Adobe Campaign Tweets auf Ihrem Twitter-Konto posten kann. Gehen Sie dazu wie folgt vor:

1. Melden Sie sich bei Ihrem Twitter-Konto an.
1. Stellen Sie eine Verbindung mit dem [Twitter-Entwicklerportal](https://developer.twitter.com/en/apps) her.
1. Wählen Sie **App erstellen** aus.
1. Der Twitter-Assistent führt Sie durch den Prozess.
1. Um Adobe Campaign zu erlauben, Tweets auf Ihrem Konto zu posten, bearbeiten Sie die **Anwendungsberechtigungen** im Abschnitt &quot;Benutzerauthentifizierung einrichten&quot; Ihrer Anwendung. Wählen Sie **Lesen, Schreiben und Direktnachrichten**.

   ![](assets/tw-permissions.png)

1. Wählen Sie im Bereich **Anwendungstyp** **Web-Anwendung, automatisierte Anwendung oder Bot**. Sie können das Feld **Callback-URL** leer lassen und Ihre Konfiguration speichern.

   ![](assets/tw-app-type.png)

1. Gehen Sie zurück zu Ihrem Anwendungs-Dashboard, wählen Sie Ihre Anwendung aus und wechseln Sie zur Registerkarte **Schlüssel und Token**. Wenn unter **Zugriffs-Token und Geheimnis** die Berechtigung **Lesen, Schreiben und Direktnachrichten** nicht aufgeführt wird, müssen Sie das Token und das Geheimnis Ihrer Anwendung neu generieren. Beachten Sie, dass alle Schlüssel und Token bei der Erstellung gespeichert werden müssen. Sie benötigen sie, um Ihren Campaign-Twitter-Service zu konfigurieren.

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>Pro Twitter-Konto benötigen Sie eine Anwendung. Daher müssen Sie eine weitere Testanwendung erstellen, um Testsendungen an Ihr Testkonto durchzuführen.

## Erstellen eines Twitter-Service in Campaign. {#create-tw-service}

Um Ihre Campaign-Instanz mit Ihrem Twitter-Konto zu verknüpfen, erstellen Sie einen **Twitter**-Service und delegieren Sie Schreibzugriff an Campaign.

>[!CAUTION]
>
>Erstellen Sie einen **Twitter**-Service pro Twitter-Konto. Infolgedessen müssen Sie einen weiteren Test-Service erstellen, um Testsendungen an Ihr [Testkonto](#tw-test-account) zu senden.
>
>Jeder **Twitter**-Service muss ebenfalls von Adobe auf Ihrer MID-Instanz erstellt werden. Wenden Sie sich an Ihren Adobe-Support, um Ihre Umgebung konfigurieren zu lassen.

Um Einstellungen vorzunehmen, müssen Sie sowohl auf Ihre Adobe Campaign-Konsole als auch auf die Berechtigungen Ihrer Twitter-Anwendung zugreifen.

1. Gehen Sie in **Adobe Campaign** zur Registerkarte **[!UICONTROL Profile und Zielgruppen]** und klicken Sie auf den Link **[!UICONTROL Services und Abonnements]**.
1. Erstellen Sie einen neuen Service.
1. Wählen Sie den Typ **[!UICONTROL Twitter]**.
1. Geben Sie den Titel und den internen Namen des Services ein.

   >[!CAUTION]
   >
   >Der **[!UICONTROL Interne Name]** des Services muss mit dem Namen des Twitter-Kontos identisch sein.

1. Standardmäßig werden Follower im Ordner **[!UICONTROL Besucher]** gespeichert. Sie können über das Feld **[!UICONTROL Besucherordner]** eine andere Position auswählen. [Weitere Informationen](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >Die Option **[!UICONTROL Abonnements synchronisieren]** ist standardmäßig aktiviert: Diese Option ruft automatisch die Liste Ihrer Twitter-Follower ab, damit Sie ihnen [Direktnachrichten senden](../send/twitter.md#direct-tw-messages) können. Die Synchronisation wird von einem [dedizierten technischen Workflow](#synchro-tw-accounts) ausgeführt.

1. Kopieren Sie in Ihrer Twitter-Anwendung den Inhalt der Felder **API-Schlüssel** und **[API-Schlüsselgeheimnis]** und fügen Sie sie in die Felder **[!UICONTROL Consumer Key]** und **[!UICONTROL Consumer Secret]** Ihres Campaign-**Twitter**-Service ein.

1. Kopieren Sie in Ihrer Twitter-App den Inhalt der Felder **Zugriffs-Token** und **Zugriffs-Token-Geheimnis** und fügen Sie ihn in die Felder **[!UICONTROL Zugriffs-Token]** und **[!UICONTROL Zugriffs-Token-Geheimnis]** Ihres Campaign-**Twitter**-Services ein.

1. Klicken Sie in der Client-Konsole von Campaign auf **[!UICONTROL Speichern]**. Sie haben jetzt den Schreibzugriff an Adobe Campaign delegiert.

Um Ihre Einstellungen zu überprüfen, gehen Sie folgendermaßen vor:

* Bearbeiten Sie den **Twitter**-Service, den Sie gerade erstellt haben.
* Öffnen Sie die Registerkarte **[!UICONTROL Twitter-Seite]**: Ihr Twitter-Konto sollte angezeigt werden.
   ![](assets/tw-page.png)


## Synchronisieren Ihres Twitter-Kontos {#synchro-tw-accounts}

Die Synchronisation zwischen Campaign und Twitter wird mithilfe dedizierter technischer Workflows verwaltet. Diese Workflows werden im Ordner **[!UICONTROL Administration > Produktion > Technische Workflows > Social Marketing]** verwaltet.

Sie werden standardmäßig angehalten: Sie müssen sie manuell starten, wenn Sie mit der Verwendung des Moduls **Social Marketing** beginnen.

Der technische Workflow **[!UICONTROL Synchronisation von Twitter-Konten]** synchronisiert Twitter-Konten in Adobe Campaign. Durch diesen Workflow wird die Liste der Twitter-Follower abgerufen, sodass Sie ihnen Direktnachrichten senden können. [Weitere Informationen](../send/twitter.md#direct-tw-messages)

Standardmäßig wird dieser Workflow jeden Donnerstag um 7.30 Uhr ausgelöst. Sie können die Option **[!UICONTROL Ausstehende Aufgabe(n) jetzt ausführen]** verwenden, um den Workflow bei der Implementierung dieser Integration jederzeit zu starten.  Sie können auch die Planung bearbeiten, um die Häufigkeit der Auslösung des Workflows zu ändern. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/scheduler.html?lang=de){target="_blank"}.

>[!CAUTION]
>
>Um die Liste der Twitter-Abonnenten abzurufen, muss die **[!UICONTROL Synchronisation von Twitter-Konten]** für den mit dem Konto verknüpften Service aktiviert sein. [Weitere Informationen](#create-tw-service)

Die Follower werden in einer spezifischen Tabelle gespeichert: der Besuchertabelle. Um die Liste der Twitter-Follower anzuzeigen, gehen Sie zu **[!UICONTROL Profile und Zielgruppen > Besucher]**.

Für jeden Follower speichert Adobe Campaign die folgenden Informationen:

* **[!UICONTROL Herkunft]**: Twitter
* **[!UICONTROL Externe Kennung]**: Benutzerkennung
* **[!UICONTROL Benutzername]**: Kontoname der/des Benutzenden
* **[!UICONTROL Vollständiger Name]**: Name des/r Benutzenden
* **[!UICONTROL Anzahl Freunde]**: Anzahl der Follower
* **[!UICONTROL Geprüft]**: Dieses Feld gibt an, ob die/der Benutzende über ein bestätigtes Twitter-Konto verfügt

Sobald diese Konfiguration abgeschlossen ist, können Sie Tweets in Ihren Twitter-Konten posten und Direktnachrichten an Ihre Follower senden. [Weitere Informationen](../send/twitter.md)

## Erstellen eines Testkontos auf Twitter {#tw-test-account}

Erstellen Sie zusätzlich zum Twitter-Konto ein privates Twitter-Konto, das zum Senden von [Tweet-Testsendungen](../send/twitter.md#send-tw-proofs) verwendet werden kann. Gehen Sie dazu wie folgt vor:

1. Erstellen Sie ein neues Twitter-Konto.
1. Öffnen Sie die **Einstellungen** des Kontos.
1. Gehen Sie zu **Einstellungen und Datenschutz** und **Zielgruppe und Markieren** und setzen Sie ein Häkchen neben der Option **Schütze deine Tweets**. Ihre Tweets und andere Kontoinformationen sind dann nur für Personen sichtbar, die Ihnen folgen.

![](assets/social_tw_test_page.png)

Konfigurieren Sie Ihre Twitter-Anwendung und Ihren Campaign-Service, um dieses Testkonto wie oben beschrieben zu verwenden.
