---
title: Campaign-Versionen und -Upgrades
description: Weitere Informationen über die Campaign-Versionen und -Upgrades
feature: Release Notes
role: User
level: Beginner
exl-id: 04bda36f-051f-41a3-84b3-6af3c5e34ab2
source-git-commit: a779f243b0ba13dc3fcb7839377ca8766e5f7841
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 96%

---

# Versionen und Upgrades {#upgrades}

## Campaign-Versionen {#versions}

Adobe Campaign veröffentlicht regelmäßig Produktversionen, die die Leistung, Sicherheit, Logik und Benutzerfreundlichkeit der Campaign-Infrastruktur verbessern.

Bei den Upgrades kann es sich um folgende Arten handeln:

* **Wichtige Upgrades**, von einer Hauptversion auf eine andere, z. B. von v7 zu v8. Diese Upgrades beinhalten neue Funktionen, Verbesserungen, Kompatibilitäts- und Sicherheitsaktualisierungen sowie Fehlerbehebungen.
* **Geringfügige Upgrades**, von einer Nebenversion auf eine andere, z. B. von v8.5 auf v8.6. Diese Upgrades beinhalten Verbesserungen, Kompatibilitäts- und Sicherheitsaktualisierungen sowie Fehlerbehebungen.
* **Patch-Upgrades**, von einer Patch-Version zu einer anderen, z. B. von v8.5.1 bis v8.5.2. Diese Aktualisierungen bringen Sicherheitsupdates und -korrekturen mit sich.

Detaillierte Informationen zu den einzelnen neuen Versionen finden Sie in den [Versionshinweisen](release-notes.md).

Um eine stabile Konfiguration sicherzustellen, empfiehlt Adobe, **genau dieselbe Version** auf allen Campaign-Servern zu installieren. Außerdem muss sich die Client-Konsole, sofern in den [Versionshinweisen](release-notes.md) nicht anders angegeben, auf **genau derselben Version** wie die Server-Instanz befinden. Weitere Informationen dazu, wie Sie die Client-Konsole aktualisieren, erhalten Sie auf [dieser Seite](../start/connect.md#upgrade-ac-console).

Wenn Sie Kundin oder Kunde von Campaign Managed Services sind, wird Ihre Infrastruktur ohne weitere Maßnahmen Ihrerseits durch Adobe aktualisiert, sobald eine neue Campaign-Version verfügbar ist.

Beachten Sie, dass Sie als Kunde bzw. Kundin sicherstellen müssen, dass Sie die neuesten unterstützten Versionen der in der [Kompatibilitätsmatrix](compatibility-matrix.md) aufgeführten Systeme verwenden.


## Häufig gestellte Fragen {#upgrades-faq}

### So überprüfen Sie Ihre Campaign-Version {#version}

Öffnen Sie über die Client-Konsole das Menü **Hilfe > Über…**, um Ihre Campaign-Version zu überprüfen.

![](assets/ac-version.png)

Sie erhalten folgende Informationen:

* **Versionsnummer** Ihrer Client-Konsole und des Anwendungs-Servers. Im obigen Beispiel wird Version 8.1.5 der Client-Konsole und des Anwendungs-Servers verwendet.
* Die SHA-Nummer zwischen Klammern
* Link zur Adobe-Kundenunterstützung
* Links zur Adobe-Datenschutzrichtlinie sowie zu Nutzungsbedingungen und Bestimmungen zu Cookies.

### So erhalten Sie Informationen zu Veröffentlichungen neuer Versionen {#upgrades-0}

Neue Versionen und die Änderungen, die sie enthalten, werden in den [Versionshinweise](release-notes.md) aufgeführt. Sobald eine neue Version verfügbar ist, kontaktiert Adobe Sie und Ihre Umgebungen werden aktualisiert.

Abonnieren Sie das [Prioritätsprodukt-Update von Adobe](https://www.adobe.com/de/subscription/priority-product-update.html){target="_blank"}, um über neue Versionen der Experience Cloud-Lösungen informiert zu werden.

Sie können außerdem die [Campaign-Community](https://experienceleaguecommunities.adobe.com/t5/custom/page/page-id/Community-TopicsPage?style=all&amp;sort=date&amp;order=desc&amp;filters=adobe-campaign-classic-community&amp;topic=Campaign+v8){target="_blank"} besuchen, um Informationen über Versionsaktualisierungen zu erhalten.


### Warum benötigt meine Organisation dieses Upgrade? {#upgrades-1}

Durch die Aktualisierung Ihrer Infrastruktur auf die neueste Version wird sichergestellt, dass Ihr Konto vor Sicherheitslücken geschützt ist und dass die aktuelle Technologie verwendet wird.

Normalerweise bietet ein Upgrade auf die neueste Version Folgendes:

* Verbesserte Sicherheit

  Sicherheit erfordert eine ständige Überwachung und vorausschauende Wartung. Sicherheitsrisiken sind allgegenwärtig und können nicht ignoriert werden. Jedes Upgrade von Campaign verbessert die Sicherheit. Diese Upgrades müssen auf alle Campaign-Instanzen sowie auf die Client-Konsole angewendet werden. Eine Kombination von Technologien, die bei Adobe Campaign zum Einsatz kommen, sorgen gemeinsam für einen Mehrwert. Müssen alle diese Technologien auf dem neuesten Stand gehalten werden?

* Verbesserter Support

  Die meisten kritischen Probleme werden tatsächlich mit Upgrades behoben und können so vermieden werden. Regelmäßige Upgrades tragen dazu bei, die Herausforderungen, mit denen Sie konfrontiert werden, zu verringern und die Effizienz zu steigern, indem sie diese Probleme beseitigen. Der Bedarf an Kundenunterstützung wird reduziert, was schnellere Lösungen ermöglicht und mehr Zeit für Probleme lässt, die nicht mit Upgrades in Verbindung stehen.


* Verbesserte Wartung und Stabilität

  Im Laufe der Zeit ermittelt das Adobe Campaign-Team Möglichkeiten zur Verbesserung der Stabilität und Leistung des Produkts sowie zur Behebung bekannter Probleme. Durch die Aktualisierung wird Ihre Instanz mit diesen Verbesserungen auf dem neuesten Stand gehalten und die allgemeinen Herausforderungen für Unternehmen beseitigt, die in ihren Campaign-Instanzen ein rasches Wachstum und/oder eine schnelle Komplexität verzeichnen. Verbesserungen im gesamten Technologie-Stack von Campaign werden sowohl dem Marketing- als auch dem IT-Team Ihres Unternehmens zugutekommen.


### Wie sieht das Verfahren und der Zeitplan für dieses Upgrade aus? {#upgrades-2}

Als v8-Kunde oder -Kundin werden Sie von Adobe direkt benachrichtigt, wenn für Ihr Konto ein Upgrade auf eine neue Version erforderlich ist.

Das Adobe-Team begleitet Ihr Unternehmen durch diese Journey.  Zur Unterstützung wurde ein Team aus engagierten Mitarbeitenden der Kundenunterstützung, Produkt-Managern und -Managerinnen, Ingenieuren und Ingenieurinnen, TechOps-Spezialisten und -Spezialistinnen sowie Produktberatenden zusammengestellt, um ein möglichst reibungsloses Erlebnis zu gewährleisten.
