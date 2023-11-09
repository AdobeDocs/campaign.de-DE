---
product: campaign
title: Künftige Änderungen am Push-Benachrichtigungskanal
description: Künftige Änderungen am Push-Benachrichtigungskanal
hide: true
hidefromtoc: true
source-git-commit: 70d1e7336cce7660890b13def5efcb614c0dc12e
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 5%

---

# Künftige Änderungen am Push-Benachrichtigungskanal {#push-upgrade}

Es gibt wichtige Änderungen am Firebase Cloud Messaging (FCM)-Dienst, die sich auf Ihre Adobe Campaign Classic-Implementierung auswirken können.

Im Rahmen der kontinuierlichen Bemühungen von Google, seine Dienste zu verbessern, werden die veralteten FCM-APIs im Juni 2024 eingestellt ([Firebase Cloud Messaging - HTTP-Protokoll](https://firebase.google.com/docs/cloud-messaging/http-server-ref))

Diese APIs sind derzeit in Adobe Campaign Classic integriert, um Push-Benachrichtigungen zu senden. Wir wissen, dass viele unserer Kunden, wie Sie, für Ihre Marketing-Kampagnen und Kommunikationsanforderungen und insbesondere für Android-Geräte auf diese Dienste angewiesen sind.

## Sind Sie betroffen?

* **HTTP-API-Benutzer (veraltet)**: Wenn eine Ihrer aktiven Push-Benachrichtigungs-Kampagnen die HTTP-API (frühere Version) verwendet, wirkt sich diese Änderung direkt auf Ihr Setup aus. Wir empfehlen Ihnen dringend, Ihre aktuellen Konfigurationen zu überprüfen und sich auf die Migration zu den neueren APIs vorzubereiten.

* **Gute Nachrichten für HTTP v1-API-Benutzer**: Wenn Ihr Setup ausschließlich die HTTP v1-API für Android-Push-Benachrichtigungen verwendet, sind Sie bereits konform und es sind keine weiteren Maßnahmen Ihrerseits erforderlich.

## Was machen wir?

* **Übergangsplan**: Unser Team arbeitet aktiv an der Entwicklung eines umfassenden Übergangsplans. Dadurch wird sichergestellt, dass Sie Ihre Implementierung bei Bedarf auf die neueren FCM-APIs aktualisieren können, die bereits in den letzten Versionen von Adobe Campaign verfügbar sind, und dass Ihre Kampagnen nur geringfügig beeinträchtigt werden.

* **Detaillierte Anweisungen**: Wir stellen eine schrittweise Anleitung und weitere Ressourcen bereit, um einen reibungslosen Übergangsprozess zu erleichtern.

* **Support**: Unser Support-Team steht Ihnen während des gesamten Übergangszeitraums zur Verfügung. Wir können auch Webinare und Aktivierungssitzungen veranstalten, um die technischen Aspekte und Best Practices für die Umstellung abzudecken.

## Was erwarten wir von Ihnen?

* **Bleiben Sie informiert**: Behalten Sie Ihren Posteingang im Auge, um weitere Informationen von uns zu erhalten, einschließlich des detaillierten Übergangsplans.

* **Aktuelle Einrichtung überprüfen**: Nehmen Sie diese Zeit, um Ihre aktuelle Konfiguration und Anpassung in Adobe Campaign Classic zu überprüfen und Sie auf die Vorbereitung zu warten, um bei Bedarf die erforderlichen Änderungen vorzunehmen.

* **Kontakt**: Wenn Sie Fragen oder Anliegen haben, wenden Sie sich bitte an unser Support-Team.

## Implementierungsschritte

In den kommenden Wochen werden wir weitere Details zum Übergangsplan für veraltete FCM-APIs teilen, einschließlich Zeitplänen und Aktionselementen. Seien Sie sicher, unser Hauptziel ist es, diesen Übergang für Sie und Ihr Team so nahtlos wie möglich zu gestalten.

Wir freuen uns über Ihr Geschäft und danken Ihnen für Ihr Verständnis, wenn wir uns an diese Veränderungen anpassen. Ihr Erfolg ist unsere oberste Priorität, und wir sind entschlossen, Sie bei jedem Schritt zu unterstützen.

Sie können die Änderung also vorhersehen. Hier sind die allgemeinen Schritte, die erforderlich sind, um Ihre Push-Konfiguration von der HTTP (Legacy)- zur FCM HTTPv1-API zu migrieren.

### Build-Upgrade

* Campaign Classic: Die Unterstützung von HTTPv1 wurde in Version 20.3.1 hinzugefügt. Wenn Sie eine frühere Version verwenden, müssen Sie zunächst auf den neuesten Campaign Classic-Build aktualisieren.

* Campaign v8: HTTPv1 wird von allen Campaign v8-Versionen unterstützt. Keine Aktualisierung erforderlich.

### Marketing-Server

Konfigurationsänderungen können vom Kunden/Partner vorgenommen werden.

1. Zunächst müssen Sie Ihre JSON-Datei extrahieren. Die JSON-Datei des Kontos des Firebase Admin SDK-Dienstes ist erforderlich, damit die Mobile App auf HTTPv1 verschoben wird. Mehr dazu erfahren Sie auf [dieser Seite](https://firebase.google.com/docs/admin/setup#initialize-sdk).

1. Navigieren Sie zu Ihrer Liste von **Dienste und Abonnements**.

1. Suchen Sie alle Mobile Apps mithilfe der HTTP-API-Version (frühere Version).

1. Legen Sie für jede dieser Mobile Apps die Variable **API-Version** auf HTTPv1 klicken und die Konfigurationsanweisungen befolgen, die im Abschnitt [Dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=de).

>[!NOTE]
>
>Bei neuen Sendungen wird der Wechsel zur HTTPv1-API berücksichtigt. Für Sendungen, die wiederholt ausgeführt und verwendet werden, wird weiterhin die HTTP-API (frühere Version) verwendet.

### Mid Sourcing-Server

Es sind keine Änderungen erforderlich.

### Echtzeit-Ausführungsserver

Wenden Sie sich diesbezüglich an den Adobe Campaign-Support. Das Migrationsverfahren entspricht dem für den Marketing-Server.

### Android OS und Android Mobile App

Es sind keine spezifischen Änderungen am Code der Android Mobile Apps erforderlich und das Benachrichtigungsverhalten sollte sich nicht ändern.

Dennoch führt HTTPv1 drei neue Payload-Elemente ein:

| Name | Standardwert |
|---|---|
| Sticky | False |
| priority | Standard |
| visibility | False |
| Sticky | Privat |
