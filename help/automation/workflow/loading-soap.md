---
product: campaign
title: Laden (SOAP)
description: Laden (SOAP)
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 21c42a36-9a50-49b8-8a07-b041ba8b2026
TQID: 'https://experienceleague.adobe.com/CBO5ddwOwsFclqdXq-ahz6ZMg0fXVc4L8vIruKz17j4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 82%
---
# Laden (SOAP){#loading-soap}



>[!CAUTION]
>
>Die Aktivität **Laden (SOAP)** erfordert die Installation des **FDA**-Moduls (Federated Data Access). Prüfen Sie diesbezüglich Ihren Lizenzvertrag.

Im Allgemeinen wird die Aktivität **Laden (SOAP)** ergänzend zur Aktivität **Laden (DBMS)** eingesetzt, für den Fall, dass der direkte Datenabruf aus einer externen Datenbank über den FDA nicht möglich ist.

Gehen Sie wie folgt vor:

1. Wählen Sie zwischen der Verwendung eines Beispiel-XMLs oder einer WSDL.

   Das im Folgenden dargestellte Beispiel stammt aus einem technischen Workflow des Message-Center-Moduls.

   ![Aktivität „Laden (SOAP)“ mit ausgewählter Beispiel-XML, Ergebnisbeispiel und Initialisierungsskript verwenden.](assets/load_soap_002.png)

1. Wählen Sie für ein XML-Beispiel eine Beispieldatei aus. Die Datei wird analysiert, um ein Beispielergebnis zu erzeugen.

   Geben Sie für eine WSDL die entsprechende Zugriffs-URL ein und generieren Sie dann das Code-Skelett. Der ausgewählte Dienst und Aufruf werden automatisch aktualisiert und angezeigt.

   ![Ergebnisformat mit ausgewählter Option „WSDL verwenden“, einem Feld „Zugriffs-URL“ und dem Link „Skelett-Code generieren“.](assets/soap_load_003.png)

1. Klicken Sie auf den Link **[!UICONTROL Zur Ansicht und Änderung des Analyseergebnisses hier klicken...]**, um die identifizierten Spalten zu definieren.

   ![Dateiformatfenster mit einer Liste identifizierter Spalten mit Titel, Datentyp und internem Namen der ausgewählten Spalte.](assets/soap_load_001.png)

   Durch Klick auf **[!UICONTROL Beispiel erneut analysieren]**, können Sie das Beispiel aktualisieren.

1. Als Kennung kann die Zeilennummer verwendet werden und/oder Sie können angeben, dass der SOAP-Aufruf mehrere Elemente zurückgibt.
1. Geben Sie die erforderlichen Scripts in den entsprechenden Tabs ein:

   * **[!UICONTROL Initialisierung]**: Herstellung der SOAP-Verbindung.
   * **[!UICONTROL Iteration]**: Aufruf des SOAP-Dienstes. Zurückgegeben werden muss ein XML-Objekt, das mit der Beispielbeschreibung oder der WSDL kompatibel ist.

     Der Code dieses Tabs wird von Adobe Campaign so lange in einer Schleife aufgerufen, bis ein Null-XML-Element zurückgegeben wird.

   * **[!UICONTROL Fertigstellung]**: Unterbrechung der Verbindung und/oder Freigabe der anderen, während des Vorgangs erstellten Ressourcen.
