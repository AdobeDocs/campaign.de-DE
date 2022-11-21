---
product: campaign
title: Test
description: Erfahren Sie mehr über die Workflow-Aktivität "Test".
feature: Workflows
exl-id: 0d4d13f6-7128-44d3-ad5c-4ed02257ee64
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 100%

---

# Test{#test}



Ein **Test** aktiviert die erste Transition, welche die ihm zugeordneten Bedingungen erfüllt. Wenn keine der Bedingungen &#39;wahr&#39; zurückgibt, wird die **[!UICONTROL Standard-Verzweigung]** aktiviert, vorrausgesetzt, die entsprechende Option wurde angekreuzt.

Eine Bedingung ist ein JavaScript-Ausdruck, der entweder &#39;true&#39; oder &#39;false&#39; zurückgibt. Klicken Sie auf die Schaltfläche rechts in der Bedingungsspalte und wählen Sie die Option **[!UICONTROL Bearbeiten...]** aus.

![](assets/edit_test.png)

Weitere Informationen zu allen zusätzlichen JavaScript-Funktionen und SOAP-Methoden des über Workflow-JavaScript zugänglichen Applikationsservers finden Sie in der [JSAPI-Dokumentation](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=de).

Im Editor können auch direkt Variablen eingegeben werden. Weitere Informationen zum Arbeiten mit Variablen finden Sie in [diesem Abschnitt](javascript-scripts-and-templates.md#variables).

Bedingungen können im Bearbeitungsfenster der Aktivitätseigenschaften hinzugefügt, gelöscht oder geordnet oder über die Transition geändert werden.

Wenn ein Berechnungsergebnis in verschiedenen Bedingungen verwendet werden soll, kann die Berechnung im Initialisierungsscript der Aktivität erfolgen. Das Ergebnis ist dann in einer Variablen der Aufgabe zu speichern, damit es für die Bedingungsscripts verfügbar ist (task.vars.xxx).
