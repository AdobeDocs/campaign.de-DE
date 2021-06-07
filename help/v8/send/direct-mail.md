---
product: Adobe Campaign
title: Senden von Briefpost mit Adobe Campaign
description: Erste Schritte mit Briefpost in Campaign
feature: Übersicht
role: Data Engineer
level: Beginner
source-git-commit: 67657fa19f3ff4594f7901f30d0d49ac75dcfbe0
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 31%

---

# Erstellen von Briefpost-Sendungen

Ein Briefpost-Versand erzeugt eine Ausgabedatei, die die Daten der Zielpopulation enthält. Sie können diese Datei dann für den Provider freigeben, der Nachrichten an die Zielgruppen sendet.

Die Schritte zum Generieren der Datei sind:

1. Versand erstellen

   Erstellen Sie einen Briefpost-Versand anhand der Vorlage. Sie können die integrierte Vorlage **[!UICONTROL Versand per Briefpost (Papier)]** duplizieren und konfigurieren.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html)

1. Audience festlegen

   Empfängerprofile müssen mindestens ihren Namen und ihre Anschrift enthalten.

   Postanschriften bestehen aus berechneten Feldern. Standardmäßig kann eine Anschrift bis zu sechs Zeilen aufweisen: Die erste Zeile enthält den Vor- und Nachnamen des Empfängers, die folgenden Zeilen die für die Zustellung erforderlichen Informationen (z. B. Straße und Zusätze) sowie in der letzten Zeile Postleitzahl und Ort.

   Eine Anschrift gilt als vollständig angegeben, wenn die Felder Name, Postleitzahl und Ort nicht leer sind.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html?lang=de)

1. Dateiinhalt festlegen

   Definieren Sie mithilfe des Extraktionsassistenten die Informationen (Spalten), die in die Ausgabedatei exportiert werden sollen.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html)

1. Versand überprüfen

   Überprüfen Sie das Ergebnis der Analyse und den Inhalt der Ausgabedatei.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html)

   Im Rahmen einer Marketingkampagne wird am Extraktionsdatum die Extraktionsdatei erstellt. Sie können den Inhalt der extrahierten Datei anzeigen, sie validieren oder das Format ändern und die Extraktion bei Bedarf neu starten. Nachdem die Datei validiert wurde, können Sie die Benachrichtigungs-E-Mail an den Router senden.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html#approving-an-extraction-file)

1. Versand starten

   Nachdem Sie die Extraktionsdatei validiert haben, klicken Sie auf **Versand bestätigen**, um den Versand zu starten.

   Durch die Bestätigung wird die Datenextraktion in der angegebenen Datei gestartet.

   Im Rahmen einer Marketing-Kampagne werden die Extraktionsdateien nach Erteilung aller Validierungen über einen speziellen Workflow erstellt, der standardmäßig automatisch startet, wenn ein Briefpost-Versand auf Extraktion wartet.

   [!DNL :arrow_upper_right:] Weitere Informationen finden Sie in der Dokumentation zu  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html#starting-an-offline-delivery)