---
product: campaign
title: Lebenszyklus eines Workflows
description: Erfahren Sie mehr über den Lebenszyklus eines Workflows
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 4356b90c-9d7c-49ef-88cd-716b2ccdb7f0
TQID: https://experienceleague.adobe.com/lrXuOzmsLhy3AfYLPzKfLd1-IVfB5r9xZZqoMdihYus
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 261
ht-degree: 55%

---

# Lebenszyklus eines Workflows {#workflow-life-cycle}



Der Lebenszyklus eines Workflows gestaltet sich in drei Hauptetappen:

* **In Bearbeitung**

  Dies ist die anfängliche Design-Phase: Wenn ein neuer Workflow erstellt wird, lautet sein Status „In Bearbeitung“. Der Workflow wird noch nicht vom Server verarbeitet und kann ohne Risiko geändert werden.

* **Gestartet**

  Sobald die anfängliche Design-Phase abgeschlossen ist, kann der Workflow gestartet werden. In dieser Phase wird die Instanz vom Server verarbeitet und die einzelnen Aufgaben werden ausgeführt. Der Workflow kann dennoch mit bestimmten Vorsichtsmaßnahmen geändert werden.

* **Abgeschlossen**

  Ein Workflow ist abgeschlossen, wenn keine Aufgaben mehr zur Verarbeitung anstehen, oder wenn ein Benutzer die Workflow-Instanz ausdrücklich angehalten hat.

Beispielsweise sind im unten stehenden Workflow die Aktivitäten **Beginn** und **Versand** umrandet und die Aktivität **Validierung** blinkt.

![](assets/new-workflow-6.png)

Dies bedeutet, dass die ersten beiden Aktivitäten erfolgreich ausgeführt wurden und dass die Validierungsaktivität in Gang ist, d. h. sie wurde erstellt, ist aber noch nicht abgeschlossen.

Die Zeichen **574 -Ok**, die oberhalb der Transition nach der Aktivität **Versand** angezeigt werden, bedeuten, dass die Versandvorbereitung 574 Empfängerinnen und Empfänger angesprochen hat und dass der Vorgang erfolgreich abgeschlossen wurde. Diese Informationen, die den Transitionen bei ihrer Ausführung hinzugefügt werden, werden von den Aktivitäten berechnet, die Daten verarbeiten.

Der Workflow wartet also auf die Entscheidung eines Benutzers, der der Gruppe angehört, welche in der **Validierung**-Aktivität ausgewählt wurde. Gruppenmitglieder, deren E-Mail-Adresse oder Mobiltelefonnummer in ihrem Profil gespeichert sind, werden über die entsprechenden Kanäle benachrichtigt.

Weitere Informationen zur Überwachung Ihrer Workflows finden Sie in [diesem Abschnitt](monitor-workflow-execution.md).
