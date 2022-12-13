---
product: campaign
title: Technote – Adobe Campaign-System-Upgrades
description: Adobe Campaign-System-Upgrade
hide: true
hidefromtoc: true
exl-id: 78949d94-60b3-44f1-8e5a-d61b5b723e87
source-git-commit: 3535e1e4fcd326412b6378253e5dde1249bce1f2
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 40%

---

# Umgebung-Upgrades für Adobe Campaign 2023 {#ac-system-upgrade}

Die Campaign-Infrastruktur beruht auf Drittanbietersystemen, die regelmäßig mit den neuesten Versionen und Fehlerbehebungen aktualisiert werden müssen. Diese Aktualisierungen sind obligatorisch, um die Kontinuität des Service und den Schutz von Campaign-Umgebungen vor Sicherheitsgefahren zu gewährleisten. Außerdem ist ein Campaign-Upgrade erforderlich, um die Kompatibilität mit Systemänderungen von Drittanbietern sicherzustellen.

Als **Managed Cloud Services-Kunde**, informiert Sie Adobe über diese Aktualisierungen, wenn sie benötigt werden. Ihre Umgebungen müssen entsprechend den Empfehlungen aktualisiert werden, um die Einhaltung der Vorschriften sicherzustellen.

Aus Sicherheitsgründen muss die Adobe [Installieren des aktuellen Campaign-Builds](#ac-upgrade), und aktualisieren Sie anschließend Ihre [Betriebssystem](#os-upgrade) und/oder Ihre [Relation Database Management System (RDBMS)](#pg-upgrade).

>[!NOTE]
>
>Wenden Sie sich bei Fragen zu diesen Änderungen an die [Adobe-Kundenunterstützung](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).

## Campaign-Build-Upgrade {#ac-upgrade}

**Sind Sie betroffen?**

Wenn Sie von der [Betriebssystemaktualisierung](#os-upgrade) und/oder [Datenbanksystemaktualisierung](#pg-upgrade) Im Folgenden wird beschrieben, wie Adobe Ihre Campaign-Umgebungen auf [die neueste Version 8.4.3](../../v8/start/release-notes.md), die mit diesen Systemen kompatibel ist.

**Wie wird die Aktualisierung durchgeführt?**

Als Managed Cloud Services-Kunde kontaktiert Adobe Sie und aktualisiert Ihre Campaign-Version.

## Betriebssystem-Upgrade {#os-upgrade}

**Sind Sie betroffen?**

Wenn Sie Campaign auf einem Debian-Betriebssystem ausführen, muss Adobe Ihre Campaign-Infrastruktur auf **Debian 11**. Bitte beachten, dass die Sicherheitsunterstützung für Debian 9 nur bis zum 30. Juni 2023 verfügbar sein wird.

**Wie wird die Aktualisierung durchgeführt?**

Als Managed Cloud Services-Kunde kontaktiert Adobe Sie und aktualisiert Ihre Umgebung.

## Upgrade des Datenbanksystems {#pg-upgrade}

**Sind Sie betroffen?**

Wenn Ihr Campaign-Datenbanksystem PostgreSQL ist, muss Adobe ein Upgrade auf **PostgreSQL 14**. Bitte beachten, dass für PostgreSQL 11 am 9. November 2023 das Ende der Lebensdauer und damit der Unterstützung erreicht sein wird.

**Wie wird die Aktualisierung durchgeführt?**

* Als Managed Cloud Services-Kunde kontaktiert Adobe Sie und aktualisiert Ihr Datenbanksystem von PostgreSQL 11 auf PostgreSQL 14.
