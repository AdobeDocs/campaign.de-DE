---
product: campaign
title: Content Management
description: Content Management
feature: Workflows, Data Management
exl-id: 9b225f78-1959-4e4f-aa4e-ff8a63051154
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 100%

---

# Content Management{#content-management}

Mithilfe der Aktivität **Content Management** lassen sich Inhalte erstellen und bearbeiten sowie Inhaltsdateien erzeugen. Die Inhalte können dann im Ramen einer Versandaktivität genutzt werden.

>[!CAUTION]
>
>Das Content Management ist ein optionales Modul von Adobe Campaign. Bitte prüfen Sie Ihren Lizenzvertrag.

Die Konfiguration der Aktivität gliedert sich in drei Schritte:

* **Inhalt auswählen**: Der Inhalt kann zuvor erstellt worden sein oder in der Aktivität erstellt werden.
* **Inhalt aktualisieren**: Die Aufgabe kann den Betreff des Inhalts ändern oder den gesamten XML-Inhalt importieren.
* **Auszuführende Aktion**: Der Inhalt kann gespeichert oder erzeugt werden.

  ![](assets/content_mgmt_edit.png)

1. **Content**

   * **[!UICONTROL Wird durch die Transition angegeben]**

     Bei Auswahl dieser Option wird der durch die eingehende Transition übermittelte Inhalt verwendet. Dies bedeutet, dass das Ereignis, welches das Content Management aktiviert, eine **[!UICONTROL contentId]**-Variable enthalten muss. Diese kann durch eine vorangehende Content-Management-Aktivität oder durch ein beliebiges Script bestimmt worden sein.

   * **[!UICONTROL Explizit]**

     Wählen Sie diese Option, wenn ein zuvor erstellter Inhalt verwendet werden soll. Geben Sie diesen im Feld **[!UICONTROL Inhalt]** an. Das Feld erscheint nur, wenn die Option **[!UICONTROL Explizit]** angekreuzt wurde.

     ![](assets/content_mgmt_explicit.png)

   * **[!UICONTROL Wird durch ein Script erstellt]**

     Die Kennung des Inhalts wird über ein Script erstellt. Im Feld **[!UICONTROL Script]** wird das JavaScript-Template berechnet, welches die Kennung (den Primärschlüssel) des Inhalts auswertet. Das Feld erscheint nur, wenn die Option **[!UICONTROL Wird durch ein Script erstellt]** aktiviert wurde.

     ![](assets/content_mgmt_script.png)

   * **[!UICONTROL Neu, basierend auf einer Veröffentlichungsvorlage erstellt]**

     Wählen Sie diese Option, wenn ein neuer, auf einer Vorlage beruhender Inhalt erstellt werden soll. Geben Sie im Feld **[!UICONTROL Inhaltskanal]** den Ordner an, in dem der neue Inhalt gespeichert werden soll und im Feld **[!UICONTROL Vorlage]** die zu verwendende Veröffentlichungsvorlage.

     ![](assets/content_mgmt_new.png)

1. **Bereich Inhalt aktualisieren**

   * **[!UICONTROL Betreff]**

     Hier kann der Betreff der dem Inhalt entsprechenden Versandaktion überschrieben werden.

   * **[!UICONTROL Zugriff auf Daten eines XML-Streams]**

     Mithilfe dieser Option ist es möglich, einen Inhalt ausgehend von einem XML-Dokument, das von einem Webserver heruntergeladen wurde, zu erstellen und ihn gegebenenfalls mit einem XSL-Stylesheet umzuwandeln. Im Feld **[!UICONTROL URL]** ist die URL für den XML-Download und im Feld **[!UICONTROL XSL-Stylesheet]** das für die Umwandlung zu nutzende Stylesheet anzugeben. Letzteres ist optional.

     ![](assets/content_mgmt_xmlcontent.png)

1. **Auszuführende Aktion**

   * **[!UICONTROL Speichern]**

     Der erstellte oder geänderte Inhalt wird gespeichert.

     In diesem Fall wird die ausgehende Transition einmal aktiviert. In der Variable **[!UICONTROL contentId]** wird die Kennung des Inhalts gespeichert.

   * **[!UICONTROL Erzeugen]**

     Der Inhalt wird gespeichert und die Ausgabedateien für alle Umwandlungsvorlagen mit dem Veröffentlichungstyp &#39;Datei&#39; werden erzeugt.

     ![](assets/content_mgmt_generate.png)

     In diesem Fall wird die ausgehende Transition für jede erzeugte Datei aktiviert. In der Variable **[!UICONTROL contentId]** wird die Kennung des Inhalts und in der Variable **[!UICONTROL filename]** der Name der Datei gespeichert.

## Eingabeparameter {#input-parameters}

* contentId

Kennung des zu verwendenden Inhalts, wenn die Option **[!UICONTROL Wird durch die Transition angegeben]** ausgewählt wurde.

## Ausgabeparameter {#output-parameters}

* contentId

  Kennung des Inhalts.

* filename

  Vollständiger Name der erzeugten Datei, wenn die Aktion **[!UICONTROL Erzeugen]** ausgewählt wurde.
