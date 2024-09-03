---
title: Externe SMPP-Kontoeinstellungen
description: Erfahren Sie, wie Sie das externe SMPP-Konto konfigurieren.
feature: SMS
role: User
level: Intermediate
badge: label="Eingeschränkte Verfügbarkeit" type="Informative"
source-git-commit: 36bb1e2c9e2391065360c3cd2ad97612373ec0c2
workflow-type: tm+mt
source-wordcount: '3652'
ht-degree: 27%

---


# Externe SMPP-Kontoeinstellungen {#smpp-external-account}

Adobe Campaign verwendet das SMPP-Protokoll, um SMS an einen Dienstleister zu senden.

>[!IMPORTANT]
>
>Adobe Campaign unterstützt die SMPP-Protokollversion 3.4.


Der SMS-Connector in Adobe Campaign bietet viele Möglichkeiten, sein Verhalten anzupassen, um mit den meisten SMPP-Anbietern kompatibel zu sein, die in der Regel etwas von der offiziellen Spezifikation abweichen.

>[!IMPORTANT]
>
>Das Einrichten einer Verbindung zu einem neuen Provider erfordert möglicherweise einige technische Fähigkeiten, Kenntnisse über TCP, die binäre, hexadezimale Darstellung und Textkodierungen. Es erfordert auch eine aktive Zusammenarbeit mit dem Provider.

Die Netzwerkgeräte auf der Seite des SMS-Dienstleisters werden oft als SMSC bezeichnet.

## Verbindungsparameter {#smpp-connection-settings}

![](assets/smpp_connection_settings.png){zoomable="yes"}

Im Folgenden finden Sie die Parameter und ihre Rolle, die zum Einrichten der Verbindung erforderlich sind:

* **Name der SMSC-Implementierung**: Legt den Namen der SMSC-Implementierung fest. Sollte auf den Namen Ihres Providers eingestellt werden. Die Rolle dieses Felds wird im Abschnitt Verwaltung von SMPP-Fehlern beschrieben.
* **Server**: Der DNS-Name oder die IP-Adresse des Servers, mit dem eine Verbindung hergestellt werden soll.
* **Port**: Der TCP-Port, mit dem eine Verbindung hergestellt werden soll.
* **Konto**: Die Anmeldung der Verbindung. Wird im Feld system_id der BIND PDU übergeben.
* **Kennwort**: Kennwort der SMPP-Verbindung. Im Passwortfeld der BIND PDU übergeben.
* **Systemtyp**: Wert, der im Feld system_type der BIND PDU übergeben wird. Einige Provider benötigen hier einen bestimmten Wert.
* **Anzahl untergeordneter MTA-Verbindungen**: Damit wird definiert, wie viele Verbindungen pro sendendem Thread geöffnet werden.
Die Gesamtanzahl der Verbindungen kann mithilfe dieser Formel berechnet werden:
  *Gesamtanzahl der Verbindungen = Anzahl der SMS-Prozesse * Anzahl der Versand-Threads * Anzahl untergeordneter MTA-Verbindungen*

   * Die Anzahl der SMS-Prozesse beträgt normalerweise 1. In einigen sehr leistungsstarken Instanzen können mehrere SMS-Prozesse parallel gestartet werden.
   * Die Anzahl der Versand-Threads wird in serverConf festgelegt (Einstellung sendThreads ). Der Standardwert ist 1.
   * Die Anzahl der untergeordneten MTA-Verbindungen ist diese Einstellung im externen Konto.

  Bei Standardwerten legt diese Einstellung direkt die Anzahl der Verbindungen fest.

Im **Transceiver-Modus** ist dies die Gesamtanzahl der Verbindungen.

Im Modus **Transmitter+Receiver** wird dadurch die Anzahl der Sender-/Receiver-Paare definiert (ein Paar = ein Transmitter + ein Receiver).
Es gibt keine Möglichkeit, das Gleichgewicht zwischen Sender und Empfängern zu verändern.

* **Nachrichten über einen dedizierten Prozess senden**:
Für Adobe Campaign v8.7.2 und höher sollte diese Option immer aktiviert sein. Die Verarbeitung von Nachrichten hat viele Auswirkungen.
* **SMPP-Verbindungsmodus**:
Stellen Sie die Verbindung im Transceiver-Modus oder im getrennten Modus Transmitter + Receiver ein.
   * Transmitter+Receiver (oder TX+RX): Es werden zwei separate TCP-Verbindungen zum Senden und Empfangen von Nachrichten verwendet.
   * Transceiver (oder TRX): Es wird eine einzelne TCP-Verbindung zum Senden und Empfangen von Nachrichten verwendet.
* **Verwenden Sie unterschiedliche Parameter für den Empfänger**:
Nur im Modus Transmitter + Receiver verfügbar.
Wenn das Kontrollkästchen deaktiviert ist, werden für Sender und Empfänger dieselben Einstellungen verwendet. Wenn das Kontrollkästchen aktiviert ist, gelten die Standardeinstellungen nur für den Sender, während die Empfängereinstellungen nur für den Empfänger gelten.
* **Receiver-Server, Port, Konto, Kennwort, Systemtyp**
Diese Einstellungen gelten für den Empfänger im Modus Transmitter + Receiver . Sie funktionieren wie der Senderteil, siehe oben für [weitere Details](#smpp-connection-settings).
* **Aktivieren Sie ausführliche SMPP-Verfolgung in der Protokolldatei**
Wenn diese Option aktiviert ist, werden zusätzliche Protokolle in die Protokolldatei ausgegeben. Dies ist sehr nützlich für die Fehlerbehebung, sollte jedoch bei Instanzen mit hohem Durchsatz deaktiviert bleiben, wenn keine Fehlerbehebung erforderlich ist.

## Parameter des SMPP-Kanals {#smpp-channel-settings}

![](assets/smpp_channel_settings.png){zoomable="yes"}

### Transliteration der Zeichen zulassen

Bei der Transliteration werden äquivalente Zeichen zu fehlenden Zeichen gefunden. Beispielsweise fehlt das französische Zeichen &quot;ê&quot; (e mit Zirkumflex-Akzent) in der GSM-Kodierung, kann jedoch durch &quot;e&quot;ersetzt werden, ohne die Lesbarkeit zu stark zu beeinträchtigen.

Wenn dieses Kontrollkästchen deaktiviert ist, schlägt die Textkodierung fehl, wenn die Zeichenfolge nicht exakt kodiert werden kann.

Wenn dieses Kontrollkästchen aktiviert ist, versucht die Textkodierung, die Zeichenfolge in eine ungefähre Version zu konvertieren, anstatt fehlzuschlagen. Wenn einige Zeichen in der Zielkodierung keine Entsprechung haben, schlägt die Textkodierung fehl.

Eine allgemeinere Erläuterung des Kodierungsprozesses finden Sie unter dem Parameter [Definieren eines bestimmten Kodierungs-Mapping](#mapping-encodings).

### Anrufernummer

Definiert die Standardquelladresse für Nachrichten. Diese Einstellung gilt nur, wenn die Quellnummer im Versand leer gelassen wurde. Standardmäßig wird das Feld für die Anrufernummer nicht übergeben, sodass der Provider es durch die Kurzwahlnummer ersetzt.

Dadurch wird die Funktion zum Überschreiben der Absenderadresse/oADC aktiviert.

### Anrufer-TON/NPI, Empfänger-TON/NPI

TON (Type of Number = Nummerntyp) und NPI (Numbering Plan Indicator = Nummerierungsplanindikator) (beschrieben in Abschnitt 5.2.5 der Spezifikation von SMPP Version 3.4). Diese Werte sollten entsprechend den Anforderungen des Providers eingestellt werden.

Sie werden unverändert in den Feldern source_addr_ton, source_addr_npi, dest_addr_ton und dest_addr_npi der SUBMIT_SM PDU übertragen.

### Diensttyp

Dieses Feld wird unverändert im Feld service_type der SUBMIT_SM PDU übertragen. Stellen Sie dies auf die Anforderungen des Providers ein.

## Durchsatz und Verzögerungen {#smpp-delays}

![](assets/smpp_throughput.png){zoomable="yes"}

Diese Einstellungen steuern alle Zeitaspekte des SMPP-Kanals. Einige Provider erfordern eine sehr genaue Kontrolle der Nachrichtenrate, des Fensters und der Wiederholungszeiten. Daher sollten diese Einstellungen auf Werte gesetzt werden, die mit der Kapazität des Providers und den in seinem Vertrag angegebenen Bedingungen übereinstimmen.

### Übertragungsfenster

Das Fenster ist die Anzahl der SUBMIT_SM PDUs, die gesendet werden können, ohne auf eine passende SUBMIT_SM_RESP zu warten.

Beispiel einer Übertragung mit einem maximalen Fenster von 4:

![](assets/sms_sending_window.png){zoomable="yes"}

Das Fenster hilft bei der Erhöhung des Durchsatzes, wenn die Netzwerkverbindung eine hohe Latenz aufweist. Der Wert des Fensters muss mindestens der Anzahl der SMS entsprechen, multipliziert mit der Latenz des Links (in Sekunden), sodass der Connector nie auf ein SUBMIT_SM_RESP wartet, bevor er die nächste Nachricht sendet.

Wenn das Fenster zu groß ist, können Sie bei Verbindungsproblemen (selten) mehr doppelte Nachrichten senden. Außerdem haben die meisten Provider ein sehr strenges Limit für das Fenster und lehnen Nachrichten ab, die das Limit überschreiten.

Berechnung der optimalen Formel für das Übertragungsfenster:

Messen Sie die maximale Latenz zwischen SUBMIT_SM und SUBMIT_SM_RESP.
Multiplizieren Sie diesen Wert (in Sekunden) mit dem maximalen MT-Durchsatz: Dies ergibt den optimalen Wert für das Übertragungsfenster.
Beispiel: Wenn Sie für den maximalen MT-Durchsatz 300 SMS/s festgelegt haben und zwischen SUBMIT_SM und SUBMIT_SM_RESP im Durchschnitt 100 ms Latenz besteht, wäre der optimale Wert 300×0.1 = 30.

Im Zweifelsfall sollten Sie ein größeres Fenster bevorzugen, um Leistungsprobleme zu vermeiden.

### Maximaler Durchsatz an MT

Maximale Anzahl an MT pro Sekunde und pro Verbindung. Diese Einstellung wird genau eingehalten. Der MTA wird beim Nachrichtenversand diese Grenze nie überschreiten. Diese Einstellung ist nützlich für Provider, die eine genaue Drosselung benötigen.

Um die Gesamtdurchsatzgrenze zu ermitteln, multiplizieren Sie diese Zahl mit der Gesamtanzahl der Verbindungen (siehe obige Formel).

0 bedeutet keine Begrenzung, der MTA sendet MT so schnell wie möglich.

Es wird allgemein empfohlen, diese Einstellung unter 1000 zu halten, da es nicht möglich ist, einen präzisen Durchsatz über dieser Zahl zu gewährleisten, es sei denn, es wird ein ordnungsgemäßer Vergleich der endgültigen Architektur durchgeführt und ein speziell angeforderter SMPP-Provider durchgeführt. Möglicherweise ist es besser, die Anzahl der Verbindungen auf über 1.000 MT/s zu erhöhen.

### Dauer bis zu einer erneuten Verbindung

Wenn die TCP-Verbindung verloren geht, wartet der Connector diese Anzahl von Sekunden, bevor er versucht, eine Verbindung herzustellen.

### Gültigkeitsdauer der MT

Dies ist die Zeitüberschreitung zwischen SUBMIT_SM und der zugehörigen SUBMIT_SM_RESP. Wenn der RESP nicht rechtzeitig empfangen wird, gilt die Nachricht als fehlgeschlagen und die globale Wiederholungsrichtlinie des MTA wird angewendet.

### Bind-Timeout

Zeitüberschreitung zwischen dem TCP-Verbindungsversuch und der BIND_*_RESP-Antwort. Wenn eine Zeitüberschreitung auftritt, wird die Verbindung vom Campaign-Connector geschlossen und es wird auf die Zeit vor einer erneuten Verbindung gewartet, bevor ein erneuter Versuch unternommen wird.

### enquire_link-Zeitraum

inquire_link ist eine spezielle Art von PDU, die gesendet wird, um die Verbindung aktiv zu halten. Dieser Zeitraum wird in Sekunden angegeben. Der Campaign-Connector sendet nur inquire_link, wenn die Verbindung inaktiv ist, um Bandbreite zu sparen. Wenn nach der doppelten Zeitdauer keine RESP empfangen wird, wird die Verbindung als unterbrochen betrachtet und ein Wiederverbindungsprozess ausgelöst.

## Kodierungs-Mapping {#mapping-encodings}

Einzelheiten zur Textkodierung finden Sie im Abschnitt [SMS-Textkodierung](sms-channel.md#sms-text-encoding) .

Diese Einstellung ermöglicht die Definition eines benutzerdefinierten Kodierungs-Mappings, das von der Spezifikation abweicht. Sie können eine Liste von Kodierungen zusammen mit ihrem data_coding -Wert deklarieren. Der MTA versucht, die Kodierung mit der ersten Kodierung in der Liste durchzuführen. Wenn dies fehlschlägt, versucht er, die nächste Kodierung in der Liste zu verwenden usw.. Wenn keine Kodierung zum Kodieren der Nachricht verwendet werden kann, tritt ein Fehler auf. Sobald die Kodierung gefunden wurde, erstellt der MTA die SUBMIT_SM-PDU mit dem kodierten Text und dem Feld data_coding , das mit dem in der Tabelle angegebenen Wert eingestellt ist.

Die Reihenfolge der Elemente in der Tabelle ist wichtig: Kodierungen werden von oben nach unten versucht. Sie sollten die billigste oder am besten empfohlene Kodierung an die Spitze der Liste setzen, gefolgt von immer teureren (oder weniger wünschenswerten) Kodierungen.

Beachten Sie, dass UCS-2 niemals fehlschlagen wird, da es alle in Campaign unterstützten Zeichen kodieren kann. Bitte beachten Sie, dass die maximale Länge einer UCS-2-SMS viel kleiner ist (nur 70 Zeichen).

Sie können diese Einstellung auch verwenden, um zu erzwingen, dass eine bestimmte Kodierung immer verwendet wird, indem Sie in der Mapping-Tabelle nur eine Zeile deklarieren.

Das standardmäßige Mapping, das verwendet wird, wenn das Kontrollkästchen nicht aktiviert ist, entspricht der folgenden Tabelle:

| data_coding | Kodierung |
|:-:|:-:|
| 0 | GSM |
| 8 | UCS-2 |

Das bedeutet, dass der MTA versucht, die Nachricht im GSM zu kodieren, wenn sie erfolgreich ist, sendet er sie mit data_coding auf 0.

Wenn die Nachricht nicht in GSM kodiert werden kann, wird sie in UCS-2 kodiert und data_coding auf 8 gesetzt.

## SMSC-Besonderheiten {#smsc-specificities}

![](assets/smsc_specificities.png){zoomable="yes"}

### message_payload aktivieren

Wenn diese Option deaktiviert ist, werden lange SMS vom MTA aufgeteilt und in mehreren SUBMIT_SM-PDUs mit UDH gesendet. Die Nachricht wird vom Mobiltelefon entsprechend den UDH-Daten neu zusammengesetzt.

Wenn diese Option aktiviert ist, werden lange SMS in einer SUBMIT_SM-PDU gesendet, wobei der Text in das optionale Feld message_payload eingefügt wird (weitere Informationen finden Sie in der SMPP-Spezifikation ).

Wenn diese Funktion aktiviert ist, kann Campaign SMS-Teile nicht einzeln zählen: Alle Nachrichten werden in einem Teil als gesendet gezählt.

### Vollständige Telefonnummer senden

Wenn dieses Kontrollkästchen nicht aktiviert ist, werden nur Ziffern der Telefonnummer an den Provider gesendet (Feld destination_addr des Felds SUBMIT_SM ). Dies ist das Standardverhalten, da der internationale Zahlenindikator (normalerweise ein &quot;+&quot;-Präfix) in SMPP durch TON- und NPI-Felder ersetzt wird.

Wenn das Kontrollkästchen aktiviert ist, wird die Telefonnummer unverändert gesendet, ohne Vorverarbeitung (und potenzielle Leerzeichen, &quot;+&quot;-Präfix oder Pfund-/Hash-/Sternzeichen).

Diese Funktion wirkt sich auch auf das Verhalten der Quarantänefunktion für automatische Antworten aus: Wenn das Kontrollkästchen nicht aktiviert ist, wird den in die Quarantänetabelle eingefügten Telefonnummern ein &quot;+&quot;-Präfix hinzugefügt, um das &quot;+&quot;-Präfix zu kompensieren, das vom SMPP-Protokoll selbst aus der Telefonnummer entfernt wird.

### Bind TON/NPI

TON (Type of Number = Nummerntyp) und NPI (Numbering Plan Indicator = Nummerierungsplanindikator) (beschrieben in Abschnitt 5.2.5 der Spezifikation von SMPP Version 3.4). Diese Werte sollten entsprechend den Anforderungen des Providers eingestellt werden.

Sie werden unverändert in den Feldern addr_ton und addr_npi der BIND PDU übertragen.

### Adressenbereich

Wird im Feld address_range der BIND PDU unverändert gesendet. Dieser Wert sollte entsprechend den Anforderungen des Providers eingestellt werden.

### Anzahl ungültiger ID-Quittierungen

Begrenzt die Anzahl der &quot;Nachrichten-ID ungültig&quot; DELIVER_SM_RESP, die für einen einzelnen SR gesendet werden können. **Dies sollte nur zur Fehlerbehebung als Problemumgehung verwendet** und unter normalen Bedingungen auf 0 gesetzt werden.

Detaillierte Erläuterung: Angenommen, Sie legen diese Einstellung auf 2 fest:

* Der Provider sendet einen SR (DELIVER_SM) mit der ID &quot;1234&quot;
* Die Kennung &quot;1234&quot;konnte nicht in der Datenbank gefunden werden.
* Der Connector zählt für diese ID den Fehler &quot;Ungültige ID&quot;, daher wird DELIVER_SM_RESP mit dem Fehlercode &quot;Nachrichten-ID ungültig&quot; (normales Verhalten) gesendet.
* Der Provider versucht denselben SR mit der ID &quot;1234&quot; erneut.
* Die Kennung &quot;1234&quot; konnte noch nicht in der Datenbank gefunden werden.
* Der Connector zählt für diese ID den Fehler &quot;Ungültige ID&quot;, daher wird DELIVER_SM_RESP &quot;OK&quot; gesendet, auch wenn diese nicht korrekt verarbeitet wurde.

Diese Funktion dient dazu, SR-Puffer auf der Provider-Seite zu leeren, wenn ungültige SR-Regeln legitime Nachrichten blockieren, die nicht verarbeitet werden können.

Wenn dieses Feld auf 0 gesetzt wird, wird der Mechanismus deaktiviert, sodass &quot;Nachrichten-ID ungültig&quot;immer zurückgegeben wird. Dies ist das normale Verhalten.

Wenn Sie dieses Feld auf 1 setzen, antwortet der Connector immer mit &quot;OK&quot;, auch wenn die ID ungültig ist. Dieser Wert sollte auf 1 gesetzt werden, der nur unter Aufsicht für die Fehlerbehebung und für die Mindestdauer verwendet wird, z. B. um ein Problem auf der Seite des Providers zu beheben.

### Regex zur ID-Extraktion im SR

Das SR-Format wird von der SMPP-Protokollspezifikation nicht strikt durchgesetzt. Es handelt sich lediglich um eine Empfehlung, die in Anhang B der Spezifikation beschrieben ist. Aus diesem Grund formatieren einige SMPP-Implementoren dieses Feld unterschiedlich, sodass Campaign eine Möglichkeit benötigt, das richtige Feld zu extrahieren.

Standardmäßig werden bis zu 10 alphanumerische Zeichen nach &quot;id:&quot;erfasst.

Der Regex muss über genau eine Erfassungsgruppe verfügen (ein Teil, der in Klammern steht). Klammern müssen den Teil umschließen, der der ID entspricht. Das Regex-Format ist PCRE.

Achten Sie beim Anpassen dieser Einstellung darauf, so viel Kontext wie möglich einzubeziehen, um Fehlauslösungen zu vermeiden. Wenn bestimmte Präfixe vorhanden sind (z. B. &quot;id:&quot;im Standard), schließen Sie sie in den Regex ein. Verwenden Sie außerdem so weit wie möglich Worttrennzeichen (\b), um zu vermeiden, dass Text in der Mitte eines Wortes erfasst wird.

Wenn nicht genügend Kontext in den Regex aufgenommen wird, kann es zu einer kleinen Sicherheitslücke kommen: Der tatsächliche Inhalt der Nachricht kann in den SR eingeschlossen werden. Wenn Sie also nur ein bestimmtes ID-Format ohne Kontext verwenden (z. B. eine UUID), wird möglicherweise der eigentliche Textinhalt (z. B. eine UUID, die in das Textfeld eingebettet ist) anstelle der ID analysiert.

### Regex zur Status-Extraktion im SR

Dieser Regex erfasst den Status aus dem Textfeld der SR-Nachrichten.

Standardmäßig werden zwischen 5 und 15 Zeichen nach &quot;stat:&quot;erfasst.

Der Regex muss über **genau eine Erfassungsgruppe** verfügen (ein Teil, der in Klammern steht). Klammern müssen den Teil umschließen, der dem Status entspricht. Das Regex-Format ist PCRE.

### Regex angewendet, um Erfolgsstatus zu ermitteln

Dieser Regex wird auf das Ergebnis des vorherigen Regex angewendet (&quot;Extraktionsregex des Status&quot;). Wenn der Regex übereinstimmt, wird die Nachricht als erfolgreich betrachtet.

Standardmäßig stimmt sie mit allem überein, was mit &quot;DELIV&quot;beginnt. Sie entspricht dem Standardwert &quot;DELIVRD&quot;.

### Regex angewendet, um den Fehlerstatus zu ermitteln

Dieser Regex wird auf das Ergebnis des vorherigen Regex angewendet (&quot;Extraktionsregex des Status&quot;). Wenn der Regex übereinstimmt, wird die Nachricht als fehlerhaft betrachtet.

Standardmäßig werden alle in der Spezifikation beschriebenen Fehlerstatus abgeglichen.

### Regex zur Fehlercode-Extraktion im SR

Dieser Regex erfasst den Fehler-Code aus dem Textfeld der SR-Nachrichten.

Fehlercodes können in der Versandlogqualifizierung qualifiziert werden.

Standardmäßig werden 3 Zeichen nach &quot;err:&quot;erfasst.

### ID-Format in der MT-Quittierung (resp)

Dies gibt das Format der ID an, die im Feld message_id der SUBMIT_SM_RESP PDU zurückgegeben wird.

* **Nicht ändern**: Die ID wird unverändert als ASCII-kodierter Text wie in der Datenbank gespeichert. Es findet keine Vorverarbeitung oder Filterung statt.
* **Dezimalzahl**: Die ID wird als Dezimalzahl in ASCII-Form erwartet. Führende und nachfolgende Leerzeichen und führende Nullen werden bei Verwendung dieser Einstellung entfernt.
* **Hexadezimalzahl**: Die ID wird als Hexadezimalzahl in ASCII-Form erwartet, ohne führendes 0x und nachgestelltes h. Die ID wird dann in eine Dezimalzahl umgewandelt, bevor sie in der Datenbank gespeichert wird.
* **Hexadezimaler String**: Die ID muss ein ASCII-kodierter Text sein, der selbst eine Zeichenfolge ist, die als Hexadezimalwert kodiert wurde. In der PDU finden Sie beispielsweise 0x34 0x31 0x34 0x32 0x34 0x33, was zu ASCII &quot;414243&quot;führt. Dann wird dieser String als hexadezimaler String mit Bytes dekodiert und Sie erhalten &quot;ABC&quot;: Sie speichern die ID. &quot;ABC&quot;in der Datenbank.

### ID-Format im SR

Dies gibt das Format der ID an, die vom Regex zur Extraktion der ID im SR erfasst wird. Die Werte haben die gleiche Bedeutung und das gleiche Verhalten wie das Format im MT oben.

### SR-Kennung oder Fehlercode in einem optionalen Feld speichern

Wenn diese Option aktiviert ist, wird der Inhalt der optionalen Felder an den Text angehängt, der durch die oben genannten Regex verarbeitet wird. Der Text hat das Format &quot; 0xTAG:VALUE&quot;, 0xTAG ist der 4-stellige Hexadezimalwert des Tags in Großbuchstaben (z. B. 0x002E).

Sie können beispielsweise die ID im Feld receipted_message_id erfassen. Aktivieren Sie dazu dieses Kontrollkästchen, und dem Status wird folgender Text hinzugefügt:

0x001E:05e3299e-8d37-49d0-97c6-8e4fe60c7739

In diesem Beispiel ist 0x001E das Tag des optionalen Felds und die UUID der Wert des Felds.

Um diesen Wert zu erfassen, können Sie jetzt den folgenden Regex im Feld &quot;Regex zur ID-Extraktion im SR&quot; festlegen:

\b0x001E:([0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]\ 2\})\b

>[!IMPORTANT]
>
>Sie können nur optionale Felder mit 8-Bit-Textwerten (ASCII/UTF-8) erfassen. Insbesondere können Binärfelder mit dem aktuellen Regex-System nicht zuverlässig erfasst werden.

### SR-Kennung oder Fehlercode in einem Textfeld speichern

Wenn diese Option aktiviert ist, wird das Feld Text: während der Verarbeitung des Statustextes des SR beibehalten. Dies ist nützlich, wenn der Provider wichtige Daten wie die ID oder den Status in dieses Feld eingibt. Normalerweise kann dieses Feld sicher verworfen werden, da es Text mit einer Nicht-ASCII-Kodierung enthalten und die Regex-Verarbeitung stören kann.

Durch Aktivierung dieser Option kann es zu einer sehr kleinen Sicherheitslücke kommen, wenn der Regex zur ID-Extraktion im SR-Feld nicht spezifisch genug ist: Der Inhalt des Textfelds kann als ID geparst werden und ein Angreifer kann es verwenden, um gefälschte IDs einzuschleusen, was zu einer teilweisen Dienstverweigerung führen kann.

### Dienst-ID-Tag

Ermöglicht das Hinzufügen eines benutzerdefinierten TLV. Dieses Feld legt das Tag fest, das als Hexadezimalwert im Format **0x1234** übergeben wird.

Der Wert des benutzerdefinierten TLV muss im Versand im Feld &quot;Dienst- oder Programm-ID&quot; in den erweiterten Versandparametern festgelegt werden. Der Wert wird als UTF-8-kodierter Text gesendet.

Diese Einstellung erlaubt nur das Hinzufügen einer TLV-Option pro Nachricht.

>[!NOTE]
>
>Diese Option wird durch die viel leistungsfähigere Einstellung **Optionale SMPP-Parameter (TLV)** in Versandparametern ersetzt. Diese Funktionen schließen sich gegenseitig aus und können nicht gleichzeitig verwendet werden.

### TLS über SMPP aktivieren

Wenn diese Option aktiviert ist, werden alle Verbindungen zum SMSC mit TLS verschlüsselt.

### Zertifikatsprüfung

* **Vollständige Zertifikatüberprüfung**: Prüfen Sie beim Herstellen einer Verbindung das TLS-Zertifikat und den Namen des Remote-Hosts. Dieser Wert bietet das höchste Sicherheitsniveau.
* **Überspringen Sie die Überprüfung des Hostnamens**: Überprüfen Sie das Remote-TLS-Zertifikat, überprüfen Sie jedoch nicht, ob der Name des Remote-Hosts übereinstimmt. Verringert die Sicherheit geringfügig.
* **Überspringen der Zertifikatüberprüfung**: Prüfen Sie das TLS-Zertifikat überhaupt nicht. Die Verbindung ist noch verschlüsselt, aber anfällig für Man-in-the-Middle-Angriffe. Verringert die Sicherheit erheblich.

## Eingehender Traffic {#incoming-traffic}

![](assets/incoming_traffic.png){zoomable="yes"}

### Optionale SMPP-Parameter (TLV) in MO

Campaign ermöglicht den Empfang von drei zusätzlichen Feldern in MO (nms:inSms table): Verknüpfte SMS, Alias und große Konten. Mit dem SMPP-Connector können diese Felder mit Daten aus einem beliebigen optionalen SMPP-Parameter (TLV) in einem beliebigen gemeinsamen Format gefüllt werden.

Sie können für jedes Feld das zugehörige Tag sowie dessen Format festlegen. Bitten Sie den SMPP-Dienstleister, diese Informationen zu erhalten.

* Tag: der Tag-Wert im Dezimalformat (z. B. 12345) oder im Hexadezimalformat mit 0x-Präfix (z. B. 0x12ab). Tags können zwischen 0 und 65535 liegen.
* Format: Format für den Wert. Binärwerte sind alle signierten Big-Endian-Binärwerte. Wählen Sie für Textfelder die vom SMPP-Provider verwendete Kodierung aus.

### Automatische Antwort auf MO          

Mit dieser Funktion können Sie schnell auf MO antworten und Blacklists pro Kurzwahlnummer verarbeiten.

Die Spalten *Schlüsselwort* und *Kurzwahlnummer* definieren Bedingungen für den Trigger der automatischen Antwort: Wenn beide Felder übereinstimmen, wird der MO gesendet und die zusätzliche Aktion ausgelöst. Lassen Sie das Feld leer, um einen Platzhalter anzugeben. Das Schlüsselwort wird mit dem ersten alphanumerischen Wort im MO-Text abgeglichen, wobei Interpunktion und führende Leerzeichen ignoriert werden. Das bedeutet, dass das Feld Schlüsselwort keine Leerzeichen enthalten darf und ein einzelnes Wort sein muss.

Außerdem ist die Einstellung *Suchbegriff* ein Präfix. Wenn Sie z. B. &quot;AD&quot; angeben, wird es &quot;AD&quot;, &quot;ADAPT&quot; und &quot;ADOBE&quot; entsprechen. Wenn Sie mehrere Suchbegriffe mit einem gemeinsamen Präfix haben, achten Sie auf die Reihenfolge, Suchbegriffe werden von oben nach unten verarbeitet.

Die Spalte *Antwort* enthält den Antworttext. In diesem Feld ist keine Personalisierung verfügbar, der Antworttext ist immer derselbe. Wenn Sie dieses Feld leer lassen, wird keine Nachricht als Antwort gesendet, aber die zusätzliche Aktion wird trotzdem ausgelöst.

Die Spalte *Zusätzliche Aktion* enthält eine zusätzliche Aktion, die ausgeführt werden kann, wenn sowohl Keyword als auch Kurzwahlnummer übereinstimmen (eine leere Kurzwahlnummer stimmt mit allen Kurzwahlnummern überein). Derzeit können Sie unter Quarantäne stellen oder aus der Quarantäne entlassen. Wenn Sie eine zusätzliche Aktion angeben, das Antwortfeld jedoch leer lassen, wird die Aktion ausgeführt, aber es wird keine Antwort gesendet. Quarantäne wird nur für die angegebene Kurzwahlnummer oder alle Kurzwahlnummern angewendet, wenn das Feld leer gelassen wird.

Alle Einträge in der Tabelle werden in der angegebenen Reihenfolge verarbeitet, bis eine Regel übereinstimmt. Wenn mehrere Regeln mit einem MO übereinstimmen, wird nur die oberste Regel angewendet.

>[!NOTE]
>
>Die Einstellung **Vollständige Telefonnummer senden** wirkt sich auf das Verhalten des Quarantänemechanismus für automatische Antworten aus: Wenn die vollständige Telefonnummer senden nicht aktiviert ist, wird der unter Quarantäne gestellten Telefonnummer ein Pluszeichen (&quot;+&quot;) vorangestellt, um sie mit dem internationalen Telefonnummernformat kompatibel zu machen.

>[!NOTE]
>
>In einer Mid-Sourcing-Architektur erfordert die Anwendung der automatischen Antwort für den erweiterten SMPP-Connector Schreibzugriff für den Mid-Operator im Ordner des externen Kontos.

>[!IMPORTANT]
>
>Achten Sie bei automatischen Antworten auf Kodierungen auf, insbesondere beim Kopieren und Einfügen. Word-Verarbeitungssoftware neigt dazu, zusätzliche Formatierungen hinzuzufügen, z. B. das Hinzufügen von geschützten Leerzeichen oder das Ändern von Anführungszeichen zu Apostrophen.