---
title: Merkmale des SMS-Kanals
description: Erfahren Sie mehr über die Merkmale des SMS-Kanals.
feature: SMS
role: User
level: Intermediate
exl-id: abab6f15-43ea-42fc-817b-8dbd88df82f7
source-git-commit: 6f29a7f157c167cae6d304f5d972e2e958a56ec8
workflow-type: tm+mt
source-wordcount: '1378'
ht-degree: 98%

---

# Merkmale des SMS-Kanals {#sms-channel}

>[!IMPORTANT]
>
>Diese Dokumentation gilt für Adobe Campaign Version 8.7.2 und höher. Informationen zum Wechsel vom alten zum neuen SMS-Connector finden Sie in dieser [Technote](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}
>
>Für ältere Versionen lesen Sie die [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/de/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## SMS-Typen {#sms-types}

Beim Senden von SMS über einen SMS-Provider kommen drei verschiedene Arten von SMS-Nachrichten vor:

* **SMS MT (Mobile Terminated)**: Hierbei handelt es sich um eine SMS, die von Adobe Campaign über den SMPP-Provider an Mobiltelefone versendet wird.
* **SMS MO (Mobile Originated)**: Hierbei handelt es sich um eine SMS, die von einem Mobilgerät über den SMPP-Provider an Adobe Campaign gesendet wird.
* **SMS SR (Status Report) oder DR bzw. DLR (Delivery Receipt)**: Hierbei handelt es sich um eine vom Mobilgerät über den SMPP-Provider an Adobe Campaign gesendete Rückbestätigung, die angibt, dass die SMS erfolgreich empfangen wurde. Adobe Campaign erhält möglicherweise auch einen SR, der angibt, dass die Nachricht nicht zugestellt werden konnte, oft mit einer Fehlerbeschreibung.

Sie müssen zwischen Quittierungen (RESP-PDU, Teil des SMPP-Protokolls) und SR unterscheiden. Ein SR ist eine Art SMS, die über das Netzwerk gesendet wird, während eine Quittierung nur bestätigt, dass eine Übertragung erfolgreich gewesen ist.

Sowohl Quittierungen als auch SR können Fehler auslösen, wobei es bei der Fehlerbehebung hilft, zwischen den beiden zu unterscheiden.

### Von einer SMS übertragene Informationen  {#sms-info}

Eine SMS enthält mehr Informationen als Text. Hier ist eine Liste der Informationen, die Sie in einer SMS erwarten können:

* Der Text, der auf 140 Byte begrenzt ist, was je nach Kodierung zwischen 70 und 160 Zeichen bedeutet. Details und Einschränkungen finden Sie unter [SMS-Textkodierung](#sms-text-encoding) weiter unten.
* Eine Empfängeradresse, auch als ADC oder MSISDN bezeichnet (der technische Name für „Telefonnummer“). Das ist die Nummer des Mobiltelefons, das die SMS erhält.
* Eine Absenderadresse, die auch als oADC oder Sender ID bezeichnet wird. Dabei kann es sich um eine Telefonnummer (im täglichen Gebrauch) handeln, um eine Kurzwahlnummer (wenn diese über einen Provider gesendet wird) oder um einen Namen (dies ist eine optionale Funktion; in diesem Fall können Sie nicht auf die SMS antworten).
* Ein Flag, das angibt, ob es sich bei der Nachricht um eine Flash-Nachricht handelt (eine Flash-Nachricht ist ein Popup, das nicht im Speicher abgelegt wird).
* Ein Flag, das angibt, ob ein SR erwartet wird oder nicht.
* Ein Gültigkeitsdatum, nach dem von den Netzwerkgeräten keine neuen Versuche mehr angestellt werden dürfen (nicht immer vorhanden oder berücksichtigt).
* Ein Feld „data_coding“, das die Codierung des Textes angibt.

## Codierung von SMS-Texten {#sms-text-encoding}

>[!IMPORTANT]
>
>Die Codierung von SMS ist ein riesiges, komplexes Themengebiet mit vielen Fallen und nicht konformen Implementierungen.

Die wichtigste Regel: **Wenden Sie sich bei Codierungsproblemen immer an den SMPP-Provider**. Nur dieser verfügt über genaue Kenntnisse der jeweils unterstützten Codierung und über spezielle Regeln, die aufgrund von Einschränkungen in der technischen Plattform des Providers gelten können. Lassen Sie den Provider prüfen, was zwischen Ihnen und dem Provider verschickt wird. Nur so ist eine erfolgreiche und stabile Verbindung möglich.

SMS-Nachrichten verwenden eine spezielle 7-Bit-Codierung, die häufig als GSM7-Kodierung bezeichnet wird. Auf Wikipedia gibt es [einen guten Artikel dazu (GSM 03.38)](https://de.wikipedia.org/wiki/GSM_03.38).

Im SMPP-Protokoll wird der GSM7-Text auf 8 Bit pro Zeichen erweitert, um die Fehlerbehebung zu erleichtern. Das SMSC packt ihn in 7 Bit pro Zeichen, bevor er an das Mobilgerät gesendet wird. Das bedeutet, dass das Feld „short_message“ der SMS im SMPP-Frame bis zu 160 Byte lang sein kann, während es beim Senden im Mobilfunknetz auf 140 Byte begrenzt ist (das höchstwertige Bit wird einfach verworfen).

Bei Codierungsproblemen sollten Sie Folgendes überprüfen:
* Zunächst sollten Sie wissen, welche Zeichen zu welcher Codierung gehören. GSM7 ist berüchtigt wegen seiner teilweisen Unterstützung diakritischer Zeichen (Akzente). Besonders im Französischen, wo é und è zu GSM7 gehören, ê, â oder ï aber nicht. Dasselbe gilt für Spanisch.
* Das C mit Unterhäkchen (ç) ist im GSM7-Alphabet nur in Großbuchstaben vorhanden, einige Telefone rendern es jedoch in Kleinbuchstaben oder „intelligenter“ Groß-/Kleinschreibung: Die allgemeine Empfehlung lautet, dies vollständig zu vermeiden und das Unterhäkchen zu entfernen (auf Französisch nach wie vor gut lesbar) oder auf UCS-2 umzusteigen.
* **Verwenden Sie kein ASCII in SMS,** es sei denn, dies wird vom SMPP-Provider ausdrücklich verlangt: Diese Codierung verschwendet Speicherplatz, da sie 8-Bit-Zeichen und eine geringere Abdeckung als GSM7 aufweist. Diese Codierung kann für (in Nordamerika verwendete) CDMA-Netzwerke erforderlich sein.
* Latin-1 wird nicht immer unterstützt. Überprüfen Sie die Kompatibilität mit Ihrem SMPP-Provider, bevor Sie versuchen, Latin-1 zu verwenden.
* Nationale Sprachverschiebungstabellen werden vom Adobe Campaign-Connector nicht unterstützt. Sie müssen stattdessen UCS-2 oder ein anderes data_coding verwenden.
* UCS-2 und UTF-16 werden von Telefonen oft gemischt. Dies ist ein Problem, wenn Emojis und andere selten verwendete Zeichen versendet werden, die nicht in UCS-2 vorhanden sind.
* Einige ältere Telefone haben nicht für alle UCS-2-Zeichen Schriftzeichen. Die neuesten Smartphones können seltene Zeichen in der Regel recht einfach anzeigen, ältere Smartphones haben aber häufig keine Emojis, und sehr alte Feature-Phones haben in der Regel nur eine begrenzte Unterstützung für die Zeichen, die in der Muttersprache des Landes, in dem sie gekauft wurden, nützlich sind. Wenn Sie Emoji- oder ASCII-Grafiken irgendeiner Art verwenden möchten, testen Sie sie vor dem Versand auf einer Vielzahl von Telefonen. Die Campaign-Vorschau simuliert keine fehlenden Glyphen und zeigt alle Symbole an, die im Webbrowser verfügbar sind, der die Vorschau anzeigt.

Das Feld *data_coding* gibt an, welche Codierung verwendet wird. Ein Hauptproblem besteht darin, dass der Wert 0 die *standardmäßige SMSC-Codierung* in der Spezifikation bedeutet. Dies bedeutet im Allgemeinen GSM7, aber das ist nicht immer der Fall. Erkundigen Sie sich beim SMPP-Provider, welche Kodierung mit data_coding = 0 verknüpft ist. Andere data_coding-Werte folgen in der Regel der Spezifikation. Sie müssen dies aber vom SMPP-Provider bestätigen lassen.

Die maximale Größe einer Nachricht hängt von ihrer Kodierung ab. In dieser Tabelle sind alle relevanten Informationen zusammengefasst:

| Kodierung | Übliche Datenkodierung (data_coding) | Nachrichtengröße (Zeichen) | Größe der Teile für mehrteilige SMS | Verfügbare Zeichen |
|:-:|:-:|:-:|:-:|:-:|  
| GSM7 | 0 | 160 | 152 | GSM7-Standardzeichensatz + Erweiterung (erweiterte Zeichen benötigen 2 Zeichen) |
| Latin-1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 UTF-16 | 8 | 70 | 67 | Unicode (variiert von Telefon zu Telefon) |

## Mehrteilige SMS (lange SMS) {#multipart-sms}

Mehrteilige SMS (häufig als lange SMS bezeichnet) sind SMS, die in mehreren Teilen gesendet werden. Aufgrund technischer Einschränkungen im Mobilfunknetzprotokoll kann eine SMS nicht größer als 140 Byte sein (die Anzahl der Zeichen, die in eine SMS passen, finden Sie im Abschnitt „Codierung von SMS-Texten“ unten). Daher müssen längere Nachrichten aufgeteilt werden.

Jeder Teil einer langen Nachricht ist eine individuelle SMS. Diese Teile bewegen sich unabhängig voneinander durch das Netzwerk und werden vom empfangenden Mobiltelefon zusammengesetzt. Um weitere Zustellversuche und Verbindungsprobleme ordnungsgemäß zu handhaben, sendet Campaign Teile in umgekehrter Reihenfolge und fragt nur für den ersten Teil der Nachricht (der zuletzt gesendet wird) nach einem SR. Da das Mobiltelefon nur eine Nachricht anzeigt, wenn es den ersten Teil empfangen hat, führen erneute Zustellversuche für weitere Teile nicht zu Duplikaten auf dem Mobiltelefon.

Die maximale Anzahl an SMS pro Nachricht kann pro Versand mithilfe der Einstellung „Maximale Anzahl an SMS pro Nachricht“ in der Versandvorlage eingestellt werden. Nachrichten, die diesen Grenzwert überschreiten, schlagen beim Versand mit der Fehlermeldung &quot;SMS zu lang&quot; fehl.

Es gibt zwei Möglichkeiten, lange SMS zu senden:

* UDH
* message_payload

UDH: die standardmäßige und empfohlene Methode zum Senden langer Nachrichten. In diesem Modus teilt der Connector die Nachricht in mehrere SUBMIT_SM-PDUs mit UDH-Informationen auf. Dieses Protokoll wird von Mobiltelefonen selbst verwendet, was bedeutet, dass Campaign die meiste Kontrolle über die Nachrichtengenerierung hat und somit genau berechnen kann, wie viele Teile gesendet und wie sie aufgeteilt wurden.

*message_payload*: Möglichkeit, die gesamte lange Nachricht in einer einzigen SUBMIT_SM-PDU zu senden. Der Provider muss sie aufteilen, was bedeutet, dass Campaign nicht genau wissen kann, wie viele Teile gesendet wurden. Einige Provider erfordern diesen Modus. Verwenden Sie ihn nur, wenn sie UDH nicht unterstützen.

Weitere Informationen zum Protokoll und den Formaten finden Sie in der Beschreibung der Felder esm_class, short_message und message_payload der SUBMIT_SM-PDU.

>[!NOTE]
>
>Adobe Campaign unterstützt zwar UDH und message_payload zum Senden, aber für eingehende SMS (MO) wird nur message_payload unterstützt.
