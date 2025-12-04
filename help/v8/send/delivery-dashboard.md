---
title: Überwachen von Sendungen in der Campaign-Benutzeroberfläche
description: Erfahren Sie, wie Sie auf die Liste der Sendungen zugreifen und das Versand-Dashboard verwenden können, um Ihre Sendungen zu überwachen
feature: Monitoring
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1200'
ht-degree: 70%

---

# Überwachen von Sendungen in der Campaign-Benutzeroberfläche {#delivery-dashboard}

Die Überwachung Ihrer Sendungen ist wichtig, um sicherzustellen, dass Ihre Kampagnen effizient sind und Ihre Kunden erreichen. Adobe Campaign bietet Tools, mit denen Sie auf Ihre Sendungen zugreifen und deren Leistung über die Versandliste und das Versand-Dashboard überwachen können.

## Auf die Versandliste zugreifen {#list-of-deliveries}

Auf die Liste aller Sendungen kann im Knoten **[!UICONTROL Kampagnenverwaltung > Sendungen]** zugegriffen werden.

![](assets/deliveries-list.png)

Standardmäßig zeigt die Versandliste die Titel und Status aller im ausgewählten Knoten erstellten Sendungen sowie die Anzahl der zu versendenden, der verarbeiteten und der erfolgreich zugestellten Nachrichten an.

* Die Angabe **[!UICONTROL Zu sendende Nachrichten]** entspricht der Anzahl der Empfänger in der Zielgruppe, nach der Analyse aber vor Absendung.
* In der Spalte **[!UICONTROL Erfolg]** wird die Anzahl der erfolgreich zugestellten Nachrichten angezeigt.
* Die Spalte **[!UICONTROL Verarbeitet]** enthält die Summe der zugestellten und fehlerhaften Nachrichten.

>[!NOTE]
>
>Bei umfangreichen Sendungen können Sie diese Werte aktualisieren. Markieren Sie hierzu den betreffenden Versand und klicken Sie mit der rechten Maustaste darauf. Wählen Sie **[!UICONTROL Aktion > Versand- und Berichtindikatoren neu berechnen]** aus und folgen Sie dem Assistenten, um diese Informationen zu aktualisieren.

## Versand-Dashboard - Übersicht {#delivery-dashboard-overview}

Im **Versand-Dashboard** können Sie Sendungen beobachten und etwaige Probleme beim Nachrichtenversand erkennen.

Sie können Informationen zu einem Versand abrufen und bei Bedarf bearbeiten. Beachten Sie, dass nach Abschluss des Versands der Inhalt der einzelnen Tabs nicht mehr verändert werden kann und nur zur Ansicht zur Verfügung steht.

Die folgenden Informationen können Sie mit den verschiedenen Tabs im Dashboard überwachen:

* [Versandzusammenfassung](#delivery-summary)
* [Versandberichte](#delivery-reports)
* [Versandlogs, Mirrorseiten, Ausschlüsse](#delivery-logs-and-history)
* [Versand-Trackinglogs und -Verlauf](#tracking-logs)
* [Versand-Rendering](#delivery-rendering)
* [Versandverfolgung](#delivery-audit-)

![](assets/s_ncs_user_del_details.png)

**Verwandte Themen:**

* [Ursachen für das Fehlschlagen von Sendungen](delivery-failures.md)
* [Quarantäneverwaltung](quarantines.md)
* [Best Practices beim Versand](../start/delivery-best-practices.md)
* [Verwalten der Zustellbarkeit](about-deliverability.md)

## Versandzusammenfassung {#delivery-summary}

Die Registerkarte **[!UICONTROL Zusammenfassung]** enthält die Merkmale des Versands: Versandstatus, verwendeter Kanal, Absenderinformationen, Betreff, Informationen zur Ausführung.

## Versandberichte {#delivery-reports}

Über den Link **[!UICONTROL Berichte]**, auf den Sie über den Tab **[!UICONTROL Zusammenfassung]** zugreifen können, können Sie eine Berichtserie zur Versandaktion anzeigen: allgemeiner Versandbericht, detaillierter Bericht, Versandbericht, Verteilung von fehlgeschlagenen Nachrichten, Öffnungsrate, Klicks und Transaktionen usw.

Der Inhalt dieses Tabs kann entsprechend Ihren Anforderungen konfiguriert werden. Weitere Informationen zu Versandberichten finden Sie in [diesem Abschnitt](../reporting/delivery-reports.md).

![](assets/delivery-report.png)

## Versandlogs, -verlauf und -ausschlüsse {#delivery-logs-and-history}

Der **[!UICONTROL Versand]**-Tab zeigt die Versandlogs, d. h. die Liste der Zustellversuche, und zeigt für jeden Empfänger den Status des Versands sowie die entsprechenden Nachrichten an.

Sie haben die Möglichkeit, beispielsweise nur fehlgeschlagene Zustellversuche anzuzeigen oder die Empfänger, die in Quarantäne gekommen sind. Klicken Sie hierfür auf die Schaltfläche **[!UICONTROL Filter]** und wählen Sie **[!UICONTROL Nach Status]**. Wählen Sie nun den gewünschten Status aus der Dropdown-Liste aus. Verschiedene Status werden auf der Seite [Versandstatus“ &#x200B;](delivery-statuses.md).

>[!NOTE]
>
>Die Liste mit den Versandlogs kann wie jede andere Liste in Campaign angepasst werden. Sie können beispielsweise eine Spalte hinzufügen, um zu erfahren, welche IP-Adresse die einzelnen E-Mails in einem Versand gesendet hat. Weiterführende Informationen zur Listenanzeige finden Sie in [diesem Abschnitt](../config/ui-settings.md#customize-lists).

![](assets/s_ncs_user_delivery_delivery_tab.png)

Mit dem Link **[!UICONTROL Mirrorseite für diese Nachricht anzeigen...]** können Sie die Mirrorseite für den Inhalt des aus der Liste ausgewählten Versands in einem neuen Fenster anzeigen.

Die Mirrorseite steht nur für Sendungen zur Verfügung, für die HTML-Inhalte definiert wurden. Weitere Informationen hierzu finden Sie unter [Link zur Mirrorseite](mirror-page.md).

![](assets/s_ncs_user_wizard_miror_page_link.png)

## Versand-Trackinglogs und -Verlauf {#tracking-logs}

Auf der Registerkarte **[!UICONTROL Tracking]** wird der Tracking-Verlauf für den vorliegenden Versand angezeigt. Auf dieser Registerkarte werden Tracking-Daten zu den gesendeten Nachrichten angezeigt, einschließlich aller URLs, die von Adobe Campaign getrackt werden. Die Tracking-Daten werden stündlich aktualisiert.

>[!NOTE]
>
>Wenn das Tracking für einen Versand nicht aktiviert ist, wird diese Registerkarte nicht angezeigt.

Die Tracking-Konfiguration erfolgt im entsprechenden Schritt im Versandassistenten. Siehe [Getrackte Links konfigurieren](tracking.md).

Interpretationen der **[!UICONTROL Trackingdaten]** finden Sie in den Versandberichten. Weitere Informationen finden Sie [in diesem Abschnitt](../reporting/delivery-reports.md).

![](assets/s_ncs_user_delivery_tracking_tab.png)

## Rendern des Posteingangs {#delivery-rendering}

Der Tab **[!UICONTROL Inbox Rendering]** ermöglicht es Ihnen, eine Vorschau der Nachricht in den verschiedenen Kontexten anzuzeigen, in denen sie empfangen werden kann, und die Kompatibilität mit gängigen Desktops und Anwendungen zu überprüfen.

So können Sie sicherstellen, dass Ihre Nachricht den Empfängern in unterschiedlichen Webclients, Webmails und Geräten optimal dargestellt wird.

Weitere Informationen zum Inbox Rendering finden Sie auf [dieser Seite](inbox-rendering.md).


## Versandverfolgung {#delivery-audit-}

Der Tab **[!UICONTROL Audit]** enthält das Versandlog und alle Meldungen zu den Testsendungen.

Mit der Schaltfläche **[!UICONTROL Aktualisieren]** können Sie die Daten aktualisieren. Verwenden Sie die Schaltfläche **[!UICONTROL Filter]**, um einen Filter für die Daten zu definieren.

Eventuelle Fehler oder Warnmeldungen werden durch spezifische Symbole hervorgehoben. Siehe [Versandanalyse](delivery-analysis.md).

Eine Unter-Registerkarte listet die durchgeführten **[!UICONTROL Testsendungen]** auf.

![](assets/s_ncs_user_delivery_log_tab.png)

Sie können die Anzeige in diesem Fenster (wie auch in den Registerkarten **[!UICONTROL Versand]** bzw. **[!UICONTROL Tracking]**) anpassen und die Spalten auswählen, die angezeigt werden sollen. Klicken Sie hierfür auf das Symbol **[!UICONTROL Liste konfigurieren]** in der rechten unteren Ecke des Bildschirms. Weiterführende Informationen zur Listenanzeige finden Sie in [diesem Abschnitt](../config/ui-settings.md#customize-lists).

## Synchronisation des Versand-Dashboards {#delivery-dashboard-synchronization}

Im Versand-Dashboard können Sie anhand der verarbeiteten Nachrichten und der Versandlogs überprüfen, ob Ihr Versand erfolgreich durchgeführt wurde.

Manche Indikatoren oder Status können falsch oder nicht aktuell sein. Gehen Sie zur Behebung dieses Problems wie folgt vor:

* Wenn Ihr Versandstatus falsch ist, stellen Sie sicher, dass alle erforderlichen Validierungen für diesen Versand durchgeführt wurden oder dass die technischen Workflows **[!UICONTROL operationMgt]** und **[!UICONTROL deliveryMgt]** fehlerfrei ausgeführt werden.

* Wenn Ihr Versandzähler nicht die Anzahl Ihrer Sendungen anzeigt, lassen Sie die Indikatoren neu berechnen, indem Sie mit der rechten Maustaste im Adobe Campaign-Explorer den entsprechenden Versand und danach **[!UICONTROL Aktionen]** > **[!UICONTROL Sende- und Berichtindikatoren neu berechnen...]** auswählen, um eine neue Synchronisation durchzuführen. Weiterführende Informationen zu Tracking-Indikatoren finden Sie in diesem [Abschnitt](../reporting/delivery-reports.md#tracking-indicators).

Sie können Ihre Sendungen auch mithilfe unterschiedlicher Berichte über das Versand-Dashboard nachverfolgen. Weitere Informationen hierzu finden Sie in [diesem Abschnitt](../reporting/delivery-reports.md).

>[!NOTE]
>
>Als Campaign v8 Managed Cloud Services-Anwender wird die Infrastruktur von Adobe überwacht und verwaltet. Wenn anhaltende Probleme mit Versandindikatoren oder der Dashboard-Synchronisierung auftreten, wenden Sie sich an die Adobe-Kundenunterstützung.

## Fehlerbehebung bei langsamen Sendungen {#troubleshooting-slow-deliveries}

Wenn Ihr Versand länger als üblich dauert, nachdem Sie auf die Schaltfläche **[!UICONTROL Senden]** geklickt haben, überprüfen Sie die folgenden potenziellen Ursachen:

### Probleme mit der IP-Adresse und der Reputation

Einige E-Mail-Anbieter haben Ihre IP-Adressen möglicherweise auf eine Blockierungsliste gesetzt. Überprüfen Sie Ihre Versandlogs (Broadlogs) auf der Registerkarte **[!UICONTROL Versand]** auf Bounce-Nachrichten, die auf Reputationsprobleme hinweisen. Orientierungshilfen zur Reputationsverwaltung finden [&#x200B; im Abschnitt &#x200B;](monitoring-deliverability.md)Zustellbarkeits-Monitoring“.

### Versandgröße und -komplexität

Ihr Versand ist möglicherweise zu groß, um schnell verarbeitet zu werden. Dies kann vorkommen bei:

Umfangreiche JavaScript-Personalisierung, die eine umfangreiche Datenverarbeitung für jede Empfängerin und jeden Empfänger erfordert.

Versand mit einem Gewicht von mehr als 60 KB aufgrund großer HTML-Inhalte, eingebetteter Bilder oder umfassender Personalisierung.

Unter [Best Practices für den Versand](../start/delivery-best-practices.md) erfahren Sie mehr über Inhaltsrichtlinien und Best Practices für die Personalisierung. Die empfohlene maximale Größe beträgt etwa 35 KB, um eine optimale Leistung zu erzielen.

### Systemleistung

Systemprobleme können verhindern, dass Server Sendungen effizient verarbeiten. Wenn Sie Leistungsprobleme vermuten, überprüfen Sie die Versandlogs auf Zeitüberschreitungsfehler oder Kommunikationsprobleme.

>[!NOTE]
>
>Als Campaign v8 Managed Cloud Services-Anwender wird die Überwachung der Serverinfrastruktur von Adobe verwaltet. Wenn beim Versand des Versands anhaltende Leistungsprobleme auftreten, wenden Sie sich mit Ihren Versandlogs an die Adobe-Kundenunterstützung.

