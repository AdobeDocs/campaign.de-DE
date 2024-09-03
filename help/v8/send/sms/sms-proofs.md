---
title: SMS-Testsendungen
description: Erfahren Sie, wie Sie Testsendungen eines SMS-Versands durchführen.
feature: SMS
role: User
level: Beginner, Intermediate
source-git-commit: 24a6d56a79995cd0113d8438d1bd3314a3872e35
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 8%

---


# Testversand eines SMS-Versands {#sms-proof}

Adobe empfiehlt dringend, einen Validierungszyklus für Sendungen einzurichten. Vergewissern Sie sich, dass Ihr Inhalt validiert wurde, bevor er an Ihre Audience gesendet wird.

Sie können einen Testversand für Ihren SMS-Versand durchführen, um ihn zu validieren:

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Testversand durchführen]** . Daraufhin wird ein Fenster geöffnet

   ![](assets/proof_targeting.png){zoomable="yes"}

   Sie haben mehrere Modi, um einen Testversand durchzuführen:

   * **[!UICONTROL Definition einer speziellen Testversand-Zielgruppe]**: ermöglicht die Abfrage mit Filtern der Datenbankadressen als Testversand-Zielgruppe
   * **[!UICONTROL Adressersetzung]**: ermöglicht die Eingabe Ihrer Testadressen und die Verwendung der Zielgruppenempfänger-Daten zur Überprüfung des Inhalts. Die Ersatzadressen können manuell eingegeben oder aus der Dropdown-Liste ausgewählt werden. Die zugehörige Auflistung ist **[!UICONTROL Ersatzadresse (rcpAddress)]**.
Standardmäßig wird die Ersetzung nach dem Zufallsprinzip durchgeführt. Sie können jedoch über das Symbol **[!UICONTROL Detail]** einen bestimmten Empfänger aus der Hauptzielgruppe auswählen.
   * **[!UICONTROL Testadressen]**: ermöglicht Ihnen den Zugriff auf Testadressen als Testversand-Zielgruppe. Diese Adressen können aus einer Datei importiert oder manuell eingegeben werden.
   * **[!UICONTROL Spezifische Ziel- und Testadressen]**: ermöglicht die Kombination von Testadressen und -adressen aus einem Empfänger.

1. Fügen Sie nach Auswahl Ihres **[!UICONTROL Targeting-Modus]** Ihre Testadressen entsprechend hinzu.

   Im folgenden Beispiel wählen wir **[!UICONTROL Definition einer bestimmten Testversand-Zielgruppe]** und fügen einen Empfänger hinzu:

   ![](assets/proof_recipient.png){zoomable="yes"}

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Analysieren]** .
Adobe Campaign führt die gesamte Kontrolle aus, bevor der Testversand validiert wird. Am Ende der Analyse ist die Schaltfläche **[!UICONTROL Versand bestätigen]** angeklickt.

   ![](assets/proof_analyze.png){zoomable="yes"}

1. Um den Testversand Ihres SMS-Versands durchzuführen, wählen Sie die Schaltfläche **[!UICONTROL Versand bestätigen]** aus.

Wenn in dieser Phase alles in Ordnung ist, können Sie fortfahren und [Ihren SMS-Versand an die Audience senden](sms-audience.md).
