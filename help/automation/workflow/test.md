---
product: campaign
title: Testen
description: Erfahren Sie mehr über die Workflow-Aktivität "Test".
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 0d4d13f6-7128-44d3-ad5c-4ed02257ee64
TQID: https://experienceleague.adobe.com/dXkGOQ-OD-KUwWx29DcE7FqYzbDSF-M6ox8-8cTurjA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
source-git-commit: 2425b8e500380076d56bccec41ac821f7c867d92
workflow-type: tm+mt
source-wordcount: 197
ht-degree: 96%

---

# Test{#test}



Mit einer Aktivität des Typs **Test** wird die erste Transition aktiviert, die die damit verknüpfte Bedingung erfüllt. Wenn keine Bedingung erfüllt ist und die Option **[!UICONTROL Standardtransition verwenden]** aktiviert ist, wird die Standardtransition aktiviert.

Eine Bedingung ist ein JavaScript-Ausdruck, der als &#39;true&#39; oder &#39;false&#39; ausgewertet werden muss. Um den Ausdruck einzugeben, klicken Sie auf das Symbol rechts neben dem Namen der Bedingung und wählen Sie **[!UICONTROL Bearbeiten…]**.

![](assets/edit_test.png)

Weitere Informationen zu allen zusätzlichen JavaScript-Funktionen und SOAP-Methoden des über Workflow-JavaScript zugänglichen Applikationsservers finden Sie in der [JSAPI-Dokumentation](https://experienceleague.adobe.com/en/tools/campaign-api){target="_blank"}.

Im Editor können auch direkt Variablen eingegeben werden. Weitere Informationen zum Arbeiten mit Variablen finden Sie in [diesem Abschnitt](javascript-scripts-and-templates.md#variables).

Bedingungen können im Bearbeitungsfenster der Aktivitätseigenschaften hinzugefügt, gelöscht oder geordnet oder über die Transition geändert werden.

Wenn ein Berechnungsergebnis in verschiedenen Bedingungen verwendet werden soll, kann die Berechnung im Initialisierungsskript der Aktivität erfolgen. Das Ergebnis muss dann in einer Variablen der Aufgabe gespeichert werden, damit es für die Bedingungsskripts verfügbar ist (task.vars.xxx).
