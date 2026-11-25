---
product: campaign
title: Definieren des Layouts eines Web-Formulars
description: Definieren des Layouts eines Web-Formulars
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 23ca17f8-de1a-4f9c-8357-3965dc3329b1
TQID: 'https://experienceleague.adobe.com/-0PZWl-79Q-MXZ-jHjp-VF12IUPeMcq27aGSgWl5Ans'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 72%
---
# Definieren des Layouts eines Web-Formulars{#defining-web-forms-layout}



## Container erstellen {#creating-containers}

Mit Containern können Sie die Felder einer Seite kombinieren, ihr Layout konfigurieren und die Elemente auf der Seite organisieren.

Sie können für jede Seite des Formulars Container mit der Schaltfläche **[!UICONTROL Container]** in der Symbolleiste erstellen.

![Seiteneditor für Web-Formulare mit der Schaltfläche Container-Symbolleiste geöffnet, die die Option Standard-Container bietet](assets/s_ncs_admin_survey_containers_add.png)

Verwenden Sie einen Container zum Gruppieren von Elementen auf der Seite, ohne dass ein Titel zum endgültigen Rendering hinzugefügt wird. Elemente werden in der Container-Unterstruktur gruppiert. Mit Standard-Containern können Sie das Layout verwalten.

Beispiel:

![Seiteneigenschaften mit einer Baumstruktur aus zwei Containern, „Allgemeine Informationen“ und „Ihre Verträge“ sowie deren Formularfelder](assets/s_ncs_admin_survey_containers_std_arbo.png)

Die Position von Titeln wird auf Elemente angewendet, die in der Hierarchie unter dem Container platziert werden. Bei Bedarf kann dies für jedes Element überladen werden. Fügen Sie Spalten hinzu oder entfernen Sie sie, um das Layout zu ändern. Siehe [Die Felder auf der Seite positionieren](#positioning-the-fields-on-the-page).

Im obigen Beispiel wird das Rendering wie folgt ausgeführt:

![Gerenderte Formularseite mit zwei Containern: Feldern für persönliche Details und einer Checkbox-Liste für Verträge sowie einer Schaltfläche „Validieren“](assets/s_ncs_admin_survey_containers_std_ex.png)

## Die Felder auf der Seite positionieren {#positioning-the-fields-on-the-page}

Das Layout des Web-Formulars wird in jedem Container Seite für Seite definiert und kann bei Bedarf überschrieben werden.

Seiten sind in Spalten unterteilt: Jede Seite enthält eine bestimmte Anzahl von Spalten. Jedes Feld der Seite belegt **n** Zellen. Container umfassen auch eine gewisse Anzahl von Spalten und die in ihnen enthaltenen Felder haben eine bestimmte Anzahl von Zellen.

Standardmäßig werden Seiten in einer einzelnen Spalte erstellt und jedes Element belegt eine Zelle. Das bedeutet, dass Felder untereinander angezeigt werden, wobei jedes wie unten dargestellt eine ganze Zeile umfasst:

![Gerenderte einspaltige Formularseite mit den Feldern „Geschlecht“, „Name“, „Vorname“ und „E-Mail“, die in separaten Zeilen gestapelt sind](assets/s_ncs_admin_survey_container_ex.png)

Im folgenden Beispiel wurde die Standardkonfiguration beibehalten. Die Seite belegt eine einzige Spalte, die vier Container enthält.

![Seiteneigenschaften mit vier Containern und hervorgehobener Anzahl von Spalten, die auf 1 gesetzt sind](assets/s_ncs_admin_survey_container_ex0.png)

Jeder Container belegt eine Spalte und jedes Element belegt eine Zelle:

![Eigenschaften des Informationselements, wobei in den Anzeigeeinstellungen die Anzahl der Zellen auf 1 gesetzt ist](assets/s_ncs_admin_survey_container_ex0a.png)

Das Rendering sieht folgendermaßen aus:

![Einspaltiges Seiten-Rendering mit vier Containern mit jeweils einer Spalte, vertikal gestapelt](assets/s_ncs_admin_survey_container_ex0_rend.png)

Sie können die Anzeigeparameter anpassen, um das folgende Rendering zu erhalten:

![Zweispaltiges Seiten-Rendering, bei dem die Container 1 und 3 die linke Spalte und die Container 2 und 4 die rechte Spalte ausfüllen](assets/s_ncs_admin_survey_container_ex1_rend.png)

Im obigen Rendering-Beispiel belegt jedes Eingabefeld, jeder Titel und jedes Bild eine einzige Zelle in den Spalten der Container.

Sie können die Formatierung in jedem Container ändern. In unserem Beispiel können Sie den Inhalt von Container 4 auf zwei Spalten aufteilen und die Elemente verteilen.

![Container 4 mit zwei Spalten: Titel und Kombinationsfeld nehmen jeweils eine Zelle ein, das Kontrollkästchen umfasst zwei Zellen](assets/s_ncs_admin_survey_container_ex2_rend.png)

Der Titel und die Liste belegen jeweils eine Zelle (und daher eine ganze Zeile des Containers) und das Kontrollkästchen erstreckt sich über zwei Zellen. Die Anzahl der dem Eingabefeld zugeordneten Zellen ist auf der Registerkarte **[!UICONTROL Allgemein]** oder auf der Registerkarte **[!UICONTROL Erweitert]** entsprechend dem Feldtyp definiert:

![Registerkarte Erweitert des Kontrollkästchenelements mit der Anzahl der Zellen auf 2 unter Anzeigeeinstellungen](assets/s_ncs_admin_survey_container_ex2.png)

## Die Position von Titeln definieren {#defining-the-position-of-labels}

Sie können die Ausrichtung von Feldern und Titeln im Formular definieren.

Standardmäßig übernehmen die Anzeigeparameter für Felder und andere Inhalte der Seite die allgemeine Konfiguration des Formulars, die Konfiguration der Seite oder die Konfiguration des übergeordneten Containers, sofern einer vorhanden ist.

Die globalen Anzeigeparameter für das gesamte Formular werden im Eigenschaftsfeld des Formulars festgelegt. Im Tab **[!UICONTROL Rendering]** kann die Position der Titel ausgewählt werden.

![Dialogfeld „Eigenschaften“ des Webformulars, Registerkarte „Rendering“, mit der Liste der Titelpositionen: Übernommen, Links, Rechts, Oben, Unten, Ausgeblendet](assets/s_ncs_admin_survey_label_position.png)

Diese Position kann für jede Seite, jeden Container und jedes Feld über den Tab **[!UICONTROL Erweitert]** überschrieben werden.

Folgende Ausrichtungen werden unterstützt:

* Geerbt: Die Ausrichtung wird vom übergeordneten Element (Standardwert) übernommen, d. h. vom übergeordneten Container, sofern vorhanden, oder ansonsten von der Seite.
* Links/rechts: Der Titel wird rechts oder links neben dem Feld positioniert.
* Oberhalb/unterhalb: Der Titel wird ober- oder unterhalb des Felds positioniert.
* Ausgeblendet: Der Titel wird nicht angezeigt.
