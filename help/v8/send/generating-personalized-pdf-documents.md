---
product: campaign
title: Erstellen von personalisierten PDF-Dokumenten
description: Erfahren Sie, wie Sie personalisierte PDF-Dokumente erstellen
feature: Personalization
role: User
version: Campaign v8, Campaign Classic v7
exl-id: f4a329e3-70d2-43cd-a04a-0bbd5e3ca390
TQID: https://experienceleague.adobe.com/qfSKBHeQUkAYJb-PSeTxYMxGp-WicmITitT9qh8tHBs
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 87e77fcdb7c97ed903ea37a23fb2670aca904f59
workflow-type: tm+mt
source-wordcount: 538
ht-degree: 86%

---

# Erstellen von personalisierten PDF-Dokumenten{#generating-personalized-pdf-documents}

## Über variable PDF-Dateien {#about-variable-pdf-documents}

Mit Adobe Campaign können Sie aus LibreOffice- oder Microsoft Word-Dokumenten variable PDF-Dokumente für E-Mail-Anhänge erstellen.

Unterstützt werden die Formate &quot;.docx&quot;, &quot;.doc&quot; und &quot;.odt&quot;.

Um die entsprechenden Dokumente zu personalisieren, stehen Ihnen die gleichen JavaScript-Funktionen zur Verfügung, die auch bei E-Mails Verwendung finden.

Sie müssen die Option **[!UICONTROL Dateiinhalt wird zum Zeitpunkt des Versand für jede Nachricht personalisiert und in PDF konvertiert]** aktivieren. Diese Option ist verfügbar, wenn Sie die Datei an den E-Mail-Versand anhängen. Weitere Informationen zum Anhängen einer berechneten Datei finden Sie in der [Dokumentation zu Campaign v8](attaching-files.md).

Die Erzeugung dynamischer Tabellen und der Einschluss von Bildern über URLs wird nachfolgend dargestellt.

## Erzeugen von dynamischen Tabellen {#generating-dynamic-tables}

Gehen Sie wie folgt vor, um eine dynamische Tabelle zu erzeugen:

* Erstellen Sie eine Tabelle mit drei Zeilen und einer beliebigen Anzahl an Spalten. Konfigurieren Sie das Layout (Rahmen usw.).
* Bewegen Sie den Cursor auf die Tabelle und klicken Sie im Menü auf **[!UICONTROL Tabelle > Tabelleneigenschaften]**. Geben Sie im **[!UICONTROL Tabelle]**-Tab einen mit **NlJsTable** beginnenden Titel ein.
* Definieren Sie in der ersten Zelle der ersten Zeile eine Schleife (z. B. &quot;for&quot;), die die Iteration der Werte, die Sie anzeigen möchten, ermöglicht.
* Fügen Sie in jeder Zelle der zweiten Zeile die Skripts ein, die die anzuzeigenden Werte ausgeben.
* Schließen Sie die Schleife in der dritten und letzten Zeile der Tabelle.

## Einfügen externer Bilder {#inserting-external-images}

>[!IMPORTANT]
>
>Version 8.9.3 enthält eine Aktualisierung der externen URL-Zulassungsliste. Stellen Sie sicher, dass die Domains, die für externe Bilder in Ihren Anlagen verwendet werden, zur genehmigten Zulassungsliste Ihrer Instanz hinzugefügt werden, damit Ressourcen ohne Unterbrechung weiter geladen werden. Verwenden Sie als Campaign-Admin das Control Panel, um URLs auf der Zulassungsliste hinzuzufügen und zu verwalten. Anweisungen finden [&#x200B; unter „Hinzufügen &#x200B;](https://experienceleague.adobe.com/de/docs/control-panel/using/instances-settings/url-permissions){target="_blank"} URL-Berechtigungen“.

Sie haben die Möglichkeit, ein Dokument mit Bildern zu personalisieren, deren URL in einem Feld des Empfängerprofils gespeichert ist.

Konfigurieren Sie hierzu einen Gestaltungsbaustein und verweisen Sie auf diesen im angehängten Dokument.

**Anwendungsbeispiel: Einfügen eines personalisierten Logos in Abhängigkeit vom Herkunftsland des Empfängers**

**1. Schritt: Erstellung des Anhangs**

* Fügen Sie den Verweis auf den Gestaltungsbaustein ein: **&lt;%@ include view=&quot;Baustein-Name&quot; %>**.
* Fügen Sie den (eventuell personalisierten) Inhalt in den Nachrichten-Textkörper ein.

**2. Schritt: Erstellung des Gestaltungsbausteins**

* Gehen Sie in das Menü **[!UICONTROL Ressourcen > Kampagnenverwaltung > Gestaltungsbausteine]**.
* Erstellen Sie einen neuen Baustein mit dem Titel &quot;Mein Logo&quot; und dem internen Namen &quot;Mein_Logo&quot;.
* Klicken Sie auf den Link **[!UICONTROL Erweiterte Parameter…]** und aktivieren Sie die Option **[!UICONTROL Der Inhalt des Bausteins wird als Anhang angefügt]**. So können Sie die Definition des Gestaltungsbausteins direkt in den Inhalt der OpenOffice-Datei kopieren.

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
