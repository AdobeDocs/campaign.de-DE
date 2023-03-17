---
product: campaign
title: Arbeiten mit Versandvorlagen
description: Erfahren Sie, wie Sie in Campaign Versandvorlagen erstellen und verwenden
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 3a4de36e-ba24-49ec-8113-f32f12c8ecdd
source-git-commit: edb099b3e882d857752af76798012ccd1c5a99be
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 98%

---

# Arbeiten mit Versandvorlagen{#work-with-delivery-template}

Verwenden Sie Versandvorlagen, um das kreative Erscheinungsbild zu standardisieren und so Kampagnen schneller ausführen und starten zu können.

Eine Vorlage kann systematisch Folgendes enthalten:

* Typologien
* Absender- und Antwortadressen
* Grundlegende Gestaltungsbausteine
* Links zu [Mirrorseiten](../send/mirror-page.md) und Abmelde-Links
* Inhalt, Firmenlogo oder Signatur
* Andere Versandeigenschaften, z. B. die Gültigkeit der Ressource, die Parameter für erneute Versuche oder die Quarantäneeinstellungen.

![](assets/do-not-localize/how-to-video.png) [Entdecken Sie diese Funktion im Video](#delivery-template-video)


## Erstellen einer Vorlage{#create-a-delivery-template}

Um eine Versandvorlage zu erstellen, können Sie eine integrierte Vorlage duplizieren, einen existierenden Versand in eine Vorlage konvertieren oder eine neue Versandvorlage erstellen.

### Duplizieren einer bestehenden Vorlage{#copy-an-existing-template}

Campaign verfügt über eine Reihe integrierter Vorlagen für jeden Kanal: E-Mail, Push, SMS, Briefpost und mehr.

Die einfachste Möglichkeit, eine Versandvorlage zu erstellen, besteht darin, eine integrierte Vorlage zu duplizieren und anzupassen.

Gehen Sie wie folgt vor, um eine Versandvorlage zu duplizieren:

1. Navigieren Sie im Adobe Campaign-Explorer zu **[!UICONTROL Ressourcen > Vorlagen > Versandvorlagen]**.
1. Wählen Sie eine integrierte Versandvorlage aus. Integrierte Vorlagen sind in der Liste fett hervorgehoben.
1. Klicken Sie mit der rechten Maustaste darauf und wählen Sie **[!UICONTROL Duplizieren]**.

   ![](assets/duplicate-built-in-template.png)

1. Definieren Sie die Vorlageneinstellungen und speichern Sie die neue Vorlage.

   ![](assets/delivery-template-new.png)

Die Vorlage wird der Liste der Versandvorlagen hinzugefügt. Sie können sie jetzt bei der Erstellung eines neuen Versands auswählen.

![](assets/select-the-new-template.png)

### Konvertieren eines bestehenden Versands in eine Vorlage {#convert-an-existing-delivery}

Ein Versand kann für neue wiederholte Versandaktionen in eine Vorlage umgewandelt werden.

Gehen Sie wie folgt vor, um einen Versand in eine Vorlage zu konvertieren:

1. Wählen Sie den Versand aus der Versandliste aus, auf die über den Knoten von **[!UICONTROL Kampagnenverwaltung]** des Campaign-Explorers zugegriffen werden kann.

1. Klicken Sie mit der rechten Maustaste und wählen Sie **[!UICONTROL Aktionen > Als Vorlage speichern...]**.

   ![](assets/save-as-template.png)

1. Bearbeiten Sie die Versandeigenschaften und wählen Sie (im Feld **[!UICONTROL Ordner]**) den Ordner aus, in dem die neue Vorlage gespeichert werden soll, sowie den Ordner, in dem die auf dieser Vorlage basierenden Sendungen erstellt werden sollen (im Feld **[!UICONTROL Ausführungsordner]**).

   ![](assets/template-select-folders.png)

### Erstellen einer neuen Vorlage {#create-a-new-template}

>[!NOTE]
>
>Zur Vermeidung von Konfigurationsfehlern wird empfohlen, keine neuen Vorlagen zu erstellen, sondern [eine integrierte Vorlage zu duplizieren](#copy-an-existing-template) und die Eigenschaften je nach Bedarf anzupassen.

Gehen Sie wie folgt vor, um eine Versandvorlage von Grund auf zu konfigurieren:

1. Navigieren Sie zum Ordner **Ressourcen** im Campaign-Explorer und wählen Sie **Vorlagen** und dann **Versandvorlagen** aus.
1. Klicken Sie in der Symbolleiste auf **Neu**, um eine neue Versandvorlage zu erstellen.
1. Legen Sie die **Bezeichnung** und den **internen Namen** des Ordners fest.
1. Speichern Sie Ihre Vorlage und öffnen Sie sie erneut.
1. Passen Sie über die Schaltfläche **Eigenschaften** die Einstellungen an.
1. Bestätigen Sie im Tab **Allgemein** die in den Dropdown-Menüs **Ausführungsordner**, **Ordner** und **Routing** ausgewählten Speicherorte oder ändern Sie sie.
1. Tragen Sie der Kategorie **E-Mail-Parameter** den E-Mail-Betreff und die Zielgruppe ein.
1. Fügen Sie Ihren **HTML-Inhalt** ein, um Ihre Vorlage zu personalisieren. Sie können auch einen Mirrorseite-Link und einen Abmelde-Link angeben.[](../send/mirror-page.md)
1. Wählen Sie den Tab **Vorschau**. Wählen Sie im Dropdown-Menü **Personalisierung testen** die Option **Empfänger** aus, um sich Ihre Vorlage in der Vorschau anzusehen.
1. Klicken Sie auf **Speicher**. Ihre Vorlage kann jetzt in einem Versand verwendet werden.


## Verwenden von Vorlagen{#use-a-delivery-template}

### Erstellen eines Versands aus einer Vorlage{#create-a-delivery-from-a-template}

Um einen Versand auf Basis einer existierenden Vorlage zu erstellen, wählen Sie diese aus der Liste der verfügbaren Versandvorlagen aus.

![](assets/select-the-new-template.png)

Wenn Ihre Vorlage nicht angezeigt wird, klicken Sie auf den Ordner **[!UICONTROL Link auswählen]** rechts neben dem Feld, um Campaign-Ordner zu durchsuchen.

![](assets/browse-templates.png)

Wählen Sie im Feld **[!UICONTROL Ordner]** das gesuchte Verzeichnis aus oder klicken Sie auf das Symbol **[!UICONTROL Unterordner anzeigen]**.

Wählen Sie dann die zu verwendende Versandvorlage aus und klicken Sie auf **[!UICONTROL OK]**.

### Ausführen einer Vorlage {#execute-a-template}

Sie können die Ausführung einer Vorlage direkt über die Vorlagenliste starten, ohne zuvor einen Versand zu erstellen.

Wählen Sie dazu die auszuführende Vorlage aus und klicken Sie mit der rechten Maustaste darauf. Wählen Sie **[!UICONTROL Aktionen > Ausgewählte Versandvorlage ausführen...]** aus.

Sie können auch das Menü **[!UICONTROL Datei > Aktionen > Ausgewählte Versandvorlage ausführen...]** verwenden.

![](assets/execute-delivery-template.png)

Geben Sie die Versandparameter an und klicken Sie auf **[!UICONTROL Senden]**.

Dadurch wird ein Versand im Ordner erzeugt, der mit der Vorlage verknüpft ist. Der Name dieses Versands ist der Name der Versandvorlage, aus der er erstellt wurde.


## Anleitungsvideos {#delivery-template-video}

### Konfigurieren einer Versandvorlage

Das folgende Video zeigt, wie man eine Vorlage für einen Ad-hoc-Versand konfiguriert.

>[!VIDEO](https://video.tv.adobe.com/v/342082?quality=12)

### Einrichten der Eigenschaften von Versandvorlagen

Das folgende Video zeigt, wie die Eigenschaften der Versandvorlage festgelegt werden, und erklärt die einzelnen Eigenschaften im Detail.

>[!VIDEO](https://video.tv.adobe.com/v/338969?quality=12)

### Bereitstellen einer Ad-hoc-Versandvorlage

In diesem Video wird erläutert, wie man eine Ad-hoc-E-Mail-Versandvorlage bereitstellt. Außerdem wird der Unterschied zwischen einem E-Mail-Versand- und einem Versand-Workflow erläutert.

>[!VIDEO](https://video.tv.adobe.com/v/338965?quality=12)

Weitere Anleitungsvideos zu Campaign finden Sie [hier](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
