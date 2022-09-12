---
title: Arbeiten mit Zielgruppen-Mappings
description: Erfahren Sie, wie Sie Zielgruppen-Mappings verwenden und erstellen
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
source-git-commit: a41bebfeb352b2f81f81b46c39b5f9b64431455b
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 41%

---

# Arbeiten mit Zielgruppen-Mappings{#gs-target-mappings}

Standardmäßig werden die Versandvorlagen als Zielgruppe ausgewählt **[!UICONTROL Empfänger]**. Ihr Zielgruppen-Mapping verwendet daher die Felder der **nms:recipient** Tabelle.

Sie können für Ihre Sendungen andere Zielgruppen-Mappings verwenden oder ein neues Zielgruppen-Mapping erstellen.

## Integrierte Zielgruppen-Mappings {#ootb-mappings}

Adobe Campaign enthält die folgenden integrierten Zielgruppen-Mappings:

| Name | Verwendung bis | Schema |
|---|---|---|
| Bereich Empfänger | Versand an Empfänger (integrierte Empfängertabelle) | nms:recipient |
| Besucher | Versand an Besucher, deren Profile z. B. über Verweise (Viral Marketing) erfasst wurden. | mns:visitor |
| Abonnements  | Versand richtet sich an Abonnenten eines Informationsdienstes wie z. B. einen Newsletter | nms:subscription |
| Besucher-Abonnements | Versand richtet sich an Besucher, die einen Informationsdienst beziehen | nms:visitorSub |
| Benutzer | Versand richtet sich an Adobe-Campaign-Benutzer | nms:operator |
| Externe Datei | Versand basiert auf einer Datei, die alle notwendigen Informationen enthält | Ohne Schema oder Zielgruppe |

## Zielgruppen-Mapping erstellen {#new-mapping}

Sie können auch ein Zielgruppen-Mapping erstellen. Möglicherweise müssen Sie ein benutzerdefiniertes Zielgruppen-Mapping hinzufügen, z. B. wenn:

* Sie verwenden eine benutzerdefinierte Empfängertabelle,
* Sie können eine Filterdimension konfigurieren, die sich von der integrierten Zielgruppendimension auf dem Zielgruppen-Mapping-Bildschirm unterscheidet.

Weitere Informationen zu benutzerdefinierten Empfängertabellen finden Sie unter [diese Seite](../dev/custom-recipient.md).

Der Assistent zur Erstellung von Zielgruppen-Mappings von Adobe Campaign unterstützt Sie beim Erstellen aller Schemas, die zur Verwendung Ihres benutzerdefinierten Zielgruppen-Mappings erforderlich sind.

1. Navigieren Sie im Adobe Campaign-Explorer zu **[!UICONTROL Administration]** `>` **[!UICONTROL Kampagnenverwaltung]** `>` **[!UICONTROL Zielgruppen-Mappings]** .

1. Erstellen Sie ein neues Zielgruppen-Mapping und wählen Sie Ihr benutzerdefiniertes Schema als Zielgruppendimension aus.

   ![](assets/new-target-mapping.png)


1. Geben Sie die Felder an, in denen die Profilinformationen gespeichert werden: Nachname, Vorname, E-Mail, Adresse usw.

   ![](assets/wf_new_mapping_define_join.png)

1. Geben Sie die Parameter für die Speicherung der Informationen an, einschließlich des Suffix der Erweiterungsschemata, damit diese leicht identifiziert werden können.

   ![](assets/wf_new_mapping_define_names.png)

   Wählen Sie aus, ob Ausschlüsse (**excludelog**) mit Nachrichten (**broadlog**) oder in einer separaten Tabelle gespeichert werden sollen.

   Sie können für dieses Versand-Mapping (**trackinglog**) auch auswählen, ob Tracking verwaltet werden soll.

1. Wählen Sie dann die zu berücksichtigenden Erweiterungen aus. Der Erweiterungstyp hängt von Ihren Campaign-Einstellungen und Add-ons ab.

   ![](assets/wf_new_mapping_define_extensions.png)

   Klicken Sie auf die Schaltfläche **[!UICONTROL Speichern]**, um die Erstellung des Versand-Mappings zu beginnen: Alle verknüpften Tabellen werden automatisch auf der Basis der ausgewählten Parameter erstellt.

