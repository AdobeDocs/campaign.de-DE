---
title: Arbeiten mit Campaign und Adobe Analytics
description: Erfahren Sie, wie Sie Campaign und Analytics integrieren.
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 11370fb6-e192-4626-944e-b80a7496e50d
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: ht
source-wordcount: '1284'
ht-degree: 100%

---

# Arbeiten mit Campaign und Adobe Analytics

Sie können Adobe Analytics konfigurieren, um Campaign und Analytics zu integrieren.

Durch diese Integration können Adobe Campaign und Adobe Analytics über das Add-on **Web Analytics Connectors** interagieren. Diese Integration sendet Indikatoren und Attribute von E-Mail-Kampagnen, die von Adobe Campaign bereitgestellt werden, an Adobe Analytics

![](../assets/do-not-localize/speech.png) Als Benutzer von Managed Cloud Services [kontaktieren Sie Adobe](../start/campaign-faq.md#support), um Campaign mit Adobe Experience Cloud-Services und -Lösungen zu verbinden. Das Add-on Web Analytics Connector muss über das dedizierte Paket in Ihrer Umgebung installiert werden.

Mit Adobe Analytics Connector kann Adobe Campaign die Internet-Audience (Web Analytics) messen. Die Web-Analyse-Tools von Adobe Campaign ermöglichen die Weiterleitung von Indikatoren und Kampagnenattributen an Analytics.

Die Anwendungsbereiche der einzelnen Tools sind folgende:

* **Adobe Analytics** markiert die mit Adobe Campaign ausgeführten E-Mail-Kampagnen

* **Adobe Campaign** sendet die Indikatoren und Attribute der Kampagne an den Connector, der sie an das Web-Analyse-Tool übermittelt


>[!CAUTION]
>
>Adobe Analytics Connector ist nicht kompatibel mit Transaktionsnachrichten (Message Center).

Um die Verbindung zwischen Campaign und Analytics einzurichten, müssen Sie die folgenden Schritte vornehmen:

1. [Report Suite in Adobe Analytics erstellen](#report-suite-analytics)
1. [Konfigurieren von Konversionsvariablen und Erfolgsereignissen](#configure-conversion-success)
1. [Externes Konto in Adobe Campaign konfigurieren](#external-account-ac)

## Erstellen Ihrer Analytics-Report Suite {#report-suite-analytics}

Gehen Sie wie folgt vor, um Ihre **[!UICONTROL Report Suite]** in [!DNL Adobe Analytics] zu erstellen:

1. Wählen Sie in [!DNL Adobe Analytics] die Registerkarte **[!UICONTROL Admin]** und klicken Sie dann auf **[!UICONTROL Alle Admin]**.

   ![](assets/analytics_connnector_1.png)

1. Klicken Sie auf **[!UICONTROL Report Suites]**.

   ![](assets/analytics_connnector_2.png)

1. Klicken Sie auf der Seite **[!UICONTROL Report Suite-Manager]** auf **[!UICONTROL Neu erstellen]** und anschließend auf **[!UICONTROL Report Suite]**.

   Eine detaillierte Anleitung zur Erstellung von **[!UICONTROL Report Suites]** finden Sie in [diesem Abschnitt](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/new-report-suite/t-create-a-report-suite.html?lang=de#prerequisites).

   ![](assets/analytics_connnector_3.png)

1. Wählen Sie eine Vorlage aus.

1. Konfigurieren Sie Ihre neue Report Suite anhand folgender Informationen:

   * **[!UICONTROL Report Suite-ID]**
   * **[!UICONTROL Site-Titel]**
   * **[!UICONTROL Zeitzone]**
   * **[!UICONTROL Aufschaltdatum]**
   * **[!UICONTROL Geschätzte Seitenansichten pro Tag]**

   ![](assets/analytics_connnector_4.png)

1. Klicken Sie nach Abschluss der Konfiguration auf **[!UICONTROL Report Suite erstellen]**.

## Konfigurieren von Konversionsvariablen und Erfolgsereignissen {#configure-conversion-success}

Im Anschluss an die Erstellung Ihrer **[!UICONTROL Report Suite]** müssen Sie **[!UICONTROL Konversionsvariablen]** und **[!UICONTROL Erfolgsereignisse]** konfigurieren. Gehen Sie dazu wie folgt vor:

1. Wählen Sie Ihre zuvor konfigurierte **[!UICONTROL Report Suite]** aus.

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Einstellungen bearbeiten]** und wählen Sie **[!UICONTROL Konversion]** > **[!UICONTROL Konversionsvariablen]** aus.

   ![](assets/analytics_connnector_5.png)

1. Klicken Sie auf **[!UICONTROL Neu hinzufügen]**, um die für die Messung der Effektivität der E-Mail-Kampagne erforderlichen Kennungen zu erstellen, also den internen Kampagnennamen (cid) und die ID der iNmsBroadlog-Tabelle (bid).

   Weiterführende Informationen zur Bearbeitung von **[!UICONTROL Konversionsvariablen]** finden Sie in [diesem Abschnitt](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/t-conversion-variables-admin.html?lang=de#admin-tools).

   ![](assets/analytics_connnector_6.png)

1. Klicken Sie abschließend auf **[!UICONTROL Speichern]**.

1. Um **[!UICONTROL Erfolgsereignisse]** zu erstellen, wählen Sie **[!UICONTROL Konversion]** > **[!UICONTROL Erfolgsereignisse]** über die Schaltfläche **[!UICONTROL Einstellungen bearbeiten]** aus.

   ![](assets/analytics_connnector_7.png)

1. Klicken Sie auf **[!UICONTROL Neu hinzufügen]**, um die folgenden **[!UICONTROL Erfolgsereignisse]** zu konfigurieren:

   * **[!UICONTROL Haben geklickt]**
   * **[!UICONTROL Haben geöffnet]**
   * **[!UICONTROL Personenklicks]**
   * **[!UICONTROL Verarbeitet]**
   * **[!UICONTROL Geplant]**
   * **[!UICONTROL Gesendet]**
   * **[!UICONTROL Bounces insgesamt]**
   * **[!UICONTROL Einzelklicks]**
   * **[!UICONTROL Einzelöffnungen]**
   * **[!UICONTROL Abgemeldet]**

   Näheres dazu, wie Sie **[!UICONTROL Erfolgsereignisse]** konfigurieren, finden Sie in [diesem Abschnitt](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/t-success-events.html?lang=de#admin-tools).

   ![](assets/analytics_connnector_8.png)

1. Klicken Sie abschließend auf **[!UICONTROL Speichern]**.

Nachdem Sie Ihre Report Suite konfiguriert haben, müssen Sie die **[!UICONTROL externen Konten]** in Adobe Campaign konfigurieren.

## Konfigurieren Ihres externen Campaign-Kontos {#external-account-ac}

Nun müssen Sie in Adobe Campaign ein externes **[!UICONTROL Web Analytics]**-Konto konfigurieren, um die Synchronisation zwischen den beiden Lösungen zu aktivieren.

Beachten Sie Folgendes: Wenn eine Ihrer **[!UICONTROL Report Suites]**, **[!UICONTROL Konversionsvariablen]** oder eines Ihrer **[!UICONTROL Erfolgsereignisse]** beim Konfigurieren Ihres externen Kontos nicht angezeigt wird, bedeutet dies, dass Sie im **[!UICONTROL Produktprofil]**, das dem Benutzer zugeordnet ist, über keine Berechtigung für diese neu erstellte Komponente verfügen.

Weiterführende Informationen hierzu finden Sie auf der Seite [Produktprofile für Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=de#product-profile-admins).

1. Rufen Sie im Navigationsbaum von Adobe Campaign den Ordner **[!UICONTROL Administration]** > **[!UICONTROL Plattform]** > **[!UICONTROL Externe Konten]** auf und klicken Sie auf **[!UICONTROL Neu]**.

   ![](assets/analytics_connnector_9.png)

1. Wählen Sie in der Dropdown-Liste &quot;Typ&quot; **[!UICONTROL Web Analytics]** und in der Dropdown-Liste **[!UICONTROL Integration]** **[!UICONTROL Adobe Analytics]** aus.

   ![](assets/analytics_connnector_10.png)

1. Klicken Sie auf den Link **[!UICONTROL Konfigurieren]**, der sich neben der Dropdown-Liste **[!UICONTROL Integration]** befindet.

1. Ordnen Sie das externe Konto Ihrer zuvor erstellten Report Suite zu, indem Sie im Fenster **[!UICONTROL Analytics-Integration konfigurieren]** die folgenden Informationen angeben:

   * **[!UICONTROL E-Mail]**
   * **[!UICONTROL IMS Org]**
   * **[!UICONTROL Analytics-Unternehmen]**
   * **[!UICONTROL Report Suite]**


1. Ordnen Sie unter der Kategorie **[!UICONTROL eVars]** die beiden **[!UICONTROL Konversionsvariablen]** zu, die in [!DNL Adobe Analytics] konfiguriert sind.

   ![](assets/analytics_connnector_11.png)

1. Ordnen Sie unter der Kategorie **[!UICONTROL Ereignisse]** die zehn **[!UICONTROL Erfolgsereignisse]** zu, die in [!DNL Adobe Analytics] konfiguriert sind.

1. Klicken Sie abschließend auf **[!UICONTROL OK]**. Adobe Campaign erstellt in der in Analytics zugeordneten **[!UICONTROL Report Suite]** eine **[!UICONTROL Datenquelle]**, **[!UICONTROL berechnete Metriken]**, **[!UICONTROL Remarketing-Segmente]** und **[!UICONTROL Klassifizierungen]**.

   Nach Abschluss der Synchronisation zwischen [!DNL Adobe Analytics] und Adobe Campaign können Sie das Fenster schließen.

1. Die Einstellungen können im Tab **[!UICONTROL Dateneinstellungen]** im Fenster **[!UICONTROL Analytics-Integration konfigurieren]** eingesehen werden.

   Durch Klicken auf die Schaltfläche **[!UICONTROL Synchronisieren]** synchronisiert [!DNL Adobe Campaign] die Namensänderungen, die in [!DNL Adobe Analytics] vorgenommen wurden. Wenn die Komponente in [!DNL Adobe Analytics] gelöscht wird, wird die Komponente in [!DNL Adobe Campaign] durchgestrichen oder es wird für sie die Meldung **Nicht gefunden** angezeigt.

   ![](assets/analytics_connnector_12.png)

   >[!NOTE]
   >
   > In dieser Version von Campaign v8 können keine Segmente hinzugefügt oder entfernt werden.

1. Klicken Sie in Ihrem **[!UICONTROL externen Konto]** auf den Link **[!UICONTROL Formel anreichern]**. Damit können Sie die Formel zur URL-Berechnung ändern, anhand derer die Informationen zur Web Analytics-Tool-Integration (d. h. die Kampagnenkennungen) sowie die Domains der Websites spezifiziert werden, deren Aktivität getrackt werden soll.

   ![](assets/analytics_connnector_13.png)

1. Geben Sie den oder die Namen der betroffenen Webseitendomains ein.

   ![](assets/analytics_connnector_14.png)

1. Klicken Sie auf **[!UICONTROL Weiter]** und stellen Sie sicher, dass die Domainnamen tatsächlich gespeichert wurden.

   ![](assets/analytics_connnector_15.png)

1. Bei Bedarf können Sie die Berechnungsformel überschreiben. Aktivieren Sie dazu das Kontrollkästchen und bearbeiten Sie die Formel direkt im Fenster.

   >[!IMPORTANT]
   >
   >Diese Konfigurationsoption sollte erfahrenen Nutzern vorbehalten bleiben, da Fehler in der Formel dazu führen können, dass der Nachrichtenversand blockiert wird.

1. Im Tab **[!UICONTROL Erweitert]** können Sie fortgeschrittene Parameter ändern.

   * **[!UICONTROL Lebensdauer]**: Ermöglicht nach Ablauf des angegebenen Zeitraums (standardmäßig 180 Tage) die Löschung der Webereignisse, die aus Adobe Campaign mithilfe der technischen Workflows abgerufen wurden.
   * **[!UICONTROL Persistenz]**: Zeitraum (standardmäßig 7 Tage), während dem ein Webereignis (z. B. eine Bestellung) einer Remarketing-Kampagne zugeordnet werden kann.

>[!NOTE]
>
>Bei Verwendung verschiedener Audience-Mess-Tools können Sie bei der Erstellung des externen Kontos in der Dropdown-Liste des Felds **[!UICONTROL Partner]** die Option **[!UICONTROL Sonstige]** auswählen. Da in den Versandeigenschaften jeweils nur ein externes Konto bestimmt werden kann, ist eine Anpassung der Formel für die getrackten URLs notwendig, indem Sie die von Adobe und dem anderen Messtool erwarteten Parameter hinzufügen.

## Technische Workflows der Web-Analyse-Prozesse {#technical-workflows-of-web-analytics-processes}

Der Datenaustausch zwischen Adobe Campaign und Adobe Analytics wird durch vier im Hintergrund ablaufende technische Workflows gesteuert.

Dieser Workflow ist im Campaign Explorer-Navigationsbaum im Ordner **[!UICONTROL Administration]** > **[!UICONTROL Produktion]** > **[!UICONTROL Technische Workflows]** > **[!UICONTROL Web-Analytics-Prozess]** verfügbar.

![](assets/webanalytics_workflows.png)

Der Workflow **[!UICONTROL Übermittlung der Kampagnen-Indikatoren und -Attribute]** sendet die in Adobe Campaign enthaltenen Indikatoren aus E-Mail-Kampagnen über den Adobe Analytics-Connector an Adobe Experience Cloud. Dieser Workflow wird jeden Tag um 4 Uhr ausgelöst. Es kann 24 Stunden dauern, bis die Daten an Analytics gesendet werden.

Bitte beachten Sie, dass dieser Workflow nicht neu gestartet werden sollte, da sonst alle vorherigen Daten erneut gesendet werden, was die Analyseergebnisse verfälschen könnte.

Folgende Indikatoren werden übermittelt:

* **[!UICONTROL Zu sendende Nachrichten]** (@toDeliver)
* **[!UICONTROL Verarbeitet]** (@processed)
* **[!UICONTROL Erfolg]** (@success)
* **[!UICONTROL Öffnungen insgesamt]** (@totalRecipientOpen)
* **[!UICONTROL Empfänger, die geöffnet haben]** (@recipientOpen)
* **[!UICONTROL Gesamtzahl der Empfänger, die geklickt haben]** (@totalRecipientClick)
* **[!UICONTROL Personen, die geklickt haben]** (@personClick)
* **[!UICONTROL Unique-Clicks-Anzahl]** (@recipientClick)
* **[!UICONTROL Abmeldung (Opt-out)]** (@optOut)
* **[!UICONTROL Fehler]** (@error)

>[!NOTE]
>
>Die gesendete Daten sind die Differenz zur letzten Übermittlung, was zu einem negativen Wert in den Metrikdaten führen kann.

Folgende Attribute werden übermittelt:

* **[!UICONTROL Interner Name]** (@internalName)
* **[!UICONTROL Titel]** (@label)
* **[!UICONTROL Titel]** (operation/@label): nur bei installiertem **Campaign**-Package
* **[!UICONTROL Art]** (operation/@nature): nur bei installiertem **Campaign**-Package
* **[!UICONTROL Tag 1]** (webAnalytics/@tag1)
* **[!UICONTROL Tag 2]** (webAnalytics/@tag2)
* **[!UICONTROL Tag 3]** (webAnalytics/@tag3)
* **[!UICONTROL Kontaktdatum]** (scheduling/@contactDate)

## Verfolgen von Sendungen {#tracking-deliveries-in-adobe-campaign}

Damit die Adobe Experience Cloud nach Versand der Nachrichten durch Adobe Campaign die Aktivitäten auf den Webseiten verfolgen kann, muss der entsprechende Connector in den Versandeigenschaften angegeben werden. Gehen Sie wie folgt vor:

1. Öffnen Sie den Versand der zu verfolgenden Kampagne.

   ![](assets/webanalytics_delivery_properties_003.png)

1. Öffnen Sie die Versandeigenschaften.
1. Wählen Sie im Tab **[!UICONTROL Web Analytics]** das zuvor erstellte externe Konto aus. Siehe [Konfigurieren Ihres externen Kontos in Adobe Campaign](#external-account-ac).

   ![](assets/webanalytics_delivery_properties_002.png)

1. Jetzt können Sie Ihre Nachrichten senden und auf den entsprechenden Bericht in Adobe Analytics zugreifen.


**Verwandte Themen**

* [Campaign – Integration von Experience Cloud Triggers](ac-triggers.md)
