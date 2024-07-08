---
title: Konfigurieren von E-Mails mit Adobe Campaign
description: Erfahren Sie, wie Sie E-Mails in Adobe Campaign konfigurieren.
feature: Email
role: User
level: Beginner
exl-id: 36033255-1e75-41c1-9816-126777f7330a
source-git-commit: 2e9c9f8e677233b2906f6ebb8f42dd86afe4e111
workflow-type: ht
source-wordcount: '1278'
ht-degree: 100%

---

# Konfigurieren und Durchführen des Versands {#configure-delivery}

Greifen Sie auf die Versandparameter zu, um weitere Einstellungen zu konfigurieren und festzulegen, wie Ihre Nachrichten gesendet werden. Sie können für den Versand eine [Priorität](#delivery-priority) definieren, [Schübe](#sending-using-multiple-waves) einrichten und den Versand testen. Nach Abschluss dieser Konfiguration können Sie den Versand wie in [diesem Abschnitt](#confirm-delivery) beschrieben bestätigen. Nachrichten werden dann entweder sofort oder basierend auf dem für den Versand festgelegten [Zeitplan](#schedule-delivery-sending) gesendet.

## Festlegen zusätzlicher Parameter {#delivery-additional-parameters}

Vor der Durchführung des Versands können Sie auf der Registerkarte **[!UICONTROL Versand]** die Parameter der Versandeigenschaften definieren.

![](assets/delivery-properties-delivery.png)

### Versandpriorität {#delivery-priority}

Verwenden Sie die Option **[!UICONTROL Versandpriorität]**, um die Versandreihenfolge für Ihre Sendungen zu ändern. Legen Sie dazu eine Prioritätsstufe von **[!UICONTROL Sehr niedrig]** bis **[!UICONTROL Sehr hoch]** fest (der Standardwert ist **[!UICONTROL Normal]**).

### Kontingentgröße {#delivery-batch-quantity}

Mithilfe der Option **[!UICONTROL Kontingentgröße]** können Sie die Anzahl der in einem XML-Versand-Package enthaltenen Nachrichten festlegen. Wenn der Parameter auf „0“ gesetzt ist, werden die Nachrichten automatisch gruppiert. Die Package-Größe wird durch die `<delivery size>/1024`-Berechnung definiert, mit mindestens 8 und maximal 256 Nachrichten pro Package.

>[!IMPORTANT]
>
>Wenn der Versand durch Duplizieren eines existierenden Versands erstellt wird, wird dieser Parameter zurückgesetzt.

### Testen des Versands

Verwenden Sie die Option **[!UICONTROL SMTP-Versand testen]**, um den Versand per SMTP zu testen. Der Versand wird bis zur Verbindung mit dem SMTP-Server verarbeitet, aber nicht gesendet: Für jeden Empfänger des Versands stellt Campaign eine Verbindung mit dem Server des SMTP-Anbieters her, führt den SMTP-Befehl RCPT TO aus und schließt die Verbindung vor dem SMTP-Befehl DATA.

>[!NOTE]
>
>* Diese Option darf bei Mid-Sourcing nicht festgelegt werden.
>
>* Weitere Informationen zur SMTP-Server-Konfiguration finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/additional-configurations/configure-delivery-settings.html?lang=de#smtp-relay){target="_blank"}.

## Versenden in mehreren Schüben {#sending-using-multiple-waves}

Um eine gleichmäßige Auslastung sicherzustellen, können Sie Sendungen in mehrere Schübe unterteilen. Konfigurieren Sie die Anzahl der Schübe und ihre Größe in Bezug auf den gesamten Versand.

### Aktivieren von Schüben {#enable-waves}

Gehen Sie wie folgt vor, um Schübe zu definieren:

1. Öffnen Sie die Versandeigenschaften und navigieren Sie zur Registerkarte **[!UICONTROL Versand]**.
1. Aktivieren Sie die Option **[!UICONTROL In mehreren Schüben versenden]** und klicken Sie auf den Link **[!UICONTROL Definition der Schübe]**.

   ![](assets/delivery-define-waves.png)

### Konfigurieren von Schüben {#config-waves}

>[!NOTE]
>
>Sie können nur die Größe und den zeitlichen Abstand zwischen zwei aufeinanderfolgenden Schüben definieren. Die Empfängerauswahlkriterien für jeden Schub können nicht konfiguriert werden.

Sie können entweder die Größe der einzelnen Schübe definieren oder sie einem Kalender hinzufügen.

* **Definieren Sie die Größe jedes Schubs**. Wenn Sie beispielsweise im entsprechenden Feld **[!UICONTROL 30 %]** eingeben, enthält jeder Schub 30 % der im Versand enthaltenen Nachrichten. Nur der letzte Schub enthält 10 % der Nachrichten.

  Geben Sie im Feld **[!UICONTROL Zeitraum]** die Verzögerung zwischen dem Start zweier aufeinanderfolgender Schübe an. Wenn Sie zum Beispiel **[!UICONTROL 2d]** eingeben, startet der erste Schub sofort, der zweite Schub startet in zwei Tagen, der dritte in vier Tagen usw.

  ![](assets/delivery-waves-size.png)

* **Definieren Sie einen Kalendereintrag für den Versand jedes Schubs**. Beispielsweise beinhaltet der erste Schub 25 % der Gesamtzahl der im Versand enthaltenen Nachrichten und beginnt sofort. Die beiden nächsten Schübe vervollständigen den Versand und starten in Sechs-Stunden-Intervallen.

  Geben Sie in der Spalte **[!UICONTROL Start]** die Verzögerung zwischen dem Start zweier aufeinanderfolgender Schübe an. Geben Sie in der Spalte **[!UICONTROL Größe]** eine feste Zahl oder einen Prozentsatz ein.

  ![](assets/delivery-waves-calendar.png)

### Prüfung der Schub-Planung {#check-waves}

Eine spezifische Typologieregel (**[!UICONTROL Prüfung der Schub-Planung]**) stellt sicher, dass der letzte Schub vor der Versand-Deadline eingeplant ist. Kampagnentypologien und ihre Regeln, die auf der Registerkarte **[!UICONTROL Typologie]** der Versandeigenschaften konfiguriert sind, werden in [diesem Abschnitt](../../automation/campaign-opt/campaign-typologies.md#typology-rules)<!--ref TBC--> vorgestellt.

>[!IMPORTANT]
>
>Achten Sie darauf, dass die letzten Schübe nicht die Versand-Deadline überschreiten, die auf der Registerkarte **[!UICONTROL Gültigkeit]** festgelegt ist. Andernfalls werden einige Nachrichten möglicherweise nicht gesendet. Weitere Informationen zum Gültigkeitszeitraum eines Versands finden Sie in [diesem Abschnitt](delivery-failures.md#valid-period).
>
>Planen Sie beim Konfigurieren der letzten Schübe zudem genügend Zeit für weitere Zustellversuche ein. Nähere Informationen zu weiteren Zustellversuchen finden Sie in [diesem Abschnitt](delivery-failures.md#retries).

### Überwachen von Schüben {#monitor-waves}

Öffnen Sie die Versand-Logs, um Ihre Sendungen zu überwachen. Siehe [diese Seite](send.md).

Die Versand-Logs enthalten die bereits in den verarbeiteten Schüben durchgeführten Sendungen (Status **[!UICONTROL Gesendet]**) sowie die in den restlichen Schüben durchzuführenden Sendungen (Status **[!UICONTROL Ausstehend]**).


### Beispiele für Schübe {#samples-waves}

Im Folgenden finden Sie die häufigsten Anwendungsbeispiele für Schübe.

* **In der Anfangsphase**

  Wenn E-Mails über eine neue Plattform versendet werden, sind ISPs normalerweise misstrauisch gegenüber den neuen IP-Adressen. Das plötzliche Versenden großer Mengen an E-Mails veranlasst ISPs oft dazu, sie als Spam zu qualifizieren.

  Um zu verhindern, dass Ihre Sendungen als Spam eingestuft werden, können Sie das gesendete Volumen schrittweise mithilfe von Schüben erhöhen. Damit gewährleisten Sie eine problemlose Entwicklung in der Anfangsphase und die Verringerung der Anzahl der ungültigen Adressen.

  Verwenden Sie dazu die Option **[!UICONTROL Schübe in einem Kalender definieren]**. Wählen Sie beispielsweise für den ersten Schub 10 %, für den zweiten 15 % usw. aus.

  ![](assets/delivery-waves-ex-ramp-up.png)

* **Kampagnen mit Callcentern**

  Bei telefonischen Treuekampagnen haben Unternehmen oft nur begrenzte Kapazitäten, um Abonnierende anzurufen.

  Mithilfe von Schüben kann die Anzahl der Nachrichten beispielsweise auf 20 pro Tag beschränkt werden, sofern dies der täglichen Verarbeitungskapazität eines Callcenters entspricht.

  Wählen Sie dazu die Option **[!UICONTROL Mehrere Schübe derselben Größe planen]**. Geben Sie **[!UICONTROL 20]** als Schubgröße und **[!UICONTROL 1d]** im Feld **[!UICONTROL Zeitraum]** ein.

  ![](assets/delivery-waves-ex-call-center.png)

## Bestätigen des Versands {#confirm-delivery}

Wenn der Versand konfiguriert wurde und versandbereit ist, stellen Sie sicher, dass Sie vor dem Bestätigen des Sendens die Versandanalyse ausgeführt haben.

Gehen Sie dazu wie folgt vor:

1. Klicken Sie auf **[!UICONTROL Senden]** und wählen Sie die gewünschte Aktion aus.

   * Um den Versand sofort durchzuführen, wählen Sie [**Sendungen schnellstmöglich abschicken**].
   * Um den Versand für einen späteren Zeitpunkt zu planen, wählen Sie **[!UICONTROL Versand terminieren]**. [Weitere Informationen](#schedule-delivery-sending)

1. Klicken Sie auf **[!UICONTROL Analysieren]**. Weiterführende Informationen hierzu finden Sie in [diesem Abschnitt](delivery-analysis.md).

   ![](assets/delivery-send-analyze.png)

1. Klicken Sie abschließend auf **[!UICONTROL Absendung bestätigen]**, um den Versand der Nachrichten zu starten.

   ![](assets/delivery-send-confirm.png)

1. Nun können Sie den Versand-Assistenten schließen und die Durchführung des Versands auf der Registerkarte **[!UICONTROL Versand]** verfolgen (entweder in der Detailansicht des Versands oder in der Versandliste).

   Weitere Informationen hierzu finden Sie in den folgenden Abschnitten:

   * [Sendungen überwachen](send.md)
   * [Ursachen von fehlgeschlagenen Sendungen](delivery-failures.md)

<!--About message tracking-->

## Planen des Versandzeitpunkts {#schedule-delivery-sending}

Sie können das Senden der Nachrichten auf einen späteren Zeitpunkt verschieben, um z. B. den Werbedruck auf eine bestimmte Population zu kontrollieren.

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Senden]** und wählen Sie die Option **[!UICONTROL Versand terminieren]** aus.

1. Geben Sie im Feld **[!UICONTROL Kontaktdatum]** den gewünschten Starttermin an.

   ![](assets/delivery-send-postpone.png)

1. Starten Sie die Versandanalyse und bestätigen Sie den Versand. Der Versand beginnt jedoch erst nach dem im Feld **[!UICONTROL Kontaktdatum]** angegebenen Datum.

   >[!IMPORTANT]
   >
   >Sobald Sie die Analyse gestartet haben, steht das von Ihnen definierte Kontaktdatum fest. Sollten Sie dieses Datum abändern, ist darauf zu achten, die Analyse erneut zu starten, damit Ihre Änderungen berücksichtigt werden.

   ![](assets/delivery-send-scheduled.png)

In der Versandliste erscheint der Versand mit dem Status **[!UICONTROL Ausstehend]**.

Die Terminierung kann auch vorab über die Schaltfläche **[!UICONTROL Planung]** erfolgen.

![](assets/delivery-scheduling-button.png)

Dies bietet die Möglichkeit, den Versand auf einen späteren Zeitpunkt zu verschieben und ihn im Planungskalender zu verzeichnen.

* Bei Wahl der Option **[!UICONTROL Versand planen (keine automatische Ausführung)]** können Sie zudem die Analyse des Versands terminieren.

  In diesem Fall erhält der Versand den Status **[!UICONTROL Zielbestimmung ausstehend]** und die Analyse wird zum angegebenen Zeitpunkt gestartet.

* Bei Wahl der Option **[!UICONTROL Versand planen (automatische Ausführung am geplanten Datum)]** wird nur das Kontaktdatum angegeben.

  Klicken Sie auf die Schaltfläche **[!UICONTROL Senden]**, wählen Sie **[!UICONTROL Versand terminieren]**, starten Sie die Analyse und bestätigen Sie den Versand. Auf diese Weise wird die Analyse durchgeführt und die Zielgruppe vorbereitet. Am angegebenen Stichtag werden die Nachrichten dann automatisch versendet.

Datum und Uhrzeit beziehen sich jeweils auf den aktuellen Benutzer. Die unter dem Eingabefeld des Kontaktdatums situierte Dropdown-Liste **[!UICONTROL Zeitzone]** ermöglicht es, die oberhalb eingegebene Uhrzeit der ausgewählten Zeitzone anzupassen.

Wenn Sie also beispielsweise einen Versand für 8 Uhr MEZ terminieren, wird die Uhrzeit automatisch in die ausgewählte Zeitzone konvertiert:

![](assets/delivery-schedule-time-zone.png)

<!--
## Adjust delivery failure management {#delivery-failure-management}

### Configure retries {#configure-retries}

Temporarily undelivered messages due to a **Soft** or **Ignored** error are subject to an automatic retry. The delivery failure types and reasons are presented in this [section](../../delivery/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

>[!IMPORTANT]
>
>For hosted or hybrid installations, if you have upgraded to the [Enhanced MTA](../../delivery/using/sending-with-enhanced-mta.md), the retry settings in the delivery are no longer used by Campaign. Soft bounce retries and the length of time between them are determined by the Enhanced MTA based on the type and severity of the bounce responses coming back from the message's email domain.

For on-premise installations and hosted/hybrid installations using the legacy Campaign MTA, the central section of the **[!UICONTROL Delivery]** tab for delivery parameters indicates how many retries should be performed the day after the delivery and the minimum delay between retries.

![](assets/s_ncs_user_wizard_retry_param.png)

By default, five retries are scheduled for the first day of the delivery with a minimum interval of one hour spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Validity]** tab (see [Defining validity period](#defining-validity-period)).

### Define the validity period {#define-validity-period}

When the delivery has been launched, the messages (and any retries) can be sent until the delivery deadline. This is indicated in the delivery properties, via the **[!UICONTROL Validity]** tab.

![](assets/s_ncs_user_email_del_valid_period.png)

* The **[!UICONTROL Delivery duration]** field lets you enter the limit for global delivery retries. This means that Adobe Campaign sends the messages beginning on the start date, and then, for messages returning an error only, regular, configurable retries are performed until the validity limit is reached.

  You can also choose to specify dates. To do this, select **[!UICONTROL Explicitly set validity dates]**. In this case, the delivery and validity limit dates also let you specify the time. The current time is used by default, but you can modify this directly in the input field.

  >[!IMPORTANT]
  >
  >For hosted or hybrid installations, if you have upgraded to the [Enhanced MTA](../../delivery/using/sending-with-enhanced-mta.md), the **[!UICONTROL Delivery duration]** setting in your Campaign email deliveries will be used only if set to **3.5 days or less**. If you define a value higher than 3.5 days, it will not be taken into account.

* **Validity limit of resources**: The **[!UICONTROL Validity limit]** field is used for uploaded resources, mainly for the mirror page and images. The resources on this page are valid for a limited time (to save disk space).

  The values in this field can be expressed in the units listed in [this section](../../platform/using/adobe-campaign-workspace.md#default-units).
-->
