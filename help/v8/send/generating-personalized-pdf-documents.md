---
product: campaign
title: Erstellen von personalisierten PDF-Dokumenten
description: Erfahren Sie, wie Sie personalisierte PDF-Dokumente erstellen
feature: Personalization
role: User
version: Campaign v8, Campaign Classic v7
exl-id: f4a329e3-70d2-43cd-a04a-0bbd5e3ca390
source-git-commit: 0868fa6522f622e9fa18d4acc3606f690550e5b6
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 84%

---

# Erstellen von personalisierten PDF-Dokumenten{#generating-personalized-pdf-documents}

## Über variable PDF-Dateien {#about-variable-pdf-documents}

Mit Adobe Campaign können Sie aus LibreOffice- oder Microsoft Word-Dokumenten variable PDF-Dokumente für E-Mail-Anhänge erstellen.

Unterstützt werden die Formate &quot;.docx&quot;, &quot;.doc&quot; und &quot;.odt&quot;.

Um die entsprechenden Dokumente zu personalisieren, stehen Ihnen die gleichen JavaScript-Funktionen zur Verfügung, die auch bei E-Mails Verwendung finden.

Sie müssen die Option **[!UICONTROL Der Inhalt der Datei wird beim Versand jeder Nachricht personalisiert und in PDF konvertiert“]**. Diese Option ist verfügbar, wenn Sie die Datei an die Versand-E-Mail anhängen. Weitere Informationen zum Anhängen einer berechneten Datei finden Sie in der [Dokumentation zu Campaign v8](attaching-files.md).

Die Erzeugung dynamischer Tabellen und der Einschluss von Bildern über URLs wird nachfolgend dargestellt.

## Erzeugen von dynamischen Tabellen {#generating-dynamic-tables}

Gehen Sie wie folgt vor, um eine dynamische Tabelle zu erzeugen:

* Erstellen Sie eine Tabelle mit drei Zeilen und einer beliebigen Anzahl an Spalten. Konfigurieren Sie das Layout (Rahmen usw.).
* Bewegen Sie den Cursor auf die Tabelle und klicken Sie im Menü auf **[!UICONTROL Tabelle > Tabelleneigenschaften]**. Geben Sie im **[!UICONTROL Tabelle]**-Tab einen mit **NlJsTable** beginnenden Titel ein.
* Definieren Sie in der ersten Zelle der ersten Zeile eine Schleife (z. B. &quot;for&quot;), die die Iteration der Werte, die Sie anzeigen möchten, ermöglicht.
* Fügen Sie in jeder Zelle der zweiten Zeile die Skripts ein, die die anzuzeigenden Werte ausgeben.
* Schließen Sie die Schleife in der dritten und letzten Zeile der Tabelle.

## Einfügen externer Bilder {#inserting-external-images}

Sie haben die Möglichkeit, ein Dokument mit Bildern zu personalisieren, deren URL in einem Feld des Empfängerprofils gespeichert ist.

Konfigurieren Sie hierzu einen Gestaltungsbaustein und verweisen Sie auf diesen im angehängten Dokument.

**Anwendungsbeispiel: Einfügen eines personalisierten Logos in Abhängigkeit vom Herkunftsland des Empfängers**

**1. Schritt: Erstellung des Anhangs**

* Fügen Sie den Verweis auf den Gestaltungsbaustein ein: **&lt;%@ include view=&quot;Baustein-Name&quot; %>**.
* Fügen Sie den (eventuell personalisierten) Inhalt in den Nachrichten-Textkörper ein.

**2. Schritt: Erstellung des Gestaltungsbausteins**

* Gehen Sie in das Menü **[!UICONTROL Ressourcen > Kampagnenverwaltung > Gestaltungsbausteine]**.
* Erstellen Sie einen neuen Baustein mit dem Titel &quot;Mein Logo&quot; und dem internen Namen &quot;Mein_Logo&quot;.
* Klicken Sie auf **[!UICONTROL Link Erweiterte Parameter…]** und aktivieren Sie dann die Option **[!UICONTROL Der Inhalt des Bausteins ist in einem Anhang enthalten]**. Auf diese Weise können Sie die Definition des Gestaltungsbausteins direkt in den Inhalt der OpenOffice-Datei kopieren.

  ![](assets/s_ncs_pdf_bloc_option.png)

  Innerhalb des Gestaltungsbausteins sind zwei Deklarierungstypen zu unterscheiden:

   * Der Adobe Campaign-Code der Personalisierungsfelder: Die Zeichen „Kleiner als“ und „Größer als“ müssen durch eine Escape-Sequenz ersetzt werden (`&lt;` und `&gt;`).
   * Der OpenOffice-XML-Code wird vollständig in das OpenOffice-Dokument kopiert.

Im Beispiel weist der Gestaltungsbaustein folgendes Format auf:

```
<% if (recipient.country.label == "Germany") { %>
<draw:frame svg:width="4cm" svg:height="3cm">
<draw:image xlink:href=https://..../logo_germany.png />
</draw:frame>
<% } else
if (recipient.country.label == "USA")
{ %>
<draw:frame svg:width="4cm" svg:height="3cm">
<draw:image xlink:href=https://..../logo_USA.png />
</draw:frame>
<% } %>
```

Die Personalisierung bezüglich des Herkunftslands des Empfängers wurde korrekt konfiguriert:
