---
product: campaign
title: Datei-Wächter
description: Erfahren Sie mehr über die Workflow-Aktivität "Datei-Wächter".
feature: Workflows, Data Management
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 614becf7-4cbf-40f9-a1b1-06efa054bfd9
TQID: https://experienceleague.adobe.com/7fxaGcRPnb0Q3FqBkIA4da9ksKnGDDZ4ALVTGdGsKq0
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 565
ht-degree: 56%

---

# Datei-Wächter{#file-collector}



Der **Datei-Wächter** überwacht das Eintreffen einer oder mehrerer Dateien in einem Verzeichnis und aktiviert für jede empfangene Datei deren Transition. Für jedes Ereignis enthält **[!UICONTROL Variable &quot;]**&quot; den vollständigen Namen der empfangenen Datei. Die gesammelten Dateien werden zu Archivierungszwecken in ein anderes Verzeichnis verschoben, um sicherzustellen, dass sie nur einmal gezählt werden.

Standardmäßig ist der Datei-Wächter eine persistente Aufgabe, die zu den in der Planung definierten Zeitpunkten das Verzeichnis auf das Vorhandensein von Dateien prüft.

Die Dateien müssen sich auf dem Server befinden, auf dem das für diesen Workflow verantwortliche wfserver-Modul ausgeführt wird. Wenn mehrere wfserver-Module auf einer einzigen Instanz bereitgestellt werden, muss entweder die Affinität der Aktivitäten, die diese Dateien verwenden, oder die Gesamtaffinität des Workflows angegeben werden.

## Eigenschaften {#properties}

Auf dem ersten Tab der Aktivität **[!UICONTROL Datei-Wächter]** können Sie den Quellordner auswählen und die erfassten Dateien bei Bedarf filtern. Die anderen Tabs werden unter [E-Mail-Empfang](inbound-emails.md) (auf den Tabs **[!UICONTROL Planung]** und **[!UICONTROL Ablauf]**) ausführlich beschrieben.

![](assets/file_collect_edit.png)

1. **Abruf der Dateien**

   * **[!UICONTROL Verzeichnis]**

     Ordner, der die herunterzuladenden Dateien enthält. Dieses Verzeichnis muss zuvor auf dem Server erstellt werden: Wenn es nicht existiert, wird ein Fehler ausgelöst.

   * **[!UICONTROL Filter]**

     Nur Dateien, die diesem Filter entsprechen, werden berücksichtigt. Die anderen Dateien im Verzeichnis werden ignoriert. Wenn der Filter leer ist, werden alle Dateien im Verzeichnis berücksichtigt. Filterbeispiele: **&#42;.zip**, **import-&#42;.txt**.

   * **[!UICONTROL Stoppen, sobald eine Datei bearbeitet wurde]**

     Wenn diese Option aktiviert ist, endet die Aufgabe nach Erhalt der ersten Datei. Wenn mehrere dem Filter entsprechende Dateien im Verzeichnis vorhanden sind, wird nur eine berücksichtigt. Diese Option garantiert, dass nur ein Ereignis gesendet wird. Die berücksichtigte Datei ist die erste in der Liste in alphabetischer Reihenfolge.

     Im Falle einer Aktivität, für die keine Planung definiert wurde, wird ein Fehler erzeugt, wenn keine Datei den Filterkriterien entspricht und die Option **[!UICONTROL Fehlen von Dateien bearbeiten]** nicht aktiviert wurde.

   * **[!UICONTROL Planung]**

     Definiert mithilfe der im Tab **[!UICONTROL Planung]** angegebenen Parameter die Häufigkeit, mit der das Verzeichnis auf die Existenz von Dateien überprüft wird.

1. **Umgang mit Fehlern**

   Zwei Optionen stehen zur Verfügung:

   * **[!UICONTROL Fehlen von Dateien bearbeiten]**

     Bei Ankreuzen dieser Option erscheint eine spezifische Transition, die immer dann aktiviert wird, wenn keine dem Filter entsprechende Datei im angegebenen Verzeichnis vorhanden ist.

     Wenn für die Aufgabe keine Planung definiert wurde, wird diese Transition nur einmal aktiviert.

   * **[!UICONTROL Fehler verarbeiten]**

     Mit dieser Option wird ein spezieller Übergang angezeigt, der aktiviert wird, wenn ein Fehler erzeugt wird. In diesem Fall ändert sich der Workflow nicht in den Fehlerstatus und wird weiter ausgeführt

     Dies gilt für Fehler des Dateisystems (Datei kann nicht verschoben werden, Zugriff auf das Verzeichnis nicht möglich usw.).

     Fehler, die aus der Konfiguration der Aktivität resultieren, beispielsweise durch Angabe von ungültigen Werten (z. B. inexistentes Verzeichnis), werden nicht verarbeitet.

1. **Verlauf**

   Informationen zum Schritt **[!UICONTROL Verlaufserstellung]** finden Sie unter [HTTP-Übertragung](web-download.md).

Die Reihenfolge der Dateiverarbeitung kann nicht beeinflusst werden. Um eine Reihe von Dateien schrittweise zu verarbeiten, kann die Option **[!UICONTROL Stoppen, sobald eine Datei bearbeitet wurde]** in Verbindung mit einer Schlaufe verwendet werden. In diesem Fall werden die Dateien in alphabetischer Reihenfolge verarbeitet. Die Option **[!UICONTROL Fehlen von Dateien bearbeiten]** beendet die Schlaufe.

![](assets/file_collect_loop.png)

## Ausgabeparameter {#output-parameters}

* filename: vollständiger Dateiname. Dies ist der Dateiname, nachdem er in das Historisierungsverzeichnis verschoben wurde. Der Pfad ist daher anders; der Name unterscheidet sich jedoch ebenfalls, wenn in dem Verzeichnis bereits eine andere Datei mit demselben Namen vorhanden ist. Die Erweiterung bleibt erhalten.
