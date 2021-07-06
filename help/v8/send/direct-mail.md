---
product: Adobe Campaign
title: Senden von Briefpost mit Adobe Campaign
description: Erste Schritte mit Briefpost in Campaign
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: 67657fa19f3ff4594f7901f30d0d49ac75dcfbe0
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Erstellen von Briefpost-Sendungen

Ein Briefpost-Versand erzeugt eine Extraktionsdatei, die die Daten der Zielpopulation enthält. Sie können diese Datei dann für den Provider freigeben, der Nachrichten an die Zielpopulationen sendet.

Die Schritte zum Generieren der Datei sind:

1. Versand erstellen

   Erstellen Sie anhand der Vorlage einen Briefpost-Versand. Sie können die integrierte Vorlage **[!UICONTROL Brief-Versand (Papier)]** duplizieren und konfigurieren.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html?lang=de).

1. Audience definieren

   Die Empfängerprofile müssen mindestens ihren Namen und ihre Anschrift enthalten.

   Postanschriften bestehen aus berechneten Feldern. Standardmäßig kann eine Anschrift bis zu sechs Zeilen aufweisen: Die erste Zeile enthält den Vor- und Nachnamen des Empfängers, die folgenden Zeilen die für die Zustellung erforderlichen Informationen (z. B. Straße und Zusätze) sowie in der letzten Zeile Postleitzahl und Ort.

   Eine Anschrift gilt als vollständig angegeben, wenn die Felder Name, Postleitzahl und Ort nicht leer sind.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html?lang=de).

1. Dateiinhalt festlegen

   Definieren Sie mithilfe des Extraktionsassistenten die Informationen (Spalten), die in die Ausgabedatei exportiert werden sollen.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html?lang=de).

1. Versand überprüfen

   Überprüfen Sie das Ergebnis der Analyse und den Inhalt der Ausgabedatei.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html?lang=de).

   Im Rahmen einer Marketing-Kampagne wird die Extraktionsdatei am Extraktionsdatum erstellt. Sie können den Inhalt der extrahierten Datei anzeigen, validieren oder das Format ändern und die Extraktion bei Bedarf neu starten. Nachdem die Datei validiert wurde, können Sie die Benachrichtigungs-E-Mail an den Router senden.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=de#approving-an-extraction-file?lang=de).

1. Versand starten

   Nachdem Sie die Extraktionsdatei validiert haben, klicken Sie auf **Absendung bestätigen**. Über eine Bestätigungsnachricht können Sie den Versand starten.

   Mit der Bestätigung wird die Extraktion der Daten in die angegebene Datei gestartet.

   Im Rahmen einer Marketing-Kampagne werden die Extraktionsdateien nach Erteilung aller Validierungen über einen speziellen Workflow erstellt, der in einer Standardkonfiguration automatisch gestartet wird, wenn ein Briefpost-Versand auf die Extraktion wartet.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=de#starting-an-offline-delivery).