---
solution: Campaign
product: Adobe Campaign
title: Interaktionsoperatoren für Kampagnen
description: Erstellen von Angebot-Management-Operatoren
feature: Übersicht
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: b9de052de5aaeee4b089feb70bf20723be5c9cfa
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 40%

---


# Operatoren-Profil {#operator-profiles}

Zwei Operatortypen können die Interaktion mit Kampagnen verwenden: **Angebot-Manager** und **Versand-Manager**. Jeder von ihnen hat spezifische Berechtigungen und Einschränkungen. Weitere Informationen zu Operatoren und Berechtigungen für Kampagnen finden Sie auf [dieser Seite](../start/permissions.md).

* Der **[!UICONTROL Angebot-Manager]** erstellt und verwaltet Angebot.
* Der **[!UICONTROL Versand-Manager]** genehmigt und verwendet Angebot

## Erstellen Sie einen Angebot-Manager-Operator{#offer-manager}

1. Erstellen Sie den neuen Benutzer.

:arrow_upper_right: Die Schritte zum Erstellen eines Operators in der Kampagne sind in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Klicken Sie im Fenster **[!UICONTROL Gruppen oder spezifische Berechtigungen]** auf die Schaltfläche **[!UICONTROL Hinzufügen]** und wählen Sie die Gruppe **[!UICONTROL Angebotsverantwortliche Benutzer]** aus.

Die dem Angebot-Manager zugewiesenen Rechte ermöglichen es ihnen, folgende Aufgaben durchzuführen:

* Änderung von **[!UICONTROL Design-Umgebungen]**;
* Ansicht von **[!UICONTROL Live-Umgebungen]**;
* Konfiguration von administrativen Funktionen (Platzierungen und vordefinierte Filter);
* Erstellung und Änderung von Angebotskategorien;
* Erstellung und Änderung von Angeboten;
* Konfiguration von Angebotseignungen;
* Validierung von Angeboten.

Beachten Sie, dass bei Angeboten, die in einem Workflow verwendet werden, der Operator der Operatorgruppe **[!UICONTROL Administrator]** oder **[!UICONTROL Angebot-Manager]** hinzugefügt werden muss, um den Workflow auszuführen.

>[!NOTE]
>
>Ein **Angebot-Manager** kann ein Angebot nur genehmigen, wenn kein Überprüfer angegeben ist oder wenn er in der Vorlage des Angebots, auf der das Angebot basiert, als Prüfer deklariert wurde.

## Erstellen Sie einen Versand-Manager-Operator {#delivery-manager}

1. Erstellen Sie den neuen Benutzer.

:arrow_upper_right: Die Schritte zum Erstellen eines Operators in der Kampagne sind in der [Campaign Classic-Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Klicken Sie im Fenster **[!UICONTROL Gruppen oder spezifische Berechtigungen]** auf die Schaltfläche **[!UICONTROL Hinzufügen]** und wählen Sie die Gruppe **[!UICONTROL Versandverantwortliche Benutzer]** aus.

Die dem Versand-Manager zugewiesenen Rechte sind/ermöglichen es ihm, folgende Aufgaben durchzuführen:

* Ansicht der **[!UICONTROL Design-Umgebungen]**;
* Anzeige und Änderung von Angebotskategorien;
* Validierung von Angeboten, wenn er als Validierer bezeichnet wurde.

   >[!NOTE]
   >
   >Ein **Versand-Manager** kann ein Angebot nur genehmigen, wenn er während der Konfiguration des Angebots als Überprüfer deklariert wurde.

## Berechtigungsmatrix pro Interaktionsoperator {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Angebot-Manager (Design env)</strong><br /> </td> 
   <td> <strong>Angebot-Manager (Live-Version)</strong><br /> </td> 
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
   <td> <strong>Versand-Manager (Design env.)</strong><br /> </td> 
   <td> <strong>Versand-Manager (Live-Version)</strong><br /> </td> 
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
