---
title: Arbeiten mit Zielgruppen-Mappings
description: Erfahren Sie, wie Sie Zielgruppen-Mappings erstellen und verwenden.
feature: Audiences, Profiles
role: User, Developer
level: Beginner, Intermediate
exl-id: 5256fc15-1878-4064-9c75-7876a3826b83
TQID: https://experienceleague.adobe.com/ArJJi775HkzlpPOu-SoKg8UTcYTperTC1ySmXrHHpJg
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
subfeature_v2: id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 383
ht-degree: 100%

---

# Arbeiten mit Zielgruppen-Mappings{#gs-target-mappings}

Standardmäßig haben die E-Mail- und SMS-Versandvorlagen **[!UICONTROL Empfänger]** als Zielgruppe. Das Zielgruppen-Mapping verwendet also die Felder der Tabelle **nms:recipient**.

Für Push-Benachrichtigungen ist das standardmäßige Zielgruppen-Mapping **Abonnierte Anwendungen (nms:appSubscriptionRcp)**, das mit der Empfängertabelle verknüpft ist.

Sie können für Ihre Sendungen aber auch andere Zielgruppen-Mappings verwenden oder ein neues Zielgruppen-Mapping erstellen.

## Integrierte Zielgruppen-Mappings {#ootb-mappings}

Adobe Campaign verfügt über die folgenden integrierten Zielgruppen-Mappings:

| Name | Verwendungszweck | Schema |
|---|---|---|
| Bereich Empfänger | Versand an Empfänger (integrierte Empfängertabelle) | nms:recipient |
| Besuchende | Versand an Besucher, deren Profile beispielsweise über Empfehlungen (Viral Marketing) erfasst wurden. | mns:visitor |
| Abonnements | Versand richtet sich an Abonnenten eines Informationsdienstes wie z. B. einen Newsletter | nms:subscription |
| Besucher-Abonnements | Versand richtet sich an Besucher, die einen Informationsdienst beziehen | nms:visitorSub |
| Benutzer | Versand richtet sich an Adobe Campaign-Benutzer | nms:operator |
| Externe Datei | Versand basiert auf einer Datei, die alle notwendigen Informationen enthält | Ohne Schema oder Zielgruppe |
| Abonnierte Anwendungen | Versand an Empfängerinnen und Empfänger, die eine Anwendung abonniert haben | nms:appSubscriptionRcp |


## Erstellen eines Zielgruppen-Mappings {#new-mapping}

Sie können auch selbst ein Zielgruppen-Mapping erstellen. Sie benötigen beispielsweise ein benutzerdefiniertes Zielgruppen-Mapping, wenn:

* eine benutzerdefinierte Empfängertabelle verwendet wird,
* eine Filterdimension konfiguriert wird, die sich von der integrierten Zielgruppendimension auf dem Zielgruppen-Mapping-Bildschirm unterscheidet.

Weitere Informationen über benutzerdefinierte Empfängertabellen finden sich auf [dieser Seite](../dev/custom-recipient.md).

Der Adobe Campaign-Assistent zur Erstellung von Zielgruppen-Mappings hilft Ihnen bei der Erstellung aller Schemata, die zur Verwendung Ihres benutzerdefinierten Zielgruppen-Mappings erforderlich sind.

1. Navigieren Sie im Adobe Campaign-Explorer zu **[!UICONTROL Administration]** `>` **[!UICONTROL Kampagnenverwaltung]** `>` **[!UICONTROL Zielgruppen-Mappings]**.

1. Erstellen Sie ein neues Zielgruppen-Mapping und wählen Sie Ihr benutzerdefiniertes Schema als Zielgruppendimension aus.

   ![](assets/new-target-mapping.png)


1. Geben Sie die Felder an, in denen die Profilinformationen gespeichert sind: Nachname, Vorname, E-Mail, Adresse etc.

   ![](assets/wf_new_mapping_define_join.png)

1. Geben Sie die Parameter für die Speicherung der Informationen an, einschließlich des Suffix der Erweiterungsschemata, damit diese leicht identifiziert werden können.

   ![](assets/wf_new_mapping_define_names.png)

   Wählen Sie aus, ob Ausschlüsse (**excludelog**) mit Nachrichten (**broadlog**) oder in einer separaten Tabelle gespeichert werden sollen.

   Sie können für dieses Versand-Mapping (**trackinglog**) auch auswählen, ob Tracking verwaltet werden soll.

1. Wählen Sie dann die entsprechenden Erweiterungen aus. Der Erweiterungstyp hängt von Ihren Campaign-Einstellungen und Add-ons ab.

   ![](assets/wf_new_mapping_define_extensions.png)

   Klicken Sie auf die Schaltfläche **[!UICONTROL Speichern]**, um die Erstellung des Versand-Mappings zu beginnen: Alle verknüpften Tabellen werden automatisch auf der Basis der ausgewählten Parameter erstellt.
