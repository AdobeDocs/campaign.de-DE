---
title: Senden von Briefpost mit Adobe Campaign
description: Erste Schritte mit Briefpost in Campaign
feature: Direct Mail
role: Data Engineer
level: Beginner
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 0a55d947a7646aab64ab2f9d0d09a6f930db576e
workflow-type: ht
source-wordcount: '412'
ht-degree: 100%

---

# Erstellen von Briefpost-Sendungen

Ein Briefpost-Versand erzeugt eine Extraktionsdatei, die die Daten der Zielpopulation enthält. Sie können diese Datei dann für den Provider freigeben, der Nachrichten an die Zielpopulationen sendet.

Die Schritte zum Generieren der Datei sind:

1. Versand erstellen

   Erstellen Sie anhand der Vorlage einen Briefpost-Versand. Sie können die integrierte Vorlage **[!UICONTROL Brief-Versand (Papier)]** duplizieren und konfigurieren.

   ![](../assets/do-not-localize/book.png) Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html?lang=de).{target=&quot;_blank&quot;}

1. Audience definieren

   Die Empfängerprofile müssen mindestens ihren Namen und ihre Anschrift enthalten.

   Postanschriften bestehen aus berechneten Feldern. Standardmäßig kann eine Anschrift bis zu sechs Zeilen aufweisen: Die erste Zeile enthält den Vor- und Nachnamen des Empfängers, die folgenden Zeilen die für die Zustellung erforderlichen Informationen (z. B. Straße und Zusätze) sowie in der letzten Zeile Postleitzahl und Ort.

   Eine Anschrift gilt als vollständig angegeben, wenn die Felder Name, Postleitzahl und Ort nicht leer sind.

   ![](../assets/do-not-localize/book.png) Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html?lang=de){target=&quot;_blank&quot;}.

1. Dateiinhalt festlegen

   Definieren Sie mithilfe des Extraktionsassistenten die Informationen (Spalten), die in die Ausgabedatei exportiert werden sollen.

   ![](../assets/do-not-localize/book.png) Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html?lang=de).{target=&quot;_blank&quot;}

1. Versand überprüfen

   Überprüfen Sie das Ergebnis der Analyse und den Inhalt der Ausgabedatei.

   ![](../assets/do-not-localize/book.png) Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html?lang=de).{target=&quot;_blank&quot;}

   Im Rahmen einer Marketing-Kampagne wird die Extraktionsdatei am Extraktionsdatum erstellt. Sie können den Inhalt der extrahierten Datei anzeigen, validieren oder das Format ändern und die Extraktion bei Bedarf neu starten. Nachdem die Datei validiert wurde, können Sie die Benachrichtigungs-E-Mail an den Router senden. Weitere Informationen finden Sie auf [dieser Seite](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=de).

1. Versand starten

   Nachdem Sie die Extraktionsdatei validiert haben, klicken Sie auf **Absendung bestätigen**. Über eine Bestätigungsnachricht können Sie den Versand starten.

   Mit der Bestätigung wird die Extraktion der Daten in die angegebene Datei gestartet.

   Im Rahmen einer Marketing-Kampagne werden die Extraktionsdateien nach Erteilung aller Validierungen über einen speziellen Workflow erstellt, der in einer Standardkonfiguration automatisch gestartet wird, wenn ein Briefpost-Versand auf die Extraktion wartet. Weitere Informationen finden Sie in [diesem Abschnitt](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=de).
