---
title: Campaign Interaction-Benutzer
description: Erstellen von Angebotsverwaltungs-Benutzern
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: 94fc2739c538f3aa8b11e0ea69d08f1bfffb5d32
workflow-type: ht
source-wordcount: '383'
ht-degree: 100%

---

# Benutzerprofile {#operator-profiles}

Zwei Typen von Benutzern können Campaign Interaction verwenden: **Angebotsverantwortliche** und **Versandverantwortliche**. Jeder dieser Benutzertypen verfügt über spezifische Berechtigungen und Einschränkungen. Weitere Informationen zu Campaign-Benutzern und -Berechtigungen finden Sie auf [dieser Seite](../start/permissions.md).

* **[!UICONTROL Angebotsverantwortlicher]**: erstellt und verwaltet Angebote
* **[!UICONTROL Versandverantwortlicher]**: validiert und verwendet Angebote

## Erstellen eines angebotsverantwortlichen Benutzers{#offer-manager}

1. Erstellen Sie einen Benutzer.

   ![](../assets/do-not-localize/book.png) Die Schritte zum Erstellen eines Benutzers in Campaign werden in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html?lang=de) beschrieben.

1. Klicken Sie im Fenster **[!UICONTROL Gruppen oder spezifische Berechtigungen]** auf die Schaltfläche **[!UICONTROL Hinzufügen]** und wählen Sie die Gruppe **[!UICONTROL Angebotsverantwortliche Benutzer]** aus.

Die dem Angebotsverantwortlichen zugewiesenen Berechtigungen erlauben ihm folgende Tätigkeiten:

* Änderung von **[!UICONTROL Design-Umgebungen]**;
* Ansicht von **[!UICONTROL Live-Umgebungen]**;
* Konfiguration von administrativen Funktionen (Platzierungen und vordefinierte Filter);
* Erstellung und Änderung von Angebotskategorien;
* Erstellung und Änderung von Angeboten;
* Konfiguration von Angebotseignungen;
* Validierung von Angeboten.

Wenn Angebote in einem Workflow verwendet werden, muss der Benutzer der Benutzergruppe **[!UICONTROL Administrator]** oder **[!UICONTROL Angebotsverantwortliche Benutzer]** hinzugefügt werden, um den Workflow auszuführen.

>[!NOTE]
>
>**Angebotsverantwortliche Benutzer** können ein Angebot nur genehmigen, wenn kein Prüfer angegeben ist oder wenn sie in der Angebotsvorlage als Prüfer deklariert wurden.

## Erstellen eines versandverantwortlichen Benutzers {#delivery-manager}

1. Erstellen Sie einen Benutzer.

   ![](../assets/do-not-localize/book.png) Die Schritte zum Erstellen eines Benutzers in Campaign werden in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html?lang=de) beschrieben.

1. Klicken Sie im Fenster **[!UICONTROL Gruppen oder spezifische Berechtigungen]** auf die Schaltfläche **[!UICONTROL Hinzufügen]** und wählen Sie die Gruppe **[!UICONTROL Versandverantwortliche Benutzer]** aus.

Versandverantwortliche Benutzer können mit den ihnen zugewiesenen Rechten die folgenden Aufgaben ausführen:

* Ansicht der **[!UICONTROL Design-Umgebungen]**;
* Anzeige und Änderung von Angebotskategorien;
* Angebote genehmigen, wenn sie ihre Prüfer sind.

   >[!NOTE]
   >
   >**Versandverantwortliche Benutzer** können ein Angebot nur genehmigen, wenn sie in der Angebotskonfiguration als Prüfer angegeben wurden.

## Erlaubnismatrix pro Interaktionsbenutzer {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Angebotsverantwortlicher Benutzer (Design-Umgebung)</strong><br /> </td> 
   <td> <strong>Angebotsverantwortlicher Benutzer (Live-Umgebung)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Knoten im Navigationsbaum</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Angebote - Design/Live<br /> </td> 
   <td> Lesen/Schreiben<br /> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
  <tr> 
   <td> Umgebung - Empfänger<br /> </td> 
   <td> Lesen/Schreiben<br /> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
  <tr> 
   <td> Administration<br /> </td> 
   <td> Lesen/Schreiben<br /> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
  <tr> 
   <td> Platzierungen<br /> </td> 
   <td> Lesen/Schreiben<br /> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
  <tr> 
   <td> Vordefinierte Angebotsfilter<br /> </td> 
   <td> Lesen/Schreiben<br /> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
  <tr> 
   <td> Typologien<br /> </td> 
   <td> Lesen/Schreiben<br /> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
  <tr> 
   <td> Typologieregeln<br /> </td> 
   <td> Lesen/Schreiben<br /> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
  <tr> 
   <td> Angebotskatalog<br /> </td> 
   <td> Lesen/Schreiben<br /> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
  <tr> 
   <td> Angebotskategorien<br /> </td> 
   <td> Lesen/Schreiben<br /> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Versandverantwortlicher (Design-Umgebung)</strong><br /> </td> 
   <td> <strong>Versandverantwortlicher (Live-Umgebung)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Knoten im Navigationsbaum</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Angebote - Design/Live<br /> </td> 
   <td> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
  <tr> 
   <td> Umgebung - Empfänger<br /> </td> 
   <td> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
  <tr> 
   <td> Administration<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Platzierungen<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Vordefinierte Angebotsfilter<br /> </td> 
   <td> Lesen<br /> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
  <tr> 
   <td> Typologien<br /> </td> 
   <td> Lesen<br /> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
  <tr> 
   <td> Typologieregeln<br /> </td> 
   <td> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
  <tr> 
   <td> Angebotskatalog<br /> </td> 
   <td> Lesen<br /> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
  <tr> 
   <td> Angebotskategorien<br /> </td> 
   <td> </td> 
   <td> Lesen<br /> </td> 
  </tr> 
 </tbody> 
</table>
