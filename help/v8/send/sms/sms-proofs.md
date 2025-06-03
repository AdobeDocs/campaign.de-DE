---
title: SMS-Testversand
description: Erfahren Sie, wie Sie einen SMS-Testversand durchführen.
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: d2ec4d92-7f00-47c8-98e6-0613d6387de0
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 100%

---

# Durchführen eines SMS-Testversands {#sms-proof}

Adobe empfiehlt ausdrücklich, einen Validierungszyklus für Sendungen einzurichten. Vergewissern Sie sich, dass Ihr Inhalt genehmigt wurde, bevor dieser an Ihre Zielgruppe gesendet wird.

Sie können einen Testversand für Ihren SMS-Versand durchführen, um ihn zu validieren:

1. Klicken Sie dazu auf die Schaltfläche **[!UICONTROL Testversand erzeugen]**. Daraufhin wird das folgende Fenster geöffnet:

   ![](assets/proof_targeting.png){zoomable="yes"}

   Es stehen mehrere Modi für einen Testversand zur Verfügung:

   * **[!UICONTROL Bestimmung einer speziellen Testversand-Zielgruppe]**: Ermöglicht Abfragen, die die Adressen in der Datenbank als Testversand-Zielgruppe filtern.
   * **[!UICONTROL Adressersetzung]**: Ermöglicht die Eingabe von Testadressen und Validierung des Inhalts mithilfe der Zielgruppen-Empfängerdaten. Die Ersatzadressen können manuell eingegeben oder aus der Dropdown-Liste ausgewählt werden. Die zugehörige Auflistung ist die **[!UICONTROL Ersatzadresse (rcpAddress)]**.
Standardmäßig wird die Ersetzung nach dem Zufallsprinzip durchgeführt. Sie können jedoch über das **[!UICONTROL Detail]**-Symbol eine bestimmte Empfängerin oder einen bestimmten Empfänger aus der Hauptzielgruppe auswählen.
   * **[!UICONTROL Testadressen]**: Ermöglicht den Zugriff auf Testadressen als Testversand-Zielgruppe. Diese Adressen können aus einer Datei importiert oder manuell eingegeben werden.
   * **[!UICONTROL Spezifische Zielgruppe und Testadressen]**: Ermöglicht die Kombination von Testadressen und Adressen von Empfängerinnen und Empfängern.

1. Fügen Sie nach Auswahl des gewünschten **[!UICONTROL Zielgruppenbestimmungsmodus]** Ihre Testadressen entsprechend hinzu.

   Im folgenden Beispiel wird **[!UICONTROL Bestimmung einer speziellen Testversand-Zielgruppe]** ausgewählt und eine Empfängerin bzw. ein Empfänger hinzugefügt:

   ![](assets/proof_recipient.png){zoomable="yes"}

1. Wählen Sie die Schaltfläche **[!UICONTROL Analysieren]** aus.
Adobe Campaign führt die gesamte Kontrolle aus, bevor der Testversand validiert wird. Am Ende der Analyse kann auf die Schaltfläche **[!UICONTROL Absendung bestätigen]** geklickt werden.

   ![](assets/proof_analyze.png){zoomable="yes"}

1. Um den SMS-Testversand durchzuführen, klicken Sie auf die Schaltfläche **[!UICONTROL Absendung bestätigen]**.

Wenn alles in Ordnung ist, können Sie fortfahren und [den SMS-Versand an die Zielgruppe durchführen](sms-audience.md).
