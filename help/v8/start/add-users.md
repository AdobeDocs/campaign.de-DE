---
title: Berechtigungen für Campaign v8 erteilen
description: Erfahren Sie, wie Sie Berechtigungen für Campaign v8 erteilen
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: ht
source-wordcount: '310'
ht-degree: 100%

---

# Erste Schritte mit Berechtigungen

In Adobe Campaign sind Anwender **Benutzer** und **Benutzergruppen** stehen für Benutzerrollen. 

Ein Anwender ist ein Benutzer von Adobe Campaign, der die Berechtigung besitzt, sich anzumelden und Aktionen durchzuführen. Operatoren werden standardmäßig im Knoten **[!UICONTROL Administration > Zugriffe > Operatoren]** gespeichert.

Adobe Campaign verfügt über native Operatorgruppen wie &quot;Kampagnenverantwortliche Benutzer&quot; oder &quot;Workflow-Supervisoren&quot;. Weiterführende Informationen zu Berechtigungen finden Sie in [diesem Abschnitt](../start/gs-permissions.md)

Als Mitglied einer Operatorgruppe verfügt ein Benutzer über Rechte zur Durchführung von Vorgängen, sogenannte &quot;Spezifische Berechtigungen&quot;, und er hat Zugriff auf Daten, die in Ordnern in der **Explorer**-Ansicht enthalten sind. Ein Anwender kann Mitglied in mehreren Anwendegruppen sein: Rechte und Zugriffsberechtigungen sind additiv.

Spezifische Berechtigungen gewähren Berechtigungen für:

* Vorgänge ausführen
Zum Beispiel ist die Schaltfläche **Analysieren** im Versand-Editor für Mitglieder der Gruppe **Versandoperatoren** aktiviert, die die spezifische Berechtigung **Versand vorbereiten** besitzen.

* Zugriff auf Ordner
Mitglieder von Operatorgruppen können Zugriffsrechte auf Ordner gewähren oder einschränken, indem sie die Sicherheitseinstellungen von Ordnern ändern. Weitere Informationen finden Sie auf [dieser Seite](../start/folder-permissions.md). Zum Beispiel kann es diese Auswirkungen haben: **Schreibzugriff** zum Erstellen neuer Entitäten (wie Sendungen, Profile usw.), **Lesezugriff** zum Verwenden von Entitäten, **Löschzugriff** zum Löschen von Entitäten.

## Sicherheitszonen

Jeder Operator muss mit einer Zone verknüpft sein, um sich bei einer Instanz anmelden zu können, und die IP des Operators muss in die Adressen oder Adresssätze aufgenommen werden, die in der Sicherheitszone definiert sind. Die Konfiguration der Sicherheitszone erfolgt in der Konfigurationsdatei des Adobe Campaign-Servers.

Operatoren werden über ihr Profil in der Konsole mit einer Sicherheitszone verknüpft, auf die über den Knoten **[!UICONTROL Administration > Zugriffe > Operatoren]** zugegriffen werden kann.

>[!NOTE]
>
>Adobe legt für Sie als Benutzende von Managed Cloud Services die Sicherheitszonen fest. Nehmen Sie für weitere Information [Kontakt mit Adobe auf](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**Weitere Informationen**

* [Native spezifische Berechtigungen](../start/gs-permissions.md)

* [Schritte zum Einrichten von Berechtigungen](../start/manage-permissions.md)
