---
title: Merkmale des SMS-Kanals
description: Erfahren Sie mehr über die Merkmale des SMS-Kanals
feature: SMS
role: User
level: Intermediate
badge: label="Eingeschränkte Verfügbarkeit" type="Informative"
source-git-commit: 36bb1e2c9e2391065360c3cd2ad97612373ec0c2
workflow-type: tm+mt
source-wordcount: '1365'
ht-degree: 23%

---


# Merkmale des SMS-Kanals {#sms-channel}

>[!IMPORTANT]
>
>Diese Dokumentation gilt für Adobe Campaign v8.7.2 und höher.
>
>Für ältere Versionen lesen Sie bitte die [Campaign Classic v7-Dokumentation](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol).


## SMS-Typen {#sms-types}

Beim SMS-Versand über einen SMS-Provider treten drei verschiedene Arten von SMS auf:

* **SMS MT (Mobile Terminated)**: Dies ist eine SMS, die von Adobe Campaign über den SMPP-Provider an Mobiltelefone gesendet wird.
* **SMS MO (Mobile Originated)**: Dies ist eine SMS, die von einem Mobilgerät über den SMPP-Provider an Adobe Campaign gesendet wird.
* **SMS SR (Status Report) oder DR oder DLR (Delivery Receipt)**: Dies ist ein vom Mobiltelefon über den SMPP-Provider an Adobe Campaign gesendeter Rücksendungsbeleg, der angibt, dass die SMS erfolgreich empfangen wurde. Adobe Campaign erhält möglicherweise auch einen SR, der angibt, dass die Nachricht nicht zugestellt werden konnte, oft mit einer Fehlerbeschreibung.

Sie müssen zwischen Quittierungen (RESP PDU, Teil des SMPP-Protokolls) und SR unterscheiden. Ein SR ist eine Art SMS, die durchgehend über das Netzwerk gesendet wird, während eine Bestätigung nur eine Bestätigung ist, dass eine Übertragung erfolgreich war.

Sowohl Quittungen als auch SR können Trigger verursachen, wobei die Unterscheidung zwischen den beiden zur Fehlerbehebung beiträgt.

### Von einer SMS übertragene Informationen  {#sms-info}

Eine SMS enthält mehr Informationen als Text. Hier ist eine Liste der Informationen, die Sie in einer SMS erwarten können:

* Der Text, der auf 140 Byte begrenzt ist, was je nach Kodierung zwischen 70 und 160 Zeichen bedeutet. Details und Einschränkungen finden Sie unter [SMS-Textkodierung](#sms-text-encoding) weiter unten.
* Eine Empfängeradresse, manchmal auch ADC oder MSISDN genannt (der technische Name für &quot;Telefonnummer&quot;). Das ist die Nummer des Mobiltelefons, das die SMS erhält.
* Eine Absenderadresse, die als oADC oder manchmal als Absender-ID bezeichnet werden kann. Dabei kann es sich um eine Telefonnummer (bei Tagesgebrauch), eine Kurzwahlnummer (wenn diese über einen Provider gesendet wird) oder einen Namen handeln (dies ist eine optionale Funktion, in diesem Fall können Sie nicht auf die SMS antworten).
* Eine Markierung, die angibt, ob es sich bei der Nachricht um eine Flash-Nachricht handelt (eine Flash-Nachricht ist ein Popup, das nicht im Speicher gespeichert ist)
* Eine Markierung, die angibt, ob ein SR erwartet wird oder nicht.
* Ein Gültigkeitsdatum, nach dem keine Netzwerkgeräte erneut versuchen dürfen (nicht immer vorhanden oder respektiert).
* Ein data_coding -Feld, das die Kodierung des Textes angibt.

## SMS-Textkodierung {#sms-text-encoding}

>[!IMPORTANT]
>
>Die Kodierung von SMS ist ein riesiges, komplexes Thema mit vielen Fallen und nicht konformen Implementierungen!

Die erste Regel ist **, kontaktieren Sie den SMPP-Provider bei Kodierungsproblemen immer**. Nur sie verfügen über genaue Kenntnisse der von ihnen unterstützten Kodierung und spezielle Regeln, die aufgrund von Einschränkungen in ihrer technischen Plattform gelten können. Lassen Sie sie überprüfen, was Sie ihnen senden und was sie Ihnen zurückschicken, es ist der einzige Weg zu einer erfolgreichen und stabilen Verbindung.

SMS-Nachrichten verwenden eine spezielle 7-Bit-Kodierung, die häufig als GSM7-Kodierung bezeichnet wird.  Wikipedia hat [einen guten Artikel dazu (GSM 03.38 in Englisch)](https://en.wikipedia.org/wiki/GSM_03.38).

Im SMPP-Protokoll wird der GSM7-Text auf 8 Bit pro Zeichen erweitert, um die Fehlerbehebung zu erleichtern. Das SMSC packt ihn in 7 Bit pro Zeichen, bevor er an das Mobilgerät gesendet wird. Das bedeutet, dass das Feld short_message der SMS im SMPP-Frame bis zu 160 Byte lang sein kann, während es beim Versand im Mobilfunknetz auf 140 Byte begrenzt ist (das bedeutendste Bit wird einfach verworfen).

Bei Kodierungsproblemen sollten Sie Folgendes überprüfen:
* Stellen Sie zunächst sicher, dass Sie wissen, welche Zeichen zu welcher Kodierung gehören. GSM7 ist berüchtigt für seine teilweise Unterstützung diakritischer Zeichen (Akzente). Besonders im Französischen, wo é und è zu GSM7 gehören, ê, â oder ï aber nicht. Dasselbe gilt für Spanisch.
* Das C mit Cedilla (ç) ist nur in Großbuchstaben im GSM7-Alphabet vorhanden, aber einige Telefone rendern es in Kleinbuchstaben oder &quot;intelligenten&quot; Fällen: Die allgemeine Empfehlung ist, es vollständig zu vermeiden und die Cedilla zu entfernen (es ist noch sehr lesbar auf Französisch) oder auf UCS-2 zu wechseln.
* **Verwenden Sie kein ASCII in SMS!** , sofern nicht explizit vom SMPP-Provider angefordert: Diese Kodierung verschwendet Speicherplatz, da sie 8-Bit-Zeichen und eine geringere Abdeckung als GSM7 aufweist. Diese Kodierung kann für CDMA-Netzwerke (in Nordamerika verwendet) erforderlich sein.
* Latein-1 wird nicht immer unterstützt. Überprüfen Sie die Kompatibilität mit Ihrem SMPP-Provider, bevor Sie versuchen, Latin-1 zu verwenden.
* Nationale Sprachverschiebungstabellen werden vom Adobe Campaign-Connector nicht unterstützt. Sie müssen stattdessen UCS-2 oder eine andere data_coding verwenden.
* UCS-2 und UTF-16 werden oft per Telefon gemischt. Dies ist ein Problem für Personen, die Emojis und andere selten verwendete Zeichen senden, die nicht in UCS-2 vorhanden sind.
* Einige ältere Telefone verfügen nicht über Schriftzeichen für alle UCS-2-Zeichen. Neueste Smartphones neigen dazu, seltene Zeichen eher leicht anzuzeigen, ältere Smartphones haben häufig keine Emojis, und sehr alte Funktionstelefone haben im Allgemeinen nur Unterstützung, die auf das beschränkt ist, was in der Muttersprache des Landes nützlich ist, in dem sie gekauft wurden. Wenn Sie Emoji- oder ASCII-Kunst irgendeiner Art verwenden möchten, testen Sie sie vor dem Senden auf einer Vielzahl von Telefonen. Die Kampagnenvorschau simuliert keine fehlenden Glyphen und zeigt alle Symbole an, die im Webbrowser mit der Vorschau verfügbar sind.

Das Feld *data_coding* gibt an, welche Kodierung verwendet wird. Ein Hauptproblem besteht darin, dass der Wert 0 *Standard-SMSC-Kodierung* in der Spezifikation bedeutet, im Allgemeinen bedeutet er GSM7, aber das ist nicht immer der Fall. Überprüfen Sie beim SMPP-Provider, welche Kodierung mit data_coding = 0 verknüpft ist. Andere data_coding -Werte folgen in der Regel der Spezifikation. Sie müssen sich jedoch nur mit dem SMPP-Provider in Verbindung setzen.

Die maximale Größe einer Nachricht hängt von ihrer Kodierung ab. In dieser Tabelle sind alle relevanten Informationen zusammengefasst:

| Kodierung | Übliche Datenkodierung (data_coding) | Nachrichtengröße (Zeichen) | Größe der Teile für mehrteilige SMS | Verfügbare Zeichen |
|:-:|:-:|:-:|:-:|:-:|  
| GSM7 | 0 | 160 | 152 | GSM7-Standardzeichensatz + Erweiterung (erweiterte Zeichen benötigen 2 Zeichen) |
| Latin-1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 UTF-16 | 8 | 70 | 67 | Unicode (variiert von Telefon zu Telefon) |

## Mehrteilige SMS (lange SMS) {#multipart-sms}

Mehrteilige SMS (häufig als lange SMS bezeichnet) sind SMS, die in mehreren Teilen gesendet werden. Aufgrund technischer Einschränkungen im Mobilfunknetzprotokoll kann eine SMS nicht größer als 140 Byte sein (die Anzahl der Zeichen, die in eine SMS passen, finden Sie im Abschnitt SMS-Textkodierung unten). Daher müssen längere Nachrichten geteilt werden.

Jeder Teil einer langen Nachricht ist eine individuelle SMS. Diese Teile bewegen sich unabhängig voneinander durch das Netzwerk und werden vom empfangenden Mobiltelefon zusammengesetzt. Um weitere Zustellversuche und Verbindungsprobleme ordnungsgemäß zu handhaben, sendet Campaign Teile in umgekehrter Reihenfolge und bittet nur für den ersten Teil der Nachricht (der zuletzt gesendet wird) um einen SR. Da das Mobiltelefon nur eine Nachricht anzeigt, wenn es seinen ersten Teil erhalten hat, führen erneute Zustellversuche für weitere Teile nicht zu Duplikaten auf dem Mobiltelefon.

Die maximale Anzahl an SMS pro Nachricht kann pro Versand mithilfe der Einstellung Maximale Anzahl an SMS pro Nachricht in der Versandvorlage eingestellt werden. Nachrichten, die diesen Grenzwert überschreiten, schlagen beim Versand mit der Fehlermeldung &quot;SMS zu lang&quot; fehl.

Es gibt zwei Möglichkeiten, lange SMS zu senden:

* UDH
* message_payload

UDH ist die standardmäßige und empfohlene Methode zum Senden langer Nachrichten. In diesem Modus teilt der Connector die Nachricht in mehrere SUBMIT_SM-PDUs mit UDH-Informationen auf. Dieses Protokoll wird von Mobiltelefonen selbst verwendet, d. h. Campaign hat die größte Kontrolle über die Nachrichtenerstellung und kann so genau berechnen, wie viele Teile gesendet und wie sie aufgeteilt wurden.

*message_payload* ist eine Möglichkeit, die gesamte lange Nachricht in einer einzelnen SUBMIT_SM-PDU zu senden. Der Provider muss sie aufteilen, was bedeutet, dass Campaign nicht genau wissen kann, wie viele Teile gesendet wurden. Einige Provider benötigen diesen Modus und verwenden ihn nur, wenn sie UDH nicht unterstützen.

Weitere Informationen zum Protokoll und zu den Formaten finden Sie in der Beschreibung der Felder esm_class, short_message und message_payload der SUBMIT_SM PDU oben.

>[!NOTE]
>
>Adobe Campaign unterstützt zwar UDH und message_payload zum Senden, aber nur message_payload wird für eingehende SMS (MO) unterstützt.