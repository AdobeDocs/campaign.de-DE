---
product: campaign
title: Test
description: Erfahren Sie mehr über die Workflow-Aktivität "Test".
feature: Workflows
exl-id: 0d4d13f6-7128-44d3-ad5c-4ed02257ee64
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: ht
source-wordcount: '192'
ht-degree: 100%

---

# Test{#test}



Eine Aktivität vom Typ **Test** aktiviert die erste Transition, die die mit ihr verbundene Bedingung erfüllt. Wenn keine Bedingung erfüllt ist und die Option **[!UICONTROL Standard-Verzweigung verwenden]** angekreuzt ist, wird der Standardübergang aktiviert.

Eine Bedingung ist ein JavaScript-Ausdruck, der als &#39;true&#39; oder &#39;false&#39; ausgewertet werden muss. Um den Ausdruck einzugeben, klicken Sie auf das Symbol rechts neben dem Namen der Bedingung und wählen Sie **[!UICONTROL Bearbeiten…]**.

![](assets/edit_test.png)

Weitere Informationen zu allen zusätzlichen JavaScript-Funktionen und SOAP-Methoden des über Workflow-JavaScript zugänglichen Anwendungs-Servers finden Sie in der [JSAPI-Dokumentation](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=de){target="_blank"}.

Im Editor können auch direkt Variablen eingegeben werden. Weitere Informationen zum Arbeiten mit Variablen finden Sie in [diesem Abschnitt](javascript-scripts-and-templates.md#variables).

Bedingungen können im Bearbeitungsfenster der Aktivitätseigenschaften hinzugefügt, gelöscht oder geordnet oder über die Transition geändert werden.

Wenn ein Berechnungsergebnis in verschiedenen Bedingungen verwendet werden soll, kann die Berechnung im Initialisierungsscript der Aktivität erfolgen. Das Ergebnis ist dann in einer Variablen der Aufgabe zu speichern, damit es für die Bedingungsscripts verfügbar ist (task.vars.xxx).
