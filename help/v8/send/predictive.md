---
title: Prädiktive Benutzerinteraktionsfunktionen
description: Erfahren Sie, wie Sie die prädiktive Sendezeit und Interaktionsbewertung verwenden
feature: Send Time Optimization
role: User
level: Intermediate
source-git-commit: fdaf107fd22f439a728f32ceb8cfc13a8c5bc1ad
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 67%

---

# Sendezeitoptimierung und prädiktive Interaktionsbewertung{#optimize-message-delivery}

Dank KI und maschinellem Lernen können die Sende-Time Optimization und Predictive Engagement Scoring von Adobe Campaign Öffnungsraten, optimale Sendezeiten und wahrscheinliche Abwanderungszahlen basierend auf historischen Interaktionsmetriken analysieren und vorhersagen.

Adobe Campaign bietet zwei neue Modelle für maschinelles Lernen: [Prädiktive Sendezeitoptimierung](#predictive-send) und [Prädiktive Interaktionsbewertung](#predictive-scoring). Bei diesen beiden Modellen handelt es sich um Modelle für maschinelles Lernen, die speziell für die Entwicklung und Bereitstellung besserer Journey für Kunden entwickelt wurden.

>[!CAUTION]
>
>Diese Funktion ist nicht im Produkt vorkonfiguriert. Sie ist nur für Adobe Campaign Managed Cloud Services-Kunden verfügbar, die Adobe Campaign Classic v7 oder Adobe Campaign v8 ausführen.
>
>Die Implementierung erfordert die Einbindung von Adobe Consulting. Weitere Informationen erhalten Sie von Ihrem Kundenbetreuer für Adobe.


## Prädiktive Sendezeitoptimierung{#predictive-send}

Die prädiktive Sendezeitoptimierung sagt für jedes Empfängerprofil voraus, welches die beste Sendezeit für E-Mail-Öffnungen oder Klicks und für Push-Nachrichten-Öffnungen ist. Für jedes Empfängerprofil geben die Bewertungen an, was die beste Sendezeit für jeden Wochentag ist und welcher Wochentag beim Senden die besten Ergebnisse liefert.

Im prädiktiven Sendezeitoptimierungsmodell gibt es zwei Untermodelle:

* Die prädiktive Sendezeit für Öffnungen ist die beste Zeit, zu der eine Kommunikation an den Kunden gesendet werden muss, um Öffnungen zu maximieren.

* Die prädiktive Sendezeit für Klicks ist die beste Zeit, zu der eine Kommunikation an den Kunden gesendet werden muss, um Klicks zu maximieren.


**Modelleingabe**: Versandlogs, Trackinglogs und Profilattribute (Nicht-PII)

**Modellausgabe**: Optimale Sendezeit für eine Nachricht (für Öffnungen und Klicks)

Ausgabedetails:

* Berechnen Sie die beste Tageszeit für den Versand einer E-Mail an den sieben Wochentagen in Intervallen von einer Stunde (z. B.: 9:00 Uhr, 10:00 Uhr, 11:00 Uhr).
* Das Modell zeigt den besten Tag der Woche und die beste Stunde an diesem Tag an.
* Jede optimale Zeit wird zweimal berechnet: einmal zur Maximierung der Öffnungsrate und einmal zur Maximierung der Klickrate.
* Es werden 16 Felder angegeben (14 für die Wochentage und 2 für die ganze Woche):
   * beste Zeit, um eine E-Mail zu senden, um Klicks für Montag zu optimieren – Werte zwischen 0 und 23
   * beste Zeit, um eine E-Mail zu senden, um Öffnungen für Montag zu optimieren – Werte zwischen 0 und 23
   * ...
   * beste Zeit, um eine E-Mail zu senden, um Klicks für Sonntag zu optimieren – Werte zwischen 0 und 23
   * beste Zeit, um eine E-Mail zu senden, um Öffnungen für Sonntag zu optimieren – Werte zwischen 0 und 23
   * ...
   * bester Tag, um eine E-Mail zu senden, um die Öffnungen für die ganze Woche zu optimieren – Montag bis Sonntag
   * beste Zeit, um eine E-Mail zu senden, um Öffnungen für die ganze Woche zu optimieren – Werte zwischen 0 und 23


Die prädiktive Sendezeitoptimierung wird auf Profilebene gespeichert:

![](assets/sto-schema.png)


>[!NOTE]
>
>Das Modell benötigt mindestens einen Monat an Daten, um signifikante Ergebnisse zu erzielen. Diese Prognosefunktionen gelten nur für E-Mail- und Push-Kanäle.


## Prädiktive Interaktionsbewertung {#predictive-scoring}

Die prädiktive Interaktionsbewertung sagt die Wahrscheinlichkeit voraus, mit der ein Empfänger mit einer Nachricht interagiert, sowie die Wahrscheinlichkeit, dass er sich innerhalb der nächsten sieben Tage nach dem nächsten E-Mail-Versand abmeldet. Die Wahrscheinlichkeiten werden je nach vorhergesagter Interaktion mit Ihrem Inhalt weiter in Behälter unterteilt: hoch, mittel oder niedrig. Diese Modelle bieten außerdem den Perzentil-Rang des Abmelderisikos, damit die Kunden erkennen können, wo der Rang eines bestimmten Kunden im Vergleich zu anderen liegt.

Mit der prädiktiven Interaktionsbewertung können Sie Folgendes:

* **Eine Audience auswählen**: Mithilfe der Abfrageaktivität können Sie die Audience auswählen, an die eine bestimmte Nachricht gesendet werden soll.
* **Eine Audience ausschließen**: Mithilfe der Abfrageaktivität können Sie die Audience entfernen, die sich abmelden möchte.
* **Personalisieren**: Personalisieren Sie die Nachricht basierend auf dem Grad der Interaktion (stark interaktive Benutzer erhalten eine andere Nachricht als nicht interaktive).

Dieses Modell verwendet mehrere Bewertungen, um Folgendes anzugeben:

* **Interaktionsbewertung für Öffnungen/Interaktionsbewertung für Klicks**: Dieser Wert entspricht der Wahrscheinlichkeit, mit der sich ein Abonnent mit einer bestimmte Nachricht beschäftigt (Öffnung oder Klick). Die Werte liegen zwischen 0,0 und 1,0.
* **Abmeldewahrscheinlichkeit**: Dieser Wert entspricht der Wahrscheinlichkeit, dass der Empfänger sich von einem E-Mail-Kanal abmeldet, nachdem er eine E-Mail geöffnet hat. Die Werte liegen zwischen 0,0 und 1,0.
* **Bindungsgrad**: Dieser Wert unterteilt Benutzer in drei Stufen: niedrig, mittel und hoch. Dabei bedeutet &quot;hoch&quot;, dass sie höchstwahrscheinlich bei der Marke bleiben, und &quot;niedrig&quot;, dass sie sich wahrscheinlich abmelden.
* **Perzentilrang der Bindung**: Rang des Profils in Bezug auf die Abmeldewahrscheinlichkeit. Die Werte liegen zwischen 0,0 und 1,0. Wenn der Perzentilrang der Bindung beispielsweise 0,953 beträgt, bleibt dieser Empfänger mit größerer Wahrscheinlichkeit bei der Marke und hat eine geringere Wahrscheinlichkeit, sich abzumelden, als 95,3 % aller Empfänger.

>[!NOTE]
>
>Diese prädiktiven Funktionen gelten nur für den E-Mail-Versand.
>
>Das Modell benötigt mindestens einen Monat an Daten, um signifikante Ergebnisse zu erzielen.

**Modelleingabe**: Versandlogs, Trackinglogs und spezifische Profilattribute

**Modellausgabe**: Ein Profilattribut, das die Bewertung und Kategorie des Profils beschreibt.
