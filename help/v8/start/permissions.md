---
title: Berechtigungen für Campaign v8 erteilen
description: Erfahren Sie, wie Sie Berechtigungen für Campaign v8 erteilen
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 100%

---

# Erste Schritte mit Berechtigungen

In Adobe Campaign sind Benutzer **Operatoren** und **Operatorgruppen** stehen für Benutzerrollen.

Ein Operator ist ein Benutzer von Adobe Campaign, der die Berechtigung besitzt, sich anzumelden und Aktionen durchzuführen. Operatoren werden standardmäßig im Knoten **[!UICONTROL Administration > Zugriffe > Operatoren]** gespeichert.

Adobe Campaign verfügt über native Operatorgruppen wie &quot;Kampagnenverantwortliche Benutzer&quot; oder &quot;Workflow-Supervisoren&quot;. Alle integrierten Gruppen sind in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=de#default-groups) aufgeführt.{target=&quot;_blank&quot;}.

Als Mitglied einer Operatorgruppe verfügt ein Benutzer über Rechte zur Durchführung von Vorgängen, sogenannte &quot;Spezifische Berechtigungen&quot;, und er hat Zugriff auf Daten, die in Ordnern in der **Explorer**-Ansicht enthalten sind. Ein Operator kann Mitglied in mehreren Operatorgruppen sein: Rechte und Zugriffsberechtigungen sind additiv.

Spezifische Berechtigungen gewähren Berechtigungen für:

* Vorgänge ausführen
Zum Beispiel ist die Schaltfläche **Analysieren** im Versand-Editor für Mitglieder der Gruppe **Versandoperatoren** aktiviert, die die spezifische Berechtigung **Versand vorbereiten** besitzen.

* Zugriff auf Ordner
Mitglieder von Operatorgruppen können Zugriffsrechte auf Ordner gewähren oder einschränken, indem sie die Sicherheitseinstellungen von Ordnern ändern. [Weitere Informationen finden Sie in der Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=de#permissions-on-a-folder){target=&quot;_blank&quot;}. Zum Beispiel kann es diese Auswirkungen haben: **Schreibzugriff** zum Erstellen neuer Entitäten (wie Sendungen, Profile usw.), **Lesezugriff** zum Verwenden von Entitäten, **Löschzugriff** zum Löschen von Entitäten.

## Sicherheitszonen

Jeder Operator muss mit einer Zone verknüpft sein, um sich bei einer Instanz anmelden zu können, und die IP des Operators muss in die Adressen oder Adresssätze aufgenommen werden, die in der Sicherheitszone definiert sind. Die Konfiguration der Sicherheitszone erfolgt in der Konfigurationsdatei des Adobe Campaign-Servers.

Operatoren werden über ihr Profil in der Konsole mit einer Sicherheitszone verknüpft, auf die über den Knoten **[!UICONTROL Administration > Zugriffe > Operatoren]** zugegriffen werden kann.

![](../assets/do-not-localize/speech.png) Adobe legt für Sie als Benutzer von Managed Cloud Services die Sicherheitszonen fest. Weitere Informationen finden Sie unter [Adobe kontaktieren](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}.

**Weitere Informationen finden Sie in der Dokumentation zu Campaign Classic v7**

* [Native spezifische Berechtigungen](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html?lang=de){target=&quot;_blank&quot;}

* [Native Operatorgruppen](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

* [Schritte zum Einrichten von Berechtigungen](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=de#getting-started){target=&quot;_blank&quot;}
