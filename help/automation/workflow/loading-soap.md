---
product: campaign
title: Laden (SOAP)
description: Laden (SOAP)
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Laden (SOAP){#loading-soap}



>[!CAUTION]
>
>Die Aktivität **Laden (SOAP)** erfordert die Installation des **FDA**-Moduls (Federated Data Access). Bitte prüfen Sie Ihren Lizenzvertrag.

Im Allgemeinen wird die Aktivität **Laden (SOAP)** ergänzend zur Aktivität **Laden (DBMS)** eingesetzt, für den Fall, dass der direkte Datenabruf aus einer externen Datenbank über den FDA nicht möglich ist.

Gehen Sie wie folgt vor:

1. Wählen Sie zwischen der Verwendung eines Beispiel-XMLs oder einer WSDL.

   Das im Folgenden dargestellte Beispiel stammt aus einem technischen Workflow des Message-Center-Moduls.

   ![](assets/load_soap_002.png)

1. Wählen Sie im Fall des Beispiel-XMLs die gewünschte Beispieldatei aus. Die Datei wird analysiert, um ein Beispielergebnis zu erzeugen.

   Im Falle einer WSDL ist die entsprechende Zugriffs-URL anzugeben und das Code-Skelett zu erzeugen. Der ausgewählte Dienst und der ausgewählte Aufruf werden automatisch aktualisiert und angezeigt.

   ![](assets/soap_load_003.png)

1. Klicken Sie auf den Link **[!UICONTROL Zur Ansicht und Änderung des Analyseergebnisses hier klicken...]**, um die identifizierten Spalten zu definieren.

   ![](assets/soap_load_001.png)

   Durch Klick auf **[!UICONTROL Beispiel erneut analysieren]**, können Sie das Beispiel aktualisieren.

   Sie können auch das Format der Spaltendaten über die Schaltfläche ** personalisieren.

1. Als Kennung kann die Zeilennummer verwendet werden und/oder Sie können angeben, dass der SOAP-Aufruf mehrere Elemente zurückgibt.
1. Geben Sie die erforderlichen Scripts in den entsprechenden Tabs ein:

   * **[!UICONTROL Initialisierung]**: Herstellung der SOAP-Verbindung.
   * **[!UICONTROL Iteration]**: Aufruf des SOAP-Dienstes. Zurückgegeben werden muss ein XML-Objekt, dass mit der Beispielbeschreibung oder der WSDL kompatibel ist.

      Der Code dieses Tabs wird von Adobe Campaign so lange in einer Schleife aufgerufen, bis ein Null-XML-Element zurückgegeben wird.

   * **[!UICONTROL Fertigstellung]**: Unterbrechung der Verbindung und/oder Freigabe der anderen, während des Vorgangs erstellten Ressourcen.