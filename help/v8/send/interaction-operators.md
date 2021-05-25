---
solution: Campaign v8
product: Adobe Campaign
title: Campaign Interaction-Benutzer
description: Erstellen von Angebotsmanagement-Operatoren
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 40%

---


# Benutzerprofile {#operator-profiles}

Zwei Operatortypen können Campaign Interaction verwenden: **Angebotsverantwortliche Benutzer** und **Versand-Manager**. Jeder von ihnen verfügt über spezifische Berechtigungen und Einschränkungen. Weitere Informationen zu Campaign-Benutzern und -Berechtigungen finden Sie auf [dieser Seite](../start/permissions.md).

* Der **[!UICONTROL Angebotsverantwortliche]** erstellt und verwaltet Angebote.
* Der **[!UICONTROL Versandverantwortliche]** genehmigt und verwendet Angebote.

## Erstellen eines Angebotsverantwortlichen{#offer-manager}

1. Erstellen Sie den neuen Benutzer.

   :arrow_upper_right: Die Schritte zum Erstellen eines Benutzers in Campaign werden im [Campaign Classic v7-Handbuch](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html) beschrieben.

1. Klicken Sie im Fenster **[!UICONTROL Gruppen oder spezifische Berechtigungen]** auf die Schaltfläche **[!UICONTROL Hinzufügen]** und wählen Sie die Gruppe **[!UICONTROL Angebotsverantwortliche Benutzer]** aus.

Die dem Angebotsverantwortlichen zugewiesenen Berechtigungen ermöglichen ihm die Durchführung folgender Aufgaben:

* Änderung von **[!UICONTROL Design-Umgebungen]**;
* Ansicht von **[!UICONTROL Live-Umgebungen]**;
* Konfiguration von administrativen Funktionen (Platzierungen und vordefinierte Filter);
* Erstellung und Änderung von Angebotskategorien;
* Erstellung und Änderung von Angeboten;
* Konfiguration von Angebotseignungen;
* Validierung von Angeboten.

Beachten Sie, dass bei der Verwendung von Angeboten in einem Workflow der Operator **[!UICONTROL Administrator]** oder **[!UICONTROL Angebotsverantwortliche]** hinzugefügt werden muss, um den Workflow auszuführen.

>[!NOTE]
>
>Ein **Angebotsverantwortlicher** kann ein Angebot nur genehmigen, wenn kein Validierer angegeben wurde oder wenn er in der Angebotsvorlage, auf der das Angebot basiert, als Validierer deklariert wurde.

## Versand-Manager-Benutzer {#delivery-manager} erstellen

1. Erstellen Sie den neuen Benutzer.

   :arrow_upper_right: Die Schritte zum Erstellen eines Benutzers in Campaign werden im [Campaign Classic v7-Handbuch](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html) beschrieben.

1. Klicken Sie im Fenster **[!UICONTROL Gruppen oder spezifische Berechtigungen]** auf die Schaltfläche **[!UICONTROL Hinzufügen]** und wählen Sie die Gruppe **[!UICONTROL Versandverantwortliche Benutzer]** aus.

Die dem Versandverantwortlichen zugewiesenen Berechtigungen ermöglichen es ihm, die folgenden Aufgaben auszuführen:

* Ansicht der **[!UICONTROL Design-Umgebungen]**;
* Anzeige und Änderung von Angebotskategorien;
* Validierung von Angeboten, wenn er als Validierer bezeichnet wurde.

   >[!NOTE]
   >
   >Ein **Versandverantwortlicher** kann ein Angebot nur genehmigen, wenn er während der Angebotskonfiguration als Validierer deklariert wurde.

## Berechtigungsmatrix pro Interaction-Operator {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Angebotsverantwortlicher (Design-Umgebung)</strong><br /> </td> 
   <td> <strong>Angebotsverantwortlicher (Live-Umgebung)</strong><br /> </td> 
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
   <td> <strong>Versand-Manager (Design-Umgebung)</strong><br /> </td> 
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
