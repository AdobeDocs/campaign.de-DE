---
product: campaign
title: Technote – Adobe Campaign-System-Upgrades
description: Adobe Campaign-System-Upgrade
hide: true
hidefromtoc: true
exl-id: 78949d94-60b3-44f1-8e5a-d61b5b723e87
source-git-commit: f1e963a880e8499dbbb16c44831a4ce1b537601f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 100%

---

# Umgebung-Upgrades für Adobe Campaign 2023 {#ac-system-upgrade}

Die Campaign-Infrastruktur beruht auf Drittanbietersystemen, die regelmäßig mit den neuesten Versionen und Fehlerbehebungen aktualisiert werden müssen. Diese Aktualisierungen sind obligatorisch, um die Kontinuität des Service und den Schutz von Campaign-Umgebungen vor Sicherheitsgefahren zu gewährleisten. Außerdem ist ein Campaign-Upgrade erforderlich, um die Kompatibilität mit Systemänderungen von Drittanbietern sicherzustellen.

Als **Kunde von Managed Cloud Services** werden Sie von Adobe über diese Upgrades informiert, wenn diese benötigt werden. Ihre Umgebungen müssen entsprechend den Empfehlungen aktualisiert werden, um Konformität zu gewährleisten.

Aus Sicherheitsgründen muss Adobe [den neuesten Campaign-Build installieren](#ac-upgrade) und anschließend Ihr [Betriebssystem](#os-upgrade) und/oder Ihr [Relation Database Management System (RDBMS)](#pg-upgrade) aktualisieren.

>[!NOTE]
>
>Wenden Sie sich bei Fragen zu diesen Änderungen an die [Adobe-Kundenunterstützung](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).

## Campaign-Build-Upgrade {#ac-upgrade}

**Sind Sie betroffen?**

Wenn Sie vom [Betriebssystem-Upgrade](#os-upgrade) und/oder vom [Datenbanksystem-Upgrade](#pg-upgrade) – wie im Folgenden genauer beschrieben – betroffen sind, muss Adobe Ihre Campaign-Umgebungen auf [die neueste Version 8.4.3](../../v8/start/release-notes.md) aktualisieren, die mit diesen Systemen kompatibel ist.

**Wie wird die Aktualisierung durchgeführt?**

Als Kunde von Managed Cloud Services wird Adobe Sie kontaktieren und Ihre Campaign-Version aktualisieren.

## Betriebssystem-Upgrade {#os-upgrade}

**Sind Sie betroffen?**

Wenn Sie Campaign auf einem Debian-Betriebssystem ausführen, muss Adobe Ihre Campaign-Infrastruktur auf **Debian 11** aktualisieren, damit Sie von den neuesten Debian-Sicherheitsaktualisierungen profitieren können. Bitte beachten, dass die Sicherheitsunterstützung für Debian 9 nur bis zum 30. Juni 2023 verfügbar sein wird.

**Wie wird die Aktualisierung durchgeführt?**

Als Kunde von Managed Cloud Services wird Adobe Sie kontaktieren und Ihre Umgebung aktualisieren.

## Upgrade des Datenbanksystems {#pg-upgrade}

**Sind Sie betroffen?**

Wenn Ihr Campaign-Datenbanksystem PostgreSQL ist, muss Adobe ein Upgrade auf **PostgreSQL 14** vornehmen, damit Sie von den neuesten PostgreSQL-Innovationen und -Sicherheitsaktualisierungen profitieren können. Bitte beachten, dass für PostgreSQL 11 am 9. November 2023 das Ende der Lebensdauer und damit der Unterstützung erreicht sein wird.

**Wie wird die Aktualisierung durchgeführt?**

Als Kunde von Managed Cloud Services wird Adobe Sie kontaktieren und Ihr Datenbanksystem von PostgreSQL 11 auf PostgreSQL 14 aktualisieren.
