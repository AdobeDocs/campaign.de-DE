---
product: campaign
title: SpamAssassin
description: Erfahren Sie, wie Sie mit SpamAssassin die Erkennung von Spam-E-Mails einrichten
feature: Email, Deliverability
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8be6836d-f7dc-4199-b2b2-b6a9cac9d162
source-git-commit: 96f1518f252be7ffa27ba8157b8a090bf4d4510d
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 92%

---

# SpamAssassin{#spamassassin}

Adobe Campaign bietet die Möglichkeit der Nutzung von [SpamAssassin](https://spamassassin.apache.org){target="_blank"}, einem Drittanbieterdienst zum Filtern von E-Mail-Spam. Mit diesem Filterprogramm wird E-Mails eine Punktzahl zugeordnet. Diese gibt Auskunft über die Wahrscheinlichkeit, von Anti-Spam-Programmen als unerwünscht eingestuft zu werden.

SpamAssassin nutzt eine Vielzahl von Spam-Erkennungs-Methoden, darunter:

* Spam-Erkennung auf der Basis des DNS und der unscharfen Prüfsumme
* Bayes&#39;sche Filtertechnologie
* Externe Programme
* Blockierungslisten
* Online-Datenbanken

>[!NOTE]
>
>SpamAssassin muss auf dem Adobe Campaign-Anwendungs-Server installiert und konfiguriert werden. Weitere Informationen erhalten Sie von Ihrem Adobe-Support-Mitarbeiter.
>
>Die Regeln, mit denen bestimmt wird, ob ein Element Spam ist oder nicht, werden über SpamAssassin verwaltet und können von einem Administrator mit den entsprechenden Berechtigungen bearbeitet werden.

## Verwenden von SpamAssassin in Campaign {#using-spamassassin}

Nachdem Sie Ihren E-Mail-Versand erstellt und seinen Inhalt definiert haben, folgen Sie den unten stehenden Schritten, um die Risiken auszuwerten.

Weiterführende Informationen zum Erstellen und Entwerfen eines Versands finden Sie auf dieser [Seite](defining-the-email-content.md).


1. Gehen Sie zum Tab **[!UICONTROL Vorschau]**.
1. Wählen Sie einen Empfänger aus, um Ihren Versand in der Vorschau zu betrachten.

   ![](assets/s_tn_del_preview_spamassassin_recipient.png)

   >[!NOTE]
   >
   >Wenn Sie keinen Empfänger auswählen, kann die Anti-Spam-Prüfung nicht durchgeführt werden.

1. In einem Warnhinweis wird das Testergebnis angezeigt. Wenn ein hohes Risiko besteht, wird der folgende Warnhinweis angezeigt:

   ![](assets/s_tn_del_preview_spamassassin_ko.png)

1. Wählen Sie den Link **[!UICONTROL Details...]** neben dem Warnhinweis aus.
1. Wählen Sie den Tab **[!UICONTROL Anti-Spam-Prüfung]** aus.
1. Gehen Sie zum Bereich **[!UICONTROL Punktzahl/Regel/Beschreibung]**, um sich die Gründe für das Risiko anzusehen.

   ![](assets/s_tn_del_msg_spamassassin_ko.png)

>[!NOTE]
>
>Jedes Mal, wenn Sie **[!UICONTROL Anti-Spam-Prüfung]** auswählen, wird der SpamAssassin-Dienst aufgerufen und die Nachricht wird erneut analysiert. Achten Sie darauf, dass Sie den Inhalt ändern, bevor Sie die Anti-Spam-Prüfung erneut durchführen.
