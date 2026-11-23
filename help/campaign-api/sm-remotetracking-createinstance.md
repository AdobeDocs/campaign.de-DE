---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 15%
---
# CreateInstance

> Warnung: Diese Funktion ist für eine On-Premise-Umgebung verfügbar.

Ermöglicht die Erstellung einer Trackinginstanz

```text
CreateInstance ( String instanceName, String hosts, String dbId, String cryptedPwd, String lang )
```

## Parameter

**instanceName** Name der zu erstellenden Instanz

**hosts** DNS-Masken, die mit der Instanz verknüpft sind

**dbId** Datenbankkennung des Kunden, der einen Versand durchführt

**cryptedPwd** Verschlüsseltes Kennwort für das Tracking

**lang** Instanzsprache

## Rückgabewert(e)

Keine.

## Funktionen

**Schema:** [nms:remoteTracking](s-nms-remotetracking.md)

**static:**

Ja
