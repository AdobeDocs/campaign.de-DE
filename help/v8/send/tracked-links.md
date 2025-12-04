---
title: Konfigurieren getrackter Links
description: Erfahren Sie, wie Sie getrackte Links in Sendungen konfigurieren
feature: Monitoring
role: User, Developer
level: Beginner
exl-id: ed88e1d6-c0d5-4a85-9f3e-be670f4bcc10
source-git-commit: 5b23be4cb8f0896d2482e525e416713b1a6c4514
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 85%

---

# Konfigurieren getrackter Links {#how-to-configure-tracked-links}

Sie haben die Möglichkeit, für jeden Versand die Zustellung und Klicks auf enthaltene Links zu verfolgen. Auf diese Weise kann das Verhalten der Nachrichtenempfänger analysiert werden.

>[!NOTE]
>
>Die Links in E-Mail-Inhalten, die eine Personalisierung enthalten, benötigen eine bestimmte Syntax, um nachverfolgt zu werden. Weitere Informationen dazu, wie Sie Links in personalisierbaren E-Mails hinzufügen, die das Tracking unterstützen, finden [&#x200B; in diesem Abschnitt](personalized-links.md).

Das Tracking von Nachrichten ist standardmäßig aktiviert. Um das Tracken von URLs zu personalisieren, gehen Sie folgendermaßen vor:

1. Wählen Sie die Option **[!UICONTROL URLs anzeigen]** im unteren Bereich des Versandassistenten unter dem Nachrichtentext aus.

   ![](assets/s_ncs_user_email_del_display_urls.png)

   Sobald Sie eine URL in der Liste der getrackten URLs markieren, wird sie im Versandinhalt optisch hervorgehoben. (Dies gilt nicht für den Mirrorseite-Link und den Abmelde-Link, die zum Standard-Package der Anwendung gehören.)

   ![](assets/s_ncs_user_email_del_show_urls.png)

1. Aktivieren oder deaktivieren Sie das Tracking für jede in der Nachricht enthaltene URL.

   >[!IMPORTANT]
   >
   >Wenn die URL des Links als Titel verwendet wird, empfiehlt es sich, das Tracking zu deaktivieren, damit die Nachricht nicht wegen des Verdachts auf Phishing zurückgewiesen wird.
   >
   >Wenn Sie z. B. die URL www.adobe.com in die Nachricht einfügen und das Tracking aktivieren, wird der Hyperlink in https://nlt.adobe.net/r/?id=xxxxxx umgewandelt. Dieser wird u. U. von den E-Mail-Programmen der Empfänger als Spam interpretiert.

1. Der Tracking-Titel kann angepasst werden. Doppelklicken Sie auf den zu ändernden Titel und geben Sie den neuen Titel ein.

   >[!NOTE]
   >
   >Die Anpassung der Titel der getrackten URLs dient auch der besseren Lesbarkeit der Tracking-Informationen. Identische URLs oder Titel werden bei der Klick-Zählung zusammengefasst.

1. Sie können den gewünschten Tracking-Modus in der Spalte **[!UICONTROL Tracking]** ändern. Wählen Sie dazu einen neuen Modus wie unten dargestellt aus.

   ![](assets/s_ncs_user_select_tracking_mode.png)

   Für jede einzelne URL können Sie den Tracking-Modus auf einen dieser Werte festlegen.

   * **[!UICONTROL Aktiviert]**: Aktiviert das Tracking dieser URL.
   * **[!UICONTROL Nicht aktiviert]** Deaktiviert das Tracking dieser URL.
   * **[!UICONTROL Immer aktiviert]**: Aktiviert immer das Tracking dieser URL. Diese Eingabe wird gespeichert, sodass das Tracking automatisch aktiviert wird, wenn die URL das nächste Mal in einem Nachrichtentext vorkommt.
   * **[!UICONTROL Nie aktiviert]**: Aktiviert nie das Tracking dieser URL. Diese Eingabe wird gespeichert, sodass das Tracking automatisch deaktiviert wird, wenn die URL das nächste Mal in einem Nachrichtentext vorkommt.
   * **[!UICONTROL Opt-out]**: Diese URL wird als Opt-out-URL behandelt.
   * **[!UICONTROL Mirrorseite]**: Diese URL wird als Mirrorseite behandelt.

1. Zusätzlich können Sie für jede getrackte URL in der Dropdown-Liste der Spalte **[!UICONTROL Kategorie]** eine Kategorie auswählen. Diese Kategorien können in Berichten angezeigt werden, wie z. B. im Bericht **[!UICONTROL URLs und Clickstreams]** (siehe [diesen Abschnitt](../reporting/delivery-reports.md#urls-and-click-streams)). Kategorien werden in einer bestimmten Auflistung definiert: **[!UICONTROL urlCategory]**. Weitere Informationen zum Arbeiten mit Auflistungen finden Sie in [&#x200B; Abschnitt &#x200B;](../config/enumerations.md).

## Best Practices für URL-Trennzeichen {#url-delimiters}

Es wird dringend empfohlen, URLs auf der Registerkarte **[!UICONTROL Textinhalt]** in Trennzeichen einzuschließen, bevor Sie die Tracking-Formel anwenden. Die URL-Trennzeichen, die Sie auf dieser Registerkarte eingeben, werden von Adobe Campaign verwendet, um URLs in Zeichenfolgen zu identifizieren. Sie können diese Trennzeichen-Paare verwenden:

* Runde Klammern ( )
* Eckige Klammern [ ]
* Geschweifte Klammern { }

In diesem Beispiel folgt auf die URL https://www.adobe.com ein Semikolon. Das Semikolon kann von E-Mail-Clients der Empfänger als Teil der URL interpretiert werden. Daher kann der Link beschädigt sein. Um dieses Problem zu vermeiden, können Sie die URL auf eine der folgenden Arten in Trennzeichen einschließen:

* (https://www.adobe.com);
* [https://www.adobe.com];
* {https://www.adobe.com};
