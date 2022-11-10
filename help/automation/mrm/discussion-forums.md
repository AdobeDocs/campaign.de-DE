---
product: campaign
title: Diskussionsforen
description: Erfahren Sie, wie Sie Campaign-Diskussionsforen verwenden.
exl-id: c2336507-beea-4ddb-aa8c-1ec591eb5683
source-git-commit: 72fc29c49fca5767133be4a9927b57b3cfb51a14
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 32%

---

# Diskussionsforen{#discussion-forums}

Adobe Campaign-Benutzer können Diskussionsforen verwenden, um Informationen auszutauschen. Die folgenden Elemente verfügen jeweils über ein eigenes Forum: Pläne, Programme, Kampagnen, Marketing-Ressourcen, Simulationen, Lager. Jeder Benutzer hat auch ein persönliches Forum. Alle Diskussionen sind öffentlich, auch in persönlichen Foren.

Benutzer können Foren abonnieren, um per E-Mail über jede gepostete Nachricht informiert zu werden.

## Zugriff auf ein Forum {#accessing-a-forum}

Um auf ein Forum zuzugreifen, navigieren Sie zu einem Dashboard und klicken Sie auf die Schaltfläche **[!UICONTROL Forum]** links oben rechts.

![](assets/mrm-forum-icon.png)

Nachrichten und ihre Antworten werden von neu nach alt angezeigt.

Um einen neuen Thread zu starten, klicken Sie auf die Schaltfläche **[!UICONTROL Diskussion hinzufügen]** in der oberen rechten Ecke. Die **[!UICONTROL Diskussionsforum]** wird angezeigt (siehe unten).

![](assets/mrm-forum-new-thread.png)


Geben Sie den gewünschten Text im Feld **[!UICONTROL Nachricht]** und gegebenenfalls einen Diskussionstitel im Feld **[!UICONTROL Thema]** ein.

Benutzer, die bereits eine Nachricht in diesem Forum veröffentlicht haben, werden standardmäßig benachrichtigt. Sie können einen zusätzlichen Benutzer auswählen, der benachrichtigt werden soll. Um mehrere Benutzer zu benachrichtigen, wählen Sie eine Benutzergruppe aus.

Sie können der Nachricht mithilfe der  **[!UICONTROL Durchsuchen...]** Schaltfläche. Der Anhang wird auch in die Benachrichtigungs-E-Mail aufgenommen. Anhänge dürfen nur einzeln gesendet werden: Um mehrere Dateien zu senden, müssen Sie sie in einer ZIP-Datei komprimieren.

>[!CAUTION]
>
>Wenn die Nachricht gepostet wurde, kann sie nicht mehr geändert oder gelöscht werden.

## Posts im persönlichen Benutzerforum eines Benutzers {#posting-to-the-personal-forum-of-an-operator}

Sie können eine Nachricht im Forum eines Benutzers posten. Persönliche Foren sind öffentlich und alle Benutzer können Ihre Nachricht sehen. Der Benutzer erhält bei jedem Posten in seinem persönlichen Forum eine E-Mail-Benachrichtigung.

Um auf das Benutzerforum zuzugreifen, haben Sie folgende Möglichkeiten:

* Navigieren Sie zum **[!UICONTROL Administration > Zugriffe > Benutzer]** Ordner des Campaign-Explorers, den Benutzer auswählen, um sein Dashboard zu öffnen, und auf die Schaltfläche **[!UICONTROL Forum]** links oben rechts.
* Suchen Sie den Namen des Benutzers in der Benutzeroberfläche von Adobe Campaign (über eine von diesem Benutzer im Forum veröffentlichte Nachricht, der eine Aufgabe zugewiesen wird) und klicken Sie darauf, um auf das Benutzer-Dashboard zuzugreifen.

## Forum abonnieren {#subscribing-to-a-forum}

Wenn Sie ein Forum abonnieren, können Sie alle Diskussionen verfolgen. Nach der Anmeldung erhalten Sie bei jedem Versand einer Nachricht im Forum eine E-Mail-Benachrichtigung.

Um eine Nachricht zu beantworten, klicken Sie in den E-Mail-Textkörper und melden Sie sich dann bei der Adobe Campaign-Web-Oberfläche an.

* Um ein Forum zu abonnieren, klicken Sie auf die Schaltfläche **[!UICONTROL Forum abonnieren]** rechts oberhalb der Diskussionsliste.

   Daraufhin erscheint ein blaues Band, in dem ihr Abonnement bestätigt wird.

* Wenn Sie sich von einem Forum abmelden möchten, klicken Sie auf die Schaltfläche **[!UICONTROL Abmelden]** in dem blauen Band.

* In Ihrem persönlichen Dashboard werden die von Ihnen abonnierten Foren aufgelistet. Klicken Sie auf den Link **[!UICONTROL Forum-Abonnements]**, um die Liste anzuzeigen, und anschließend auf das Forum, auf das Sie zugreifen möchten.

   ![](assets/forum-subscribed.png)


## Fehlerbehebung beim Benachrichtigungsversand {#checking-notification-delivery}

Wenn Benutzer, die ein Forum abonniert haben, keine Benachrichtigungen wie erwartet erhalten:

* Stellen Sie sicher, dass die Benutzer eine E-Mail-Adresse in ihrem Profil angebeben haben.
* Navigieren Sie zum **[!UICONTROL Administration > Betreibung > Technische Workflows > Kampagnenprozesse]** Ordner des Campaign-Explorers und überprüfen Sie die **[!UICONTROL Bearbeitungsvorgänge]** Der Workflow wird ohne Fehler gestartet.
* Überprüfen Sie die Versandlogs:

   * Navigieren Sie auf der Adobe Campaign-Startseite zu **[!UICONTROL Kampagnen > Navigation > Sendungen]**, und öffnen Sie dann die **[!UICONTROL Benachrichtigung zu Diskussionsforen]** -Versand.
   * Navigieren Sie im Campaign-Explorer zu **[!UICONTROL Administration > Betreibung > Automatisch erstellte Objekte > Technische Sendungen > Workflow-Benachrichtigungen]** Klicken Sie auf **[!UICONTROL Benachrichtigungen zu Diskussionsforen]**.
   Im Fenster **[!UICONTROL Benachrichtigungen bezüglich Diskussionsforen]** befinden sich die Versandlogs im Tab **[!UICONTROL Bearbeiten > Versand]**. Überprüfen Sie ebenfalls die Tabs **[!UICONTROL Verfolgung > Protokoll]** und **[!UICONTROL Ausschlussgründe]**.
