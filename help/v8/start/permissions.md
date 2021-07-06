---
product: Adobe Campaign
title: Berechtigungen für Campaign v8 erteilen
description: Erfahren Sie, wie Sie Berechtigungen für Campaign v8 erteilen
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Erste Schritte mit Berechtigungen

In Adobe Campaign sind Benutzer **Operatoren** und **Operatorgruppen** stehen für Benutzerrollen.

Adobe Campaign verfügt über native Operatorgruppen wie &quot;Kampagnenverantwortliche Benutzer&quot; oder &quot;Workflow-Supervisoren&quot;. Alle integrierten Gruppen sind in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=de#default-groups) aufgeführt.

Als Mitglied einer Operatorgruppe verfügt ein Benutzer über Rechte zur Durchführung von Vorgängen, sogenannte &quot;Spezifische Berechtigungen&quot;, und er hat Zugriff auf Daten, die in Ordnern in der **Explorer**-Ansicht enthalten sind. Ein Operator kann Mitglied in mehreren Operatorgruppen sein: Rechte und Zugriffsberechtigungen sind additiv.

Spezifische Berechtigungen gewähren Berechtigungen für:

* Vorgänge ausführen
Zum Beispiel ist die Schaltfläche **Analysieren** im Versand-Editor für Mitglieder der Gruppe **Versandoperatoren** aktiviert, die die spezifische Berechtigung **Versand vorbereiten** besitzen.

* Zugriff auf Ordner
Mitglieder von Operatorgruppen können Zugriffsrechte auf Ordner gewähren oder einschränken, indem sie die Sicherheitseinstellungen von Ordnern ändern. [Weitere Informationen finden Sie in der Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=de#permissions-on-a-folder){target=&quot;_blank&quot;}. Zum Beispiel kann es diese Auswirkungen haben: **Schreibzugriff** zum Erstellen neuer Entitäten (wie Sendungen, Profile usw.), **Lesezugriff** zum Verwenden von Entitäten, **Löschzugriff** zum Löschen von Entitäten.

**Weitere Informationen**   in der Dokumentation zu Campaign Classic v7:

[!DNL :arrow_upper_right:] [Native spezifische Berechtigungen](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html?lang=de){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Native Benutzergruppen](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Schritte zum Einrichten von Berechtigungen](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=de#getting-started){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Sicherheitseinstellungen für Ordner](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}