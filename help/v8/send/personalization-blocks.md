---
title: Gestaltungsbausteine
description: Erfahren Sie, wie Sie in Ihrem Nachrichteninhalt integrierte Gestaltungsbausteine verwenden
feature: Personalization
role: User
level: Beginner
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 45%

---


# Gestaltungsbausteine {#personalization-blocks}

Gestaltungsbausteine sind dynamische Inhalte, die ein bestimmtes Rendering enthalten, das Sie in Ihre Sendungen einfügen können. Sie ermöglichen beispielsweise das Einfügen eines Logos, einer bestimmten Anrede oder auch eines Links zur Mirror-Seite.

Um auf personalisierte Inhaltsbausteine zuzugreifen, navigieren Sie zum **[!UICONTROL Ressourcen > Campaign Management > Gestaltungsbausteine]** -Knoten des Explorer. Integrierte Gestaltungsbausteine werden im Abschnitt [diesem Abschnitt](#ootb-personalization-blocks).

Sie können auch neue Bausteine definieren, um die Personalisierung Ihrer Sendungen zu optimieren. [Weitere Informationen](#create-custom-personalization-blocks).

## Einfügen von Gestaltungsbausteinen {#insert-personalization-blocks}

Gehen Sie folgendermaßen vor, um Gestaltungsbausteine in eine Nachricht einzufügen:

1. Klicken Sie im Inhaltseditor des Versand-Assistenten auf das Personalisierungssymbol und wählen Sie die **[!UICONTROL Einschließen]** Menü.
1. Wählen Sie einen Gestaltungsbaustein aus der Liste aus oder klicken Sie auf die Schaltfläche **[!UICONTROL Sonstige...]** auf die vollständige Liste zugreifen.

   ![](assets/perso-content-block.png)

1. Der Gestaltungsbaustein wird in Form eines Scripts eingefügt und in der Personalisierungsphase automatisch an das Empfängerprofil angepasst.
1. Navigieren Sie zum **[!UICONTROL Vorschau]** und wählen Sie einen Empfänger aus, um den Inhalt dieses Bausteins für einen bestimmten Empfänger anzuzeigen.

Sie können auch den Quellcode eines Gestaltungsbausteins im Versandinhalt verwenden, indem Sie die Option **[!UICONTROL HTML-Quellcode des Bausteins einfügen]** auswählen.

## Integrierte Gestaltungsbausteine {#ootb-personalization-blocks}

Integrierte Gestaltungsbausteine:

* **[!UICONTROL Ermöglicht durch Adobe Campaign]**: Hiermit wird das Logo „Ermöglicht durch Adobe Campaign“ eingefügt.
* **[!UICONTROL Formatierungsfunktion für Eigennamen]**: Hiermit wird die JavaScript-Funktion **[!UICONTROL toSmartCase]** generiert, mit der der erste Buchstabe eines jeden Worts in einen Großbuchstaben umgewandelt wird.
* **[!UICONTROL Grußformeln]**: fügt Grußformeln mit dem vollständigen Namen des Empfängers ein, gefolgt von einem Komma. Beispiel: &quot;Hallo John Doe,&quot;.
* **[!UICONTROL Logo einfügen]**: Fügt ein Logo ein, das in den Instanzeinstellungen definiert ist.
* **[!UICONTROL Mirrorseiten-Link]**[: Hiermit wird ein Link zur Mirrorseite eingefügt](mirror-page.md). Das Standardformat lautet: &quot;Wenn Sie diese Nachricht nicht richtig anzeigen können, klicken Sie hier&quot;.
* **[!UICONTROL Mirror-Seiten-URL]**: Hiermit wird die Mirror-Seiten-URL eingefügt, damit Versand-Designer den Link prüfen können.
* **[!UICONTROL Annahme-URL eines Angebots im Einzelmodus]**: Hiermit wird eine URL eingefügt, die es ermöglicht, ein Angebot auf **[!UICONTROL Angenommen]** zu setzen. (Dieser Block ist verfügbar, wenn das Interaction-Modul aktiviert ist)
* **[!UICONTROL Anmeldebestätigung]**: Hiermit wird ein Link eingefügt, mit dem die Anmeldung bestätigt werden kann.
* **[!UICONTROL Anmelde-Link]**: Hiermit wird ein Anmelde-Link eingefügt. Dieser Link wird in den Instanzeinstellungen definiert. Der Standardinhalt lautet: „Klicken Sie hier, um sich zu registrieren.“
* **[!UICONTROL Anmelde-Link (mit Werber)]**: Hiermit wird ein Anmelde-Link eingefügt, über den der Besucher bzw. die Besucherin sowie der Versand identifiziert werden können. Dieser Link wird in den Instanzeinstellungen definiert.
* **[!UICONTROL Anmeldungsseiten-URL]**: Hiermit wird eine Abonnement-URL eingefügt
* **[!UICONTROL Stil von Inhalts-E-Mails]** und **[!UICONTROL Benachrichtigungsstil]**: Code generieren, der eine E-Mail mit vordefinierten HTML-Stilen formatiert.
* **[!UICONTROL Abmelde-Link]**: Fügt einen Link ein, der es ermöglicht, das Abo aller Sendungen zu kündigen (Blockierungsliste). Der standardmäßig verknüpfte Inhalt ist: „Sie erhalten diese Nachricht, da Sie mit ***Name Ihres Unternehmens*** oder einem Tochterunternehmen in Kontakt standen. Um keine Nachrichten mehr von ***Name Ihres Unternehmens*** zu erhalten, klicken Sie hier.“

## Benutzerdefinierte Gestaltungsbausteine erstellen {#create-custom-personalization-blocks}

Über das Personalisierungssymbol können Sie neue personalisierte Inhaltsbausteine definieren.

Gehen Sie wie folgt vor, um einen Gestaltungsbaustein zu erstellen:

1. Navigieren Sie zum **[!UICONTROL Ressourcen > Campaign Management > Gestaltungsbausteine]** Ordner des Campaign-Explorers.
1. Klicken Sie über der Liste der integrierten Blöcke auf **[!UICONTROL Neu]**.

   ![](assets/perso-new-block.png)

1. Konfigurieren Sie den Gestaltungsbaustein:

   ![](assets/perso-custom-block.png)

   * Geben Sie den Titel des Blocks ein. Dieser Titel wird im Einfügefenster der Personalisierungsfelder angezeigt.
   * Wählen Sie eine **Versand** Inhaltstyp.
   * Aktivieren Sie die **[!UICONTROL In den Personalisierungsmenüs sichtbar]** -Option, damit der Baustein über das Einfügesymbol für Personalisierungsfelder zugänglich ist.
   * Aktivieren Sie bei Bedarf die **[!UICONTROL Der Inhalt des Gestaltungsbausteins hängt vom Format ab]** um zwei verschiedene Bausteine für HTML- und Text-E-Mails zu definieren.
   * Geben Sie den Inhalt ein (in HTML, Text, JavaScript usw.) des Gestaltungsbausteins und klicken Sie auf **[!UICONTROL Speichern]**.

Nach der Speicherung ist der neue Gestaltungsbaustein im Versand-Editor verfügbar.

## Tutorial-Video {#personalization-blocks-video}

Im folgenden Video erfahren Sie, wie Sie dynamische Inhaltsbausteine erstellen und diese zur Personalisierung des Inhalts Ihres E-Mail-Versands verwenden.

>[!VIDEO](https://video.tv.adobe.com/v/342088?quality=12)


