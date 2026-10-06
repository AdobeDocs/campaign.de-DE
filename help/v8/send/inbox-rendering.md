---
product: campaign
title: Inbox Rendering in Campaign
description: Erfahren Sie, wie Sie E-Mail-Renderings erfassen und in einem speziellen Bericht verfügbar machen
feature: Inbox Rendering, Monitoring, Email Rendering
role: User
version: Campaign v8, Campaign Classic v7
exl-id: a3294e70-ac96-4e51-865f-b969624528ce
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: 2317b1ea-6db4-58c7-851f-717a69c0f5c0
    internal-label: Inbox Rendering
  - id: e519a22f-a06a-42fc-9d09-d78a3ab2c434
    internal-label: Monitoring guidelines
  - id: aef0b685-fc31-54d4-b831-a87fdb9d69de
    internal-label: Email Rendering
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 98%
---
# Rendern des Posteingangs{#inbox-rendering}

## Über Inbox Rendering {#about-inbox-rendering}

Bevor Sie die Schaltfläche **Senden** betätigen, sollten Sie sicherstellen, dass Ihre Nachricht den Empfängern in unterschiedlichen Webclients, Webmails und Geräten optimal dargestellt wird.

Zu diesem Zweck nutzt Adobe Campaign die Web-basierte E-Mail-Test-Software [Litmus](https://litmus.com/email-testing){target="_blank"}, mit der die Darstellung des Posteingangs sichtbar und in einem eigenen Bericht verfügbar gemacht werden kann. So können Sie eine Vorschau der Nachricht in den verschiedenen Kontexten anzeigen, in denen sie empfangen werden kann, und die Kompatibilität mit gängigen Desktops und Anwendungen prüfen.

>[!CAUTION]
>Inbox Rendering ist nicht kompatibel mit dem [wiederkehrenden Versand](../../automation/workflow/recurring-delivery.md).

Litmus ist eine E-Mail-Validierungs- und Vorschau-Anwendung mit großem Funktionsumfang. Sie ermöglicht es E-Mail-Inhaltserstellenden, ihren Nachrichteninhalt in über 70 E-Mail-Renderern als Vorschau anzuzeigen, darunter der Gmail-Posteingang oder der Apple Mail-Client.

Die für das **Inbox Rendering** in Adobe Campaign verfügbaren Clients für Mobilgeräte, SMS und Webmail finden Sie auf der Litmus-[Website](https://litmus.com/email-testing){target="_blank"} (wählen Sie dazu die Option zum **Anzeigen aller E-Mail-Clients** aus).

>[!NOTE]
>
>Zum Testen der Personalisierung in Sendungen ist kein Inbox Rendering nötig. Die Personalisierung kann auch mit Adobe Campaign-Tools, z. B. der **[!UICONTROL Vorschau]** und [Testsendungen](preview-and-proof.md#send-proofs), überprüft werden.

## Über Litmus-Token {#about-litmus-tokens}

Da Litmus ein Dienst eines Drittanbieters ist, wird für jede Nutzung eine Gebühr erhoben. Jedes Mal, wenn eine Person die Litmus-Funktion aufruft, wird ein bestimmter Betrag vom Guthaben abgezogen.

In Adobe Campaign entspricht das Guthaben der Anzahl der verfügbaren Renderings (auch Tokens genannt).

>[!NOTE]
>
>Die Anzahl der verfügbaren Litmus-Token hängt von der von Ihnen erworbenen Campaign-Lizenz ab. Details finden Sie in Ihrem Lizenzvertrag.

Jedes Mal, wenn Sie in einem Versand die Funktion **[!UICONTROL Inbox Rendering]** verwenden, wird die verfügbare Anzahl der Token um jeweils eins verringert.

>[!IMPORTANT]
>
>Token werden für jedes einzelne Rendering abgezogen, und nicht für den gesamten Inbox-Rendering-Bericht.
>
>* Das bedeutet, dass jedes Mal, wenn ein Inbox-Rendering-Bericht erstellt wird, pro E-Mail-Client ein Token abgezogen wird: ein Token für das Rendering in Outlook 2000, einer für das Rendering in Outlook 2010, einer für das Rendering in Apple Mail 9 usw.
>* Wenn Sie für denselben Versand das Inbox Rendering wiederholen, wird die Anzahl der verfügbaren Token nochmals um die Anzahl der erzeugten Renderings reduziert.
>

Die Anzahl der restlichen verfügbaren Token wird im [Inbox-Rendering-Bericht](#inbox-rendering-report) angezeigt.

![](assets/s_tn_inbox_rendering_tokens.png)

Normalerweise wird die Funktion zum Rendern des Posteingangs verwendet, um das HTML-Framework einer neu entworfenen E-Mail zu testen. Für jedes Rendering sind etwa 70 Token erforderlich (je nach der Anzahl der Umgebungen, in denen üblicherweise getestet wird). In einigen Fällen benötigen Sie jedoch möglicherweise mehrere Berichte über das Rendering des Posteingangs, um Ihren Versand vollständig zu testen. Daher könnten mehr Token erforderlich sein, um mehrere Prüfungen durchzuführen.

## Inbox-Rendering-Bericht aufrufen {#accessing-the-inbox-rendering-report}

Nachdem Sie Ihren E-Mail-Versand erstellt und seinen Inhalt sowie die Zielpopulation definiert haben, folgen Sie den unten stehenden Schritten.

Weiterführende Informationen zur Erstellung, Planung und Zielgruppenbestimmung eines Versands finden Sie auf dieser [Seite](defining-the-email-content.md).


1. Wählen Sie in der Symbolleiste des Versands die Schaltfläche **[!UICONTROL Inbox Rendering]** aus.

1. Wählen Sie **[!UICONTROL Analysieren]** aus, um den Aufnahmeprozess zu starten.

   ![](assets/s_tn_inbox_rendering_button.png)

   Ein Testversand wird durchgeführt. Die Rendering-Miniaturansichten können wenige Minuten nach dem Versand der E-Mails in diesem Testversand aufgerufen werden. Weiterführende Informationen dazu finden Sie in [diesem Abschnitt](preview-and-proof.md#send-proofs).

1. Nach dem Absenden erscheint der Testversand in der Versandliste. Doppelklicken Sie darauf.

   ![](assets/s_tn_inbox_rendering_delivery_list.png)

1. Gehen Sie zum Tab **Inbox Rendering** des Testversands.

   ![](assets/s_tn_inbox_rendering_tab.png)

   Der Inbox-Rendering-Bericht wird angezeigt.

## Inbox-Rendering-Bericht {#inbox-rendering-report}

Dieser Bericht zeigt das Rendering des Posteingangs an, so wie es für die Empfängerin bzw. den Empfänger aussieht. Das Rendering kann unterschiedlich aussehen, je nachdem, ob die Empfängerin bzw. der Empfänger den E-Mail-Versand im Browser, auf einem Mobilgerät oder über ein E-Mail-Programm öffnet.

Im oberen Bereich wird in einer grafischen, farbcodierten Darstellung die Aufteilung der Anzahl der empfangenen, unerwünschten (Spam) und nicht empfangenen Nachrichten angezeigt und die Anzahl der Nachrichten, deren Empfang aussteht.

![](assets/s_tn_inbox_rendering_summary.png){width="40%"}

Bewegen Sie den Mauszeiger über das Diagramm, um Informationen zu jeder Farbe aufzurufen. Klicken Sie auf ein Element in der Liste, um die entsprechende Kategorie im Diagramm auszublenden oder anzuzeigen.

Der Hauptteil des Berichts ist in drei Teile unterteilt: **[!UICONTROL Mobilgerät]**, **[!UICONTROL Desktop]** und **[!UICONTROL Webmails]**. Scrollen Sie im Bericht nach unten, um alle in diese drei Kategorien eingeteilten Renderings anzusehen.

![](assets/s_tn_inbox_rendering_report.png)

Klicken Sie auf eine der Karten, um das entsprechende Rendering im Detail anzusehen. Das Rendering wird für das jeweils ausgewählte Empfangsmedium angezeigt.

![](assets/s_tn_inbox_rendering_example.png)
