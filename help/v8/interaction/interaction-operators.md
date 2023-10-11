---
title: Benutzerprofile
description: Erstellen von Angebotsverwaltungs-Benutzern
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: ht
source-wordcount: '262'
ht-degree: 100%

---

# Benutzerprofile {#operator-profiles}

Zwei Typen von Benutzern können Campaign Interaction verwenden: **Angebotsverantwortliche** und **Versandverantwortliche**. Jeder dieser Benutzertypen verfügt über spezifische Berechtigungen und Einschränkungen. Weitere Informationen zu Campaign-Benutzern und -Berechtigungen finden Sie auf [dieser Seite](../start/gs-permissions.md).

* **[!UICONTROL Angebotsverantwortlicher]**: erstellt und verwaltet Angebote
* **[!UICONTROL Versandverantwortlicher]**: validiert und verwendet Angebote

## Erstellen eines angebotsverantwortlichen Benutzers{#offer-manager}

1. Erstellen Sie einen Benutzer. [Weitere Informationen](../start/manage-permissions.md#add-users)
1. Klicken Sie im Fenster **[!UICONTROL Gruppen oder spezifische Berechtigungen]** auf die Schaltfläche **[!UICONTROL Hinzufügen]** und wählen Sie die Gruppe **[!UICONTROL Angebotsverantwortliche Benutzer]** aus.

Die mit Angebotsverantwortlichen verknüpften Berechtigungen werden [hier](../start/manage-permissions.md#ootb-productprofiles) beschrieben.

## Erstellen eines versandverantwortlichen Benutzers {#delivery-manager}

1. Erstellen Sie einen Benutzer. [Weitere Informationen](../start/manage-permissions.md#add-users)
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
   <td> vordefinierte Angebotsfilter<br /> </td> 
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
   <td> vordefinierte Angebotsfilter<br /> </td> 
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
