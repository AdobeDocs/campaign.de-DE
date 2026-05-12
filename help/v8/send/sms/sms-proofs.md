---
title: SMS-Testversand
description: Erfahren Sie, wie Sie einen SMS-Testversand durchführen.
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: d2ec4d92-7f00-47c8-98e6-0613d6387de0
TQID: https://experienceleague.adobe.com/mAVky406-MXlkv76bqxfmolzhemVCUYKhQF1ESceRdE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 97%

---

# Durchführen eines SMS-Testversands {#sms-proof}

Adobe empfiehlt ausdrücklich, einen Validierungszyklus für Sendungen einzurichten. Vergewissern Sie sich, dass Ihr Inhalt genehmigt wurde, bevor dieser an Ihre Zielgruppe gesendet wird.

Sie können einen Testversand für Ihren SMS-Versand durchführen, um ihn zu validieren:

1. Klicken Sie dazu auf die Schaltfläche **[!UICONTROL Testversand erzeugen]**. Daraufhin wird das folgende Fenster geöffnet:

   ![](assets/proof_targeting.png){zoomable="yes"}

   Es stehen mehrere Modi für einen Testversand zur Verfügung:

   * **[!UICONTROL Bestimmung einer speziellen Testversand-Zielgruppe]**: Ermöglicht Abfragen, die die Adressen in der Datenbank als Testversand-Zielgruppe filtern.
   * **[!UICONTROL Adressersetzung]**: Ermöglicht die Eingabe von Testadressen und Validierung des Inhalts mithilfe der Zielgruppen-Empfängerdaten. Die Ersatzadressen können manuell eingegeben oder aus der Dropdown-Liste ausgewählt werden. Die zugehörige [Auflistung](../../config/enumerations.md) ist **[!UICONTROL Substitutionsadresse (rcpAddress)]**.
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
