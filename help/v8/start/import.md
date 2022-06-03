---
title: Erste Schritte mit Profilen
description: Erste Schritte mit Profilen
feature: Profiles
role: Data Engineer
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: ht
source-wordcount: '321'
ht-degree: 100%

---

# Daten in Campaign importieren {#ootb-profiles}

Mit Campaign können Sie der Cloud-Datenbank Kontakte hinzufügen. Sie können eine Datei laden, mehrere Kontaktaktualisierungen planen und automatisieren, Daten im Internet sammeln oder Profilinformationen direkt in die Empfängertabelle eingeben.

![](../assets/do-not-localize/glass.png) Erste Schritte mit [Audiences](audiences.md)

![](../assets/do-not-localize/glass.png) Verstehen des Campaign-[Datenmodells](../dev/datamodel.md)

## Profile in einen Workflow importieren

Profilimporte werden in speziellen Vorlagen konfiguriert, die durch Workflows über die Aktivität **Importieren** ausgeführt werden. Sie können automatisch anhand eines Zeitplans wiederholt werden, um beispielsweise den Datenaustausch zwischen verschiedenen Informationssystemen zu automatisieren. Weitere Informationen finden Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/import-export-workflows.html?lang=de){target=&quot;_blank&quot;}.

![](assets/import-wf.png)

Weitere Informationen finden Sie in der Dokumentation zu Campaign Classic v7:

* [Erste Schritte mit Importen und Exporten](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/get-started-data-import-export.html?lang=de#getting-started){target=&quot;_blank&quot;}

* [Best Practices für Import und Export](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/best-practices/import-export-best-practices.html?lang=de#getting-started){target=&quot;_blank&quot;}

* [Import konfigurieren und ausführen](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=de#getting-started){target=&quot;_blank&quot;}

## Einheitlichen Importe ausführen

Erstellen Sie einen generischen Datenimportauftrag zum Laden von Kontakten in die Cloud-Datenbank und führen Sie ihn aus.

![](assets/new-import.png)

![](../assets/do-not-localize/book.png) Erfahren Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=de#getting-started){target=&quot;_blank&quot;}, wie Sie einzelne Importvorgänge ausführen, um Ihre Datenbank zu befüllen.

## Erfassen von Profilen über Web-Anwendungen

Verwenden Sie Campaign, um Web-Formulare zu erstellen und Profilinformationen einfach und effizient zu erfassen und zu verwalten. Sie können diese Formulare auf Ihrer Website freigeben, sodass Ihre Kontakte ihre Informationen einfach bereitstellen können. Ihre Informationen werden an Campaign gesendet, um ein Profil zu erstellen oder dessen Daten zu aktualisieren, sofern diese bereits in der Datenbank vorhanden sind.

![](assets/web-form-page.png)

![](../assets/do-not-localize/book.png) Wie Sie Web-Formulare erstellen, erfahren Sie in der [Dokumentation zu Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html?lang=de){target=&quot;_blank&quot;}.

**Verwandte Themen**

* [Audiences erstellen](audiences.md)
* [Profile deduplizieren](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/deduplication-merge.html?lang=de#automating-with-workflows){target=&quot;_blank&quot;}
* [Profildaten anreichern](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html?lang=de#automating-with-workflows){target=&quot;_blank&quot;}
