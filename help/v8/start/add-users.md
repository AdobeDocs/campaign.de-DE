---
title: Berechtigungen für Campaign v8 erteilen
description: Erfahren Sie, wie Sie Berechtigungen für Campaign v8 erteilen
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
    internal-label: Permissions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 83%
---
# Erste Schritte mit Berechtigungen

In Adobe Campaign sind Anwender **Benutzer** und **Benutzergruppen** stehen für Benutzerrollen.

Ein Benutzer ist ein Benutzer von Adobe Campaign, der die Berechtigung besitzt, sich anzumelden und Aktionen durchzuführen. Benutzerprofile werden standardmäßig im Knoten **[!UICONTROL Administration > Zugriffe > Benutzer]** gespeichert.

Adobe Campaign verfügt über native Operatorgruppen wie &quot;Kampagnenverantwortliche Benutzer&quot; oder &quot;Workflow-Supervisoren&quot;. Weiterführende Informationen zu Berechtigungen finden Sie in [diesem Abschnitt](../start/gs-permissions.md)

Als Mitglied einer Operatorgruppe verfügt ein Benutzer über Rechte zur Durchführung von Vorgängen, sogenannte &quot;Spezifische Berechtigungen&quot;, und er hat Zugriff auf Daten, die in Ordnern in der **Explorer**-Ansicht enthalten sind. Eine Person kann Mitglied in mehreren Anwendegruppen sein: Rechte und Zugriffsberechtigungen sind additiv.

Spezifische Berechtigungen gewähren Berechtigungen für:

* Durchführen von Vorgängen
Beispielsweise ist die Schaltfläche **Analysieren** im Versand-Editor für Mitglieder der Gruppe **Versandoperatoren** aktiviert, die über die spezifische Berechtigung **Versand vorbereiten** verfügen

* Zugriff auf Ordner
Mitglieder von Operatorgruppen können Zugriffsrechte auf Ordner gewähren oder einschränken, indem sie die Sicherheitseinstellungen von Ordnern ändern. Weitere Informationen finden Sie auf [dieser Seite](../start/folder-permissions.md). Zum Beispiel kann es diese Auswirkungen haben: **Schreibzugriff** zum Erstellen neuer Entitäten (wie Sendungen, Profile usw.), **Lesezugriff** zum Verwenden von Entitäten, **Löschzugriff** zum Löschen von Entitäten.

## Sicherheitszonen

Jeder Operator muss mit einer Zone verknüpft sein, um sich bei einer Instanz anmelden zu können, und die IP des Operators muss in die Adressen oder Adresssätze aufgenommen werden, die in der Sicherheitszone definiert sind. Die Konfiguration der Sicherheitszone erfolgt in der Konfigurationsdatei des Adobe Campaign-Servers.

Operatoren werden über ihr Profil in der Konsole mit einer Sicherheitszone verknüpft, auf die über den Knoten **[!UICONTROL Administration > Zugriffe > Operatoren]** zugegriffen werden kann.

>[!NOTE]
>
>Adobe legt für Sie als Benutzende von Managed Cloud Services die Sicherheitszonen fest. Weitere Informationen finden Sie unter [Adobe kontaktieren](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**Weitere Informationen**

* [Native spezifische Berechtigungen](../start/gs-permissions.md)

* [Schritte zum Einrichten von Berechtigungen](../start/manage-permissions.md)
