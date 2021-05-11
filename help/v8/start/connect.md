---
solution: Campaign
product: Adobe Campaign
title: Erfahren Sie, wie Sie eine Verbindung zur Kampagne v8 herstellen.
description: Verbindung zur Kampagne v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
translation-type: tm+mt
source-git-commit: 1ac6b58e1d5731d4df4d6d7c6a9b25f0f41ff563
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 13%

---

# Verbindung zu Adobe Campaign v8 {#gs-ac-connect}

Kampagne Client Console ist ein Rich-Client, mit dem Sie eine Verbindung zu den Anwendungsservern Ihrer Kampagne herstellen können.

Bevor Sie beginnen, müssen Sie:

* Überprüfen Sie die Kompatibilität Ihres Systems und Ihrer Tools mit Adobe Campaign in der Kompatibilitätsmatrix [a1/>](compatibility-matrix.md)
* Abrufen der Kampagne-Server-URL
* Benutzeranmeldeinformationen abrufen

## Herunterladen und Installieren der Client-Konsole

Wenn Sie Kampagne zum ersten Mal verwenden oder auf eine neuere Version aktualisieren müssen, müssen Sie die Client-Konsole herunterladen und installieren.

Dazu sind zwei Optionen verfügbar:

1. Als Kampagne-Administrator stellen Sie eine Verbindung zur Adobe [Softwareverteilung](https://experience.adobe.com/#/downloads/content/software-distribution/encampaign.html) her und laden Sie das Client Console-Programm herunter. Sie können es dann auf Ihrem lokalen Computer installieren.

1. Als Endbenutzer kann Adobe die Konsole für Sie bereitstellen: Sobald die Konsole aktualisiert wurde, werden Sie aufgefordert, die neueste Version der Client-Konsole in einem Popup-Fenster herunterzuladen.

>[!CAUTION]
>
>Adobe empfiehlt, die Option **[!UICONTROL Diese Frage]** nicht mehr zu stellen, um sicherzustellen, dass alle Benutzer benachrichtigt werden, wenn eine neue Version der Konsole verfügbar ist.  Wenn diese Option aktiviert ist, wird der Benutzer nicht über neue verfügbare Versionen informiert.

## Verbindung erstellen

Nachdem die Client-Konsole neu installiert wurde, führen Sie die folgenden Schritte aus, um die Verbindung zum Anwendungsserver herzustellen:

1. Beginn Sie die Konsole aus dem Menü Windows **[!UICONTROL Beginn]** in der Gruppe **Adobe Campaign** Programm.

1. Klicken Sie auf den Link in der oberen rechten Ecke der Felder mit den Anmeldeinformationen, um das Fenster für die Verbindungskonfiguration aufzurufen.

1. Klicken Sie auf **[!UICONTROL Hinzufügen > Verbindung]** und geben Sie die Bezeichnung und URL des Adobe Campaign-Anwendungsservers ein.

1. Geben Sie über eine URL eine Verbindung zum Adobe Campaign-Anwendungsserver an. Verwenden Sie entweder ein DNS oder einen Alias des Computers oder Ihre IP-Adresse.

   Sie können beispielsweise die URL [`https://<machine>.<domain>.com`](https://myserver.adobe.com) eingeben.

1. Wenn Adobe Identity Management System (IMS) für Ihr Unternehmen konfiguriert ist, aktivieren Sie die Option **[!UICONTROL Mit einem Adobe ID]** verbinden.

1. Klicken Sie auf **[!UICONTROL OK]**, um Ihre Einstellungen zu speichern.

Sie können z. B. so viele Verbindungen wie erforderlich hinzufügen, um eine Verbindung zu Ihren Test-, Stage- und Produktionsfunktionen herzustellen.

>[!NOTE]
>
>Die Schaltfläche **[!UICONTROL Hinzufügen]** erlaubt die Erstellung von **[!UICONTROL Ordnern]**, in die Sie Ihre verschiedenen Verbindungen per Drag&amp;Drop verschieben können.

## Bei Adobe Campaign anmelden

Gehen Sie wie folgt vor, um sich bei einer vorhandenen Instanz anzumelden:

1. Beginn Sie die Konsole aus dem Menü Windows **[!UICONTROL Beginn]** in der Gruppe **Adobe Campaign** Programm.

1. Klicken Sie auf den Link in der oberen rechten Ecke der Felder mit den Anmeldeinformationen, um das Fenster für die Verbindungskonfiguration aufzurufen.

1. Wählen Sie die Kampagne aus, bei der Sie sich anmelden müssen.

1. Bestätigen Sie die Aktion mit der Schaltfläche **[!UICONTROL OK]**.

1. Geben Sie Ihre Anmeldedaten für den Benutzer ein und klicken Sie auf **[!UICONTROL ANMELDEN]**.

   ![](assets/sign-in-v8.png)

Abhängig von Ihrer Konfiguration können Ihre Anmeldedaten wie folgt lauten:

* bereitgestellt von Ihrem Kampagnen-Administrator, der Ihnen Zugriff gewährt hat
* Adobe ID

## Benutzern Zugriff gewähren

Adobe Campaign ermöglicht es, die den unterschiedlichen Benutzern zugeteilten Rechte zu bestimmen und zu verwalten. Es handelt es sich um Berechtigungen und Beschränkungen folgender Aktivitäten:

* Zugriff auf bestimmte Funktionen (über spezifische Berechtigungen);
* Zugang zu bestimmten Elementen,
* Erstellen, ändern und/oder löschen Sie Elemente (Versand, Kontakte, Kampagnen, Gruppen usw.).

Weitere Informationen zu Benutzern und zum Definieren ihrer Berechtigungen finden Sie in [diesem Abschnitt](permissions.md).

Als Administrator für Kampagnen sind Sie dafür verantwortlich, die Operatoren zu erstellen und ihre Anmeldeinformationen für die Benutzer freizugeben.

## Mit dem Adobe ID verbinden{#connect-ims}

Kampagne-Benutzer können über das Adobe ID über Adobe Identity Management System (IMS) eine Verbindung zur Adobe Campaign-Konsole herstellen. Diese Implementierung bietet die folgenden Vorteile:

* Verwendung ein und derselben ID für alle Adobe Experience Cloud-Lösungen;
* Speicherung der Verbindung bei der Verwendung von Adobe Campaign mit den verschiedenen Integrationen;
* Strengere Richtlinien für die Kennwortverwaltung.
* Verwendung von Konten des Typs Federated ID (externer Identity Provider).

:language_ballon: Als Benutzer mit Managed Cloud Services [wenden Sie sich an die Adobe ](support.md#support), um die Adobe IMS mit Kampagne zu implementieren.

## Verbindung zur Kampagne mit Ihrer LDAP-Anmeldung

Adobe Campaign kann so konfiguriert werden, dass der Benutzer über seine LDAP-Authentifizierung auf die Plattform zugreift.

:language_ballon: Als Benutzer mit verwaltetem Cloud Services [wenden Sie sich an die Adobe](support.md#support), um die LDAP-Integration mit Kampagne zu konfigurieren.


## Webzugriff

Bestimmte Teile der Anwendung können über einen einfachen Webbrowser über eine HTML-Benutzeroberfläche aufgerufen werden: Berichte, Genehmigung des Versands, Instanzüberwachung und mehr.
