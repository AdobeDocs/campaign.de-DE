---
title: SMS-Versandeinstellungen
description: Erfahren Sie, wie Sie einen SMS-Versand einrichten.
feature: SMS
role: User
level: Beginner, Intermediate
source-git-commit: af1d453179c2d739eca243b435dec90a4b8e2dd5
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 14%

---


# SMS-Versandeinstellungen {#sms-settings}

>[!IMPORTANT]
>
>Diese Dokumentation gilt für Adobe Campaign v8.7.2 und höher.
>
>Für ältere Versionen lesen Sie bitte die [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

Die technischen Parameter, die für einen SMS-Versand benötigt werden, sind:

* Routing: [das externe SMPP-Konto](smpp-external-account.md#smpp-connection-settings)

* [null ](#sms-tab)

Sie können all dies in einer Versandvorlage einrichten, um die Einstellungen für jede SMS-Versanderstellung zu vermeiden.

## Registerkarte **[!UICONTROL SMS]** konfigurieren {#sms-tab}

![](assets/send_settings.png){zoomable="yes"}

Hier finden Sie die Informationen, die Sie zum Ausfüllen dieses Formulars benötigen. Jedes Feld wird nachfolgend beschrieben:

* **[!UICONTROL Absenderadresse]**

  Dieses Feld ist optional. Es ermöglicht das Überschreiben der Absenderadresse (oADC). Der Inhalt dieses Felds wird im Feld *source_addr* der SUBMIT_SM PDU platziert.

  Das Feld ist durch die SMPP-Spezifikation auf 21 Zeichen begrenzt, einige Provider können jedoch längere Werte zulassen. Beachten Sie auch, dass in einigen Ländern sehr strenge Einschränkungen angewendet werden können (Länge, Inhalt, zulässige Zeichen usw.). Daher müssen Sie ggf. überprüfen, ob der hier platzierte Inhalt legal ist. Seien Sie besonders vorsichtig bei der Verwendung personalisierter Felder.

  Wenn dieses Feld leer gelassen wird, wird stattdessen der Wert des im externen Konto definierten Source-Zahlenfelds verwendet. Wenn beide Werte leer sind, bleibt das Feld *source_addr* leer.

* **[!UICONTROL Dienst- oder Programm-ID]**

  >[!NOTE]
  >
  >Von der Verwendung dieser Funktion wird abgeraten. Optionale SMPP-Parameter bieten eine wesentlich flexiblere Implementierung.
  >
  >Beide Funktionen können nicht gleichzeitig verwendet werden.

  Ermöglicht in Kombination mit der entsprechenden Einstellung des externen Kontos das Senden eines optionalen Parameters mit jedem MT. Dieses Feld definiert den Werteteil des TLV.

* **[!UICONTROL Übertragungsmodus]**

In diesem Feld wird die Art der SMS angegeben, die Sie übertragen möchten: normale oder Flash-Nachrichten, die auf dem Mobiltelefon oder der SIM-Karte gespeichert werden. Diese Einstellung wird im optionalen Feld dest_addr_subunit in der SUBMIT_SM PDU übertragen.

* **Flash** setzt den Wert auf 1. Es wird eine Flash-Nachricht gesendet, die auf dem Mobiltelefon angezeigt und nicht im Speicher abgelegt wird.
* **Normal** setzt den Wert auf 0. Es wird eine normale Nachricht gesendet.
* **Auf Mobilgerät speichern** setzt den Wert auf 2. Das Telefon wird angewiesen, die SMS im internen Speicher abzulegen.
* **Auf Gerät speichern** setzt den Wert auf 3. Das Telefon wird angewiesen, die SMS auf der SIM-Karte zu speichern.

* **[!UICONTROL Priorität, Kommunikationstyp]**

  Diese Felder werden vom erweiterten SMPP-Connector ignoriert.

* **[!UICONTROL Maximale Anzahl an SMS pro Nachricht]**

  Diese Einstellung funktioniert nur, wenn die Einstellung Nachrichten-Payload deaktiviert ist (weitere Informationen finden Sie in den Einstellungen für externe Konten ). Wenn die Nachricht mehr SMS als diesen Wert erfordert, wird ein Fehler ausgelöst.

  Das SMS-Protokoll begrenzt SMS auf 255 Teile, aber einige Mobiltelefone haben Probleme beim Zusammenstellen langer Nachrichten mit mehr als 10 Teilen (die Begrenzung hängt vom genauen Modell ab). Wenn Sie sicher sein möchten, gehen Sie nicht mehr als fünf Teile pro Nachricht.

  Aufgrund der Funktionsweise personalisierter Nachrichten in Adobe Campaign können die Nachrichtengrößen variieren, sodass eine Vielzahl sehr langer Nachrichten die Versandkosten erheblich erhöhen kann: Durch die Festlegung eines angemessenen Werts können diese Kosten gesenkt werden.

  Wenn Sie den Wert 0 angeben, wird der Grenzwert deaktiviert.

* **[!UICONTROL Optionale SMPP-Parameter (TLV)]**
Sie können zusätzliche Felder angeben, die als optionale SMPP-Parameter (TLV) gesendet werden sollen. Diese zusätzlichen Felder werden mit jedem MT gesendet und personalisierte Felder ermöglichen es, für jeden MT unterschiedliche Werte zu haben.
Die Tabelle enthält optionale Parameter, die mit jeder Nachricht gesendet werden können. Spalten enthalten die folgenden Informationen:
   * **Beschriftung**: Dies ist eine optionale, freie Beschriftung. Sie wird nicht an den Provider übermittelt. Sie können eine Textbeschreibung des Parameters angeben.
   * **Tag**: der Tag-Wert im Dezimalformat (z. B. 12345) oder im Hexadezimalformat mit dem Präfix 0x (z. B. 0x12ab). Tags können zwischen 0 und 65535 liegen. Fragen Sie den SMPP-Service Provider nach den von ihm unterstützten Tags.
   * **Wert**: Wert, der im optionalen Parameter gesendet werden soll. Dies ist ein personalisiertes Feld.
   * **Format**: Für den Parameter verwendete Kodierung. Sie können eine beliebige unterstützte Textkodierung oder die gängigsten Binärformate auswählen. Fragen Sie den SMPP-Dienstleister nach dem erforderlichen Format.
   * **Maximale Länge**: Maximale Anzahl der Byte für diesen Parameter. Dies wird bei binären Feldern ignoriert, da binäre Felder eine feste Größe haben.

* **[!UICONTROL Verwenden binärer Formate für TLV]**

  Campaign unterstützt das Senden von TLV im Binärformat. Die Binärdatei ist auf das Senden von Nummern beschränkt.

  Da bei personalisierten Feldern immer Text ausgegeben wird, muss das personalisierte Feld eine Dezimaldarstellung der Zahl enthalten (eine beliebige Zeichenfolge ist zulässig, solange sie nur Ziffern enthält). Die Werte können sowohl signiert als auch nicht signiert sein. Die Personalisierungsmaschine konvertiert sie einfach in die richtige binäre Darstellung.

  Bei Verwendung binärer Formate deaktivieren die Sonderwerte &quot;&quot;(leere Zeichenfolge), &quot;null&quot;und &quot;undefined&quot;das Feld vollständig, ohne einen Fehler auszulösen. In diesen 3 Sonderfällen wird das Tag überhaupt nicht übergeben. Dies ermöglicht die Übergabe eines bestimmten TLV nur für einige Nachrichten, wenn sorgfältig erstelltes JavaScript im Personalisierungsfeld verwendet wird.

  >[!NOTE]
  >
  >Binäre Formate werden immer in Big-Endian-Formulare kodiert.

## Erstellen eines SMS-Versands {#sms-delivery}

Gehen Sie wie folgt vor, um einen neuen SMS-Versand zu erstellen:

1. Erstellen Sie einen neuen Versand, beispielsweise über das Versand-Dashboard oder im Ordner Versand in **[!UICONTROL Explorer]**.  Standardmäßig wird sie als &quot;E-Mail-Versand&quot;bezeichnet.

1. Wählen Sie die für Ihren SMS-Versand erstellte Versandvorlage aus. [Weitere Informationen finden Sie hier](sms-mid-sourcing.md#sms-delivery-template).

   ![](assets/sms_create.png){zoomable="yes"}

<!-- * For standalone instance,  [learn more here](sms-standalone-instance.md#sms-delivery-template).
* For mid-sourcing infrastructure, -->

1. Benennen Sie Ihren Versand im Feld **[!UICONTROL Titel]** um und fügen Sie Informationen in das Feld **[!UICONTROL Versandcode]** und in die Liste **[!UICONTROL Art]** ein, falls dies für das Tracking erforderlich ist. Sie können Ihrem Versand auch eine **[!UICONTROL Beschreibung]** hinzufügen.

1. Klicken Sie auf die Schaltfläche **[!UICONTROL Weiter]** . Jetzt haben Sie alle Einstellungen Ihrer Vorlage in Ihrem Versand.

1. Sie können die Schaltfläche **[!UICONTROL Eigenschaften]** aktivieren, damit alle nach Bedarf eingerichtet sind. [Weitere Informationen zur Registerkarte &quot;SMS&quot;](#sms-tab)

![](assets/sms_settings.png){zoomable="yes"}

Jetzt können Sie Ihren [SMS-Inhalt](sms-content.md) konfigurieren.
