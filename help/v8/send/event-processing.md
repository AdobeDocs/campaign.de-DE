---
title: Erfassen und Verarbeiten von Ereignissen
description: Erfahren Sie, wie Transaktionsnachrichten in Campaign Ereignisse sammeln und verarbeiten.
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 44%

---


# Ereignisverarbeitung {#event-processing}

Im Zusammenhang mit Transaktionsnachrichten wird ein Ereignis von einem externen Informationssystem generiert und über die **[!UICONTROL PushEvent]** und **[!UICONTROL PushEvents]** -Methoden. Diese Methoden werden unter [diesem Abschnitt](event-description.md).

Dieses Ereignis enthält Daten, die mit dem Ereignis verknüpft sind, z. B.:

* its [type](transactional.md#create-event-types): Bestellbestätigung, Kontoerstellung auf einer Website usw.,
* E-Mail-Adresse oder Telefonnummer,
* sonstige Informationen zur Anreicherung und Personalisierung der Transaktionsnachricht vor dem Versand: Kundenkontaktdaten, Sprache der Nachricht, E-Mail-Format usw.

Beispiel für Ereignisdaten:

![](assets/mc-event-request.png)

Um Transaktionsnachrichten-Ereignisse zu verarbeiten, werden die folgenden Schritte auf der/den Ausführungsinstanz(en) ausgeführt:

1. [Ereignisabruf](#event-collection)
1. [Weiterleitung des Ereignisses zu einer Nachrichtenvorlage](#routing-towards-a-template)
1. Anreicherung des Ereignisses mit Personalisierungsdaten
1. [Versandausführung](delivery-execution.md)
1. [Recycling von Ereignissen](#event-recycling), bei denen der mit ihnen verknüpfte Versand fehlgeschlagen ist (über einen Adobe Campaign-Workflow)

Sobald alle Schritte ausgeführt wurden, erhält jeder Zielgruppenempfänger eine personalisierte Nachricht.

## Ereignisse sammeln {#event-collection}

Die vom Informationssystem erzeugten Ereignisse können auf zwei Weisen abgerufen werden:

* Nutzung von SOAP-Methoden, die die Ereignisse Adobe Campaign zuführen: Die PushEvent-Methode ermöglicht den Versand eines Ereignisses, die PushEvents-Methode den Versand mehrerer Ereignisse auf einmal. [Weitere Informationen](event-description.md).

* Die Erstellung eines Workflows ermöglicht den Abruf von Ereignissen durch den Dateiimport oder über ein SQL-Gateway mit dem [Federated Data Access](../connect/fda.md) -Modul.

Nach der Erfassung werden die Ereignisse durch technische Workflows zwischen Echtzeit- und Batch-Warteschlangen der Ausführungsinstanzen aufgeschlüsselt, wobei darauf gewartet wird, mit einer [Nachrichtenvorlage](transactional-template.md).

![](assets/mc-event-queues.png)

>[!NOTE]
>
>Auf den Ausführungsinstanzen dürfen die Ordner **[!UICONTROL Echtzeit-Ereignisse]** oder **[!UICONTROL Batch-Ereignisse]** nicht als Ansichten festgelegt werden, da dies zu Problemen mit Zugriffsrechten führen könnte. Weitere Informationen zum Festlegen eines Ordners als Ansicht finden Sie in [diesem Abschnitt](../audiences/folders-and-views.md#turn-a-folder-to-a-view).

## Ereignis an eine Vorlage übertragen {#event-to-template}

Nach der Publikation der Nachrichtenvorlage in der/den Ausführungsinstanz(en) werden zwei Vorlagen automatisch erzeugt: eines Ereignisses, das mit einem Echtzeit-Ereignis verknüpft werden soll, und eines, das mit einem Batch-Ereignis verknüpft werden soll.

Beim Routing-Schritt wird ein Ereignis mit der entsprechenden Nachrichtenvorlage verknüpft. Dies erfolgt basierend auf:

* dem in den Eigenschaften des Ereignisses angegebenen Ereignistyp:

   ![](assets/event-type-sample.png)

* dem in den Eigenschaften der Nachrichtenvorlage angegebenen Ereignistyp:

   ![](assets/event-type-select.png)

Standardmäßig erfolgt das Routing auf Basis folgender Informationen:

* dem Ereignistyp
* dem verwendeten Kanal (standardmäßig: E-Mail)
* der auf dem Veröffentlichungsdatum basierenden letzten Versandvorlage

## Ereignisstatus überprüfen {#event-statuses}

Alle verarbeiteten Ereignisse werden in einer einzigen Ansicht in der **Ereignisverlauf** oder dem Explorer. Sie können nach Ereignistyp oder nach **status**.

Mögliche Status sind:

* **Ausstehend**

   * Ein ausstehendes Ereignis kann ein Ereignis sein, das gerade erfasst wurde und noch nicht verarbeitet wurde. Die **[!UICONTROL Fehleranzahl]** gibt den Wert 0 an. Die E-Mail-Vorlage wurde noch nicht verknüpft.
   * Ein ausstehendes Ereignis kann auch ein verarbeitetes Ereignis sein, dessen Bestätigung jedoch fehlerhaft ist. Die **[!UICONTROL Fehleranzahl]** zeigt einen Wert an, der nicht 0 ist. Um zu erfahren, wann dieses Ereignis erneut verarbeitet wird, konsultieren Sie die **[!UICONTROL Prozess angefordert am]** Spalte.

* **Versand ausstehend**
Das Ereignis wurde verarbeitet und die Versandvorlage wurde verknüpft. Die E-Mail steht vor dem Versand und der klassische Versandprozess wird angewendet. Weitere Informationen erhalten Sie, wenn Sie den Versand öffnen möchten.
* **Gesendet**, **Ignoriert** und **Versandfehler**
Diese Versandstatus werden über die 
**updateEventsStatus** Arbeitsablauf. Für weitere Informationen können Sie den entsprechenden Versand öffnen.
* **Ereignis nicht erfasst**
Die Routing-Phase der Transaktionsnachrichten schlug fehl. Ein Beispiel hierfür wäre, dass Adobe Campaign die E-Mail, die als Vorlage für das Ereignis dient, nicht finden konnte.
* **Ereignis abgelaufen**
Die maximale Anzahl von Versandversuchen wurde erreicht. Das Ereignis wird als null betrachtet.

## Ereignisse wiederverwenden {#event-recycling}

Wenn der Versand einer Nachricht über einen bestimmten Kanal fehlschlägt, kann Adobe Campaign über einen anderen Kanal einen erneuten Versandversuch starten. Wenn beispielsweise der Versand einer Nachricht über den SMS-Kanal fehlschlägt, wird die Nachricht über den E-Mail-Kanal erneut versandt.

Konfigurieren Sie hierzu einen Workflow, der alle Ereignisse mit **Versandfehler** neu erstellt und ihnen einen sich vom ersten Kanal unterscheidenden Kanal zuordnet.

>[!CAUTION]
>
>Dieser Schritt kann nur mithilfe eines Workflows durchgeführt werden und sollte daher erfahrenen Benutzern vorbehalten bleiben. Wenden Sie sich für weitere Informationen hierzu an Ihren Adobe-Kundenbetreuer.



