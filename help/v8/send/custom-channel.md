---
title: Erste Schritte mit benutzerdefinierten externen Kanälen
description: Erfahren Sie, wie Sie mit Adobe Campaign Web benutzerdefinierte Sendungen für externe Kanäle erstellen und senden
role: User
level: Beginner, Intermediate
source-git-commit: 4ba419c52d6804e4f25f88990c226081ef0a06e6
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 4%

---


# Erste Schritte mit benutzerdefinierten externen Kanälen {#gs-custom-channel}

Mit Adobe Campaign können Sie benutzerdefinierte externe Kanäle erstellen, die mit Drittanbietern integriert sind. Sie können dann Sendungen basierend auf diesen Kanälen orchestrieren und ausführen.

Die Versanderstellung und der Versand können sowohl in der Client-Konsole als auch in der Web-Benutzeroberfläche durchgeführt werden. Der benutzerdefinierte externe Kanal wird jedoch nur in der Client-Konsole ausgeführt.

Informationen zum Erstellen und Senden eines Versands auf der Grundlage eines benutzerdefinierten externen Kanals finden Sie auf dieser [Seite](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/gs-custom-channel.html).

Im Folgenden finden Sie die Schritte zum Erstellen eines neuen externen benutzerdefinierten Kanals in der Client-Konsole:

1. Konfigurieren des Schemas, [weitere Informationen](#configure-schema)
1. Erstellen eines neuen externen Kontos, [mehr dazu](#create-ext-account)
1. Erstellen einer neuen Versandvorlage, [weitere Informationen](#create-template)

## Konfigurieren des Schemas{#configure-schema}

Zunächst müssen Sie das Schema konfigurieren, um den neuen Kanal zur Liste der verfügbaren Kanäle hinzuzufügen.

1. Wählen Sie im Campaign-Explorer **Administration** > **Konfiguration** > **Datenschemata**.

1. Erstellen Sie eine Schemaerweiterung, um die MessageType-Auflistung um den neuen Kanal zu erweitern.

   Beispiel:

   ```
   <enumeration basetype="byte" default="mail" label="Channel" name="messageType">
   <value desc="My Webpush" img="ncm:channels.png" label="My Webpush" name="webpush"
          value="122"/>
   </enumeration>
   ```

   ![](assets/cus-schema.png){zoomable="yes"}

## Neues externes Konto erstellen{#create-ext-account}

Anschließend müssen Sie ein neues externes Routing-Konto erstellen.

1. Wählen Sie im Campaign-Explorer **Administration** > **Plattform** > **Externe Konten**.

1. Erstellen Sie ein neues externes Konto.

1. Wählen Sie den Kanal aus und ändern Sie den Versandmodus in **Extern**.

   ![](assets/cus-ext-account.png){zoomable="yes"}

## Erstellen einer neuen Versandvorlage{#create-template}

Erstellen wir nun die neue Vorlage, die mit dem neuen Kanal verknüpft ist.

1. Wählen Sie im Campaign-Explorer **Ressourcen** > **Vorlagen** > **Versandvorlagen**.

1. Erstellen Sie eine neue Vorlage.

1. Klicken Sie auf **Eigenschaften** und wählen Sie den richtigen Ordner und das richtige Routing aus.

   ![](assets/cus-template.png){zoomable="yes"}

Der neue Kanal ist jetzt verfügbar. Sie können Sendungen auf Grundlage dieses Kanals erstellen und ausführen.


