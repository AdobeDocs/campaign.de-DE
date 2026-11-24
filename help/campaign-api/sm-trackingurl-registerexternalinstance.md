---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 37%
---
# RegisterExternalInstance

Validiert eine Trackinginstanz auf einem Relais-Server in Richtung der Weiterleitungsserver (durch Festlegung der Datenbankkennung)

```text
RegisterExternalInstance ( String login, String instanceName, String dbId, Boolean saveParams )
```

## Parameter

**login** Relay-Serverzugriff-Anmeldung

**instanceName** Name der zu validierenden Instanz

**dbId** Datenbankkennung des Kunden, der einen Versand durchführt

**saveParams** Optionen bei Erfolg speichern

## Rückgabewert(e)

Keine.

## Funktionen

**Schema:** [nms:trackingUrl](s-nms-trackingurl.md)

**static:**

Ja
