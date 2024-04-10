---
title: Erste Schritte mit Profilen
description: Erste Schritte mit Profilen
feature: Profiles, Data Management
role: User
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: ht
source-wordcount: '213'
ht-degree: 100%

---

# Daten in Campaign importieren {#ootb-profiles}

Mit Campaign können Sie der Cloud-Datenbank Kontakte hinzufügen. Sie können eine Datei laden, mehrere Kontaktaktualisierungen planen und automatisieren, Daten im Internet sammeln oder Profilinformationen direkt in die Empfängertabelle eingeben.

Erste Schritte mit [Zielgruppen](audiences.md)

Grundlegendes zum [Datenmodell](../dev/datamodel.md) von Campaign

## Profile in einen Workflow importieren

Profilimporte werden in speziellen Vorlagen konfiguriert, die durch Workflows über die Aktivität **Importieren** ausgeführt werden. Sie können automatisch anhand eines Zeitplans wiederholt werden, um beispielsweise den Datenaustausch zwischen verschiedenen Informationssystemen zu automatisieren. Weiterführende Informationen finden Sie in [diesem Abschnitt](../../automation/workflow/recurring-import-workflow.md).

![](assets/import-wf.png)


## Einheitlichen Importe ausführen

Erstellen Sie einen generischen Datenimportauftrag zum Laden von Kontakten in die Cloud-Datenbank und führen Sie ihn aus.

![](assets/new-import.png)

In der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=de){target="_blank"} erfahren Sie, wie Sie einzelne Importvorgänge ausführen, um Ihre Datenbank zu befüllen.

## Erfassen von Profilen über Web-Anwendungen

Verwenden Sie Campaign, um Web-Formulare zu erstellen und Profilinformationen einfach und effizient zu erfassen und zu verwalten. Sie können diese Formulare auf Ihrer Website freigeben, sodass Ihre Kontakte ihre Informationen einfach bereitstellen können. Ihre Informationen werden an Campaign gesendet, um ein Profil zu erstellen oder dessen Daten zu aktualisieren, sofern diese bereits in der Datenbank vorhanden sind.

![](assets/web-form-page.png)

In der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html?lang=de){target="_blank"} erfahren Sie, wie Sie Web-Formulare erstellen.

**Verwandte Themen**

* [Zielgruppen erstellen](audiences.md)
* [Profile deduplizieren](../../automation/workflow/deduplication-merge.md)
* [Profildaten anreichern](../../automation/workflow/enrich-data.md)
