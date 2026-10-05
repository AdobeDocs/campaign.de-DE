---
product: campaign
title: Technote – Adobe Campaign-System-Upgrades
description: Adobe Campaign-System-Upgrade
hide: true
exl-id: cc64cce1-2473-4136-aadc-8b13e89ef7f9
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 100%
---
# Umgebung-Upgrades für Adobe Campaign 2023 {#ac-system-upgrade}

Die Campaign-Infrastruktur beruht auf Drittanbietersystemen, die regelmäßig mit den neuesten Versionen und Fehlerbehebungen aktualisiert werden müssen. Diese Aktualisierungen sind obligatorisch, um die Kontinuität des Service und den Schutz von Campaign-Umgebungen vor Sicherheitsgefahren zu gewährleisten. Außerdem ist ein Campaign-Upgrade erforderlich, um die Kompatibilität mit Systemänderungen von Drittanbietern sicherzustellen.

Als **Kunde von Managed Cloud Services** werden Sie von Adobe über diese Upgrades informiert, wenn diese benötigt werden. Ihre Umgebungen müssen entsprechend den Empfehlungen aktualisiert werden, um Konformität zu gewährleisten.

Aus Sicherheitsgründen muss Adobe [den neuesten Campaign-Build installieren](#ac-upgrade) und anschließend Ihr [Betriebssystem](#os-upgrade) und/oder Ihr [Relation Database Management System (RDBMS)](#pg-upgrade) aktualisieren.

>[!NOTE]
>
>Wenden Sie sich bei Fragen zu diesen Änderungen an die [Adobe-Kundenunterstützung](https://helpx.adobe.com/de/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>

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
