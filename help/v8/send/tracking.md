---
title: Erste Schritte zum Tracking von Nachrichten
description: Weitere Informationen zu Tracking-Funktionen in Adobe Campaign
feature: Monitoring, Email
role: User
level: Beginner
exl-id: f3de901f-519f-42ae-846c-f20c7cb560df
source-git-commit: 90ed82673b893b62a185227dd8cdfe80cc8f1455
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 72%

---

# Erste Schritte zum Tracking von Nachrichten {#get-started-tracking}

Dank der Tracking-Funktionen können Sie mit Adobe Campaign die gesendeten Nachrichten verfolgen und das Empfängerverhalten überprüfen: Öffnungen, Klicks auf Links, Abmeldungen und mehr.

Diese Informationen werden auf der Registerkarte **[!UICONTROL Tracking]** des Profils jedes Versandempfängers abgerufen. Auf dieser Registerkarte werden alle verfolgten URL-Links angezeigt, auf die der in der Liste ausgewählte Empfänger geklickt hat. Dies ist die Akkumulation aller URLs, die in den Sendungen verfolgt werden, die noch im Versandbildschirm vorhanden sind. Die Liste kann konfiguriert werden und enthält normalerweise die angeklickte URL, das Datum und die Uhrzeit des Klicks sowie das Dokument, in dem die URL gefunden wurde.

Das **Versand-Dashboard** ist auch ein wichtiges Tool, mit dem Sie Sendungen überwachen und mögliche Probleme beim Nachrichtenversand erkennen können.

Das folgende Diagramm zeigt die Phasen des Dialogs zwischen Benutzenden und den verschiedenen Servern.

<img src="assets/tracking-diagram.png" width="70%">

>[!NOTE]
>
>Die Tracking-Konfiguration wird von Adobe für Managed Cloud Services-Bereitstellungen ausgeführt.

## Nachrichten-Tracking {#message-tracking}

**Getrackte Links**

Sie können den Empfang von Nachrichten und die Aktivierung der im Nachrichteninhalt eingefügten Links verfolgen, um das Verhalten der Empfänger besser zu verstehen.

[Weitere Informationen zu getrackten Links](tracked-links.md)

**URL-Tracking**

Tracking-Optionen können durch Aktivieren oder Deaktivieren von Tracking-URLs konfiguriert werden.

[Weitere Informationen zu URL-Tracking-Optionen](url-tracking.md)

**Personalisierung getrackter Links**

Mit den Tracking-Funktionen von Campaign können Sie Links in E-Mails einfügen, die personalisiert werden können und das Tracking unterstützen.

[Weitere Informationen zum Tracking personalisierter Links](personalized-links.md)

**Trackinglogs**

Der technische **Tracking**-Workflow ruft die Tracking-Daten ab, sobald der Versand ausgeführt und das Tracking aktiviert wurde. Diese Daten finden Sie auf der Registerkarte &quot;Tracking&quot; Ihres Versands.

[Weitere Informationen zu Trackinglogs](tracking-logs.md)

**Tracking testen**

Bevor Sie Ihre Nachrichten mit Ihrem Tracking senden, können Sie das Tracking auf Ihrer Mirrorseite, in Ihren E-Mail-Protokollen und Links testen.

[Weitere Informationen zum Testen von Tracking](testing-tracking.md)

## Tracking-Berichte {#tracking-reports}

**Tracking-Statistiken**

Dieser Bericht enthält Statistiken zu Öffnungen, Klicks und Transaktionen und ermöglicht es Ihnen, die Marketing-Wirkung des Versands zu verfolgen.

[Weitere Informationen zu Tracking-Berichten](../reporting/delivery-reports.md#tracking-indicators)

**URLs und Clickstreams**

Dieser Bericht zeigt die Rangfolge der infolge eines Versands besuchten Web-Seiten.

[Weitere Informationen zu URLs und Clickstreams](../reporting/delivery-reports.md#urls-and-click-streams)

**Personen und Empfänger**

Anhand dieses Beispiels können Sie den Unterschied beim Tracking zwischen einer Person/Personen und einem Empfänger in Adobe Campaign besser verstehen.

Weitere Informationen zu Personen und Empfängern finden Sie in der Dokumentation zu [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/person-people-recipients.html?lang=de#reporting){target="_blank"}

**Tracking-Indikatoren**

In diesem Bericht werden die Schlüsselindikatoren zum Tracking des Verhaltens der Empfänger beim Empfang der Sendung zusammengefasst, z. B. Öffnungsraten, Clickthrough-Raten und Clickstreams.

[Weitere Informationen zu Tracking-Indikatoren](../reporting/delivery-reports.md#tracking-indicators)

**Indikatorberechnung**

In den verschiedenen Tabellen finden Sie nach Versandtyp geordnet die Liste der Indikatoren, die in Berichten verwendet werden, sowie ihre Berechnungsformeln.

[Weitere Informationen zur Indikatorberechnung](../reporting/metrics-calculation.md)


