---
title: Erste Schritte mit benutzerdefinierten externen Kanälen
description: Erfahren Sie, wie Sie mit Adobe Campaign Web Sendungen über benutzerdefinierte externe Kanäle erstellen und durchführen.
role: User
level: Beginner, Intermediate
exl-id: d2d92de6-3974-41c5-a0fd-09bbf6cf0020
source-git-commit: f94074d954137c4db39b2ef9f85141b79fe3356b
workflow-type: ht
source-wordcount: '268'
ht-degree: 100%

---

# Erste Schritte mit benutzerdefinierten externen Kanälen {#gs-custom-channel}

Mit Adobe Campaign können Sie benutzerdefinierte externe Kanäle erstellen, die mit Drittanbietern integriert sind. Anschließend können Sie Sendungen basierend auf diesen Kanälen orchestrieren und ausführen.

Die Versanderstellung und das Versenden können sowohl in der Client-Konsole als auch in der Web-Benutzeroberfläche durchgeführt werden. Der benutzerdefinierte externe Kanal wird jedoch nur in der Client-Konsole ausgeführt.

Informationen zum Erstellen und Senden eines Versands auf der Grundlage eines benutzerdefinierten externen Kanals finden Sie auf [dieser Seite](https://experienceleague.adobe.com/de/docs/campaign-web/v8/msg/gs-custom-channel).

Im Folgenden finden Sie die Schritte zum Erstellen eines neuen externen benutzerdefinierten Kanals in der Client-Konsole:

1. Konfigurieren des Schemas, [weitere Informationen](#configure-schema)
1. Erstellen eines neuen externen Kontos, [weitere Informationen](#create-ext-account)
1. Erstellen einer neuen Versandvorlage, [weitere Informationen](#create-template)

## Konfigurieren des Schemas{#configure-schema}

Zunächst müssen Sie das Schema konfigurieren, um den neuen Kanal zur Liste der verfügbaren Kanäle hinzuzufügen.

1. Wählen Sie im Explorer von Campaign **Administration** > **Konfiguration** > **Datenschemata** aus.

1. Erstellen Sie eine Schemaerweiterung, um die messageType-Auflistung um den neuen Kanal zu erweitern.

   Beispiel:

   ```
   <enumeration basetype="byte" default="mail" label="Channel" name="messageType">
   <value desc="My Webpush" img="ncm:channels.png" label="My Webpush" name="webpush"
          value="122"/>
   </enumeration>
   ```

   ![](assets/cus-schema.png){zoomable="yes"}

## Erstellen eines neuen externen Kontos{#create-ext-account}

Anschließend müssen Sie ein neues externes Routing-Konto erstellen.

1. Wählen Sie im Explorer von Campaign **Administration** > **Plattform** > **Externe Konten** aus.

1. Erstellen Sie ein neues externes Konto.

1. Wählen Sie den Kanal aus und ändern Sie den Versandmodus in **Extern**.

   ![](assets/cus-ext-account.png){zoomable="yes"}

## Erstellen einer neuen Versandvorlage{#create-template}

Erstellen wir nun die neue Vorlage, die mit dem neuen Kanal verknüpft ist.

1. Wählen Sie über den Explorer von Campaign **Ressourcen** > **Vorlagen** > **Versandvorlagen** aus.

1. Erstellen Sie eine neue Vorlage.

1. Klicken Sie auf **Eigenschaften** und wählen Sie den richtigen Ordner sowie das richtige Routing aus.

   ![](assets/cus-template.png){zoomable="yes"}

Der neue Kanal ist jetzt verfügbar. Sie können Sendungen auf Grundlage dieses Kanals erstellen und ausführen.
