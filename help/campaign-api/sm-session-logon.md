---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 3%
---
# Anmelden

Eröffnet eine Sitzung

```text
[ String sessionToken, sessionInfo sessionInfo, String securityToken ] = Logon ( String login, String password, XML parameters )
```

## Parameter

**login** Benutzerkonto

**password** Kennwort, das dem Benutzerlogin zugeordnet ist

**Parameter** Verbindungseinstellungen

## Rückgabewert(e)

**sessionToken** Sitzungstoken

**sessionInfo** Sitzungsparameter

**securityToken** Security-Token

## Konfiguration des Kontosperrmechanismus

In der login()-API ist ein Mechanismus zur Kontosperrung verfügbar. Sie verhindert alle weiteren Anmeldeversuche nach einer bestimmten Anzahl aufeinander folgender fehlgeschlagener Anmeldeversuche innerhalb eines bestimmten Zeitraums.

Es stehen vier Optionen zur Konfiguration des Sperrmechanismus zur Verfügung:

* **XtkSecurity\_max\_Unsuccessul\_Attempts\_Allowed**: Max. erfolgloser Versuch, einen Schlüssel innerhalb einer bestimmten Dauer zu blockieren. Der Standardwert ist 3.
* **XtkSecurity\_Initial\_Ban\_Duration**: Dauer, für die der Schlüssel zum ersten Mal gesperrt wird. Die Standarddauer beträgt 5 Minuten.
* **XtkSecurity\_Max\_Ban\_Duration**: Maximale Dauer, für die ein Schlüssel gesperrt werden kann.
* **XtkSecurity\_Examine\_Window**: Zeitfenster zur Verfolgung der Anzahl erfolgloser Anmeldeversuche zum Sperren eines ungültigen Schlüssels. Die Standarddauer beträgt 10 Minuten.

Wenn beispielsweise jemand drei erfolglose Versuche innerhalb von 10 Minuten unternimmt, wird sein Schlüssel für 5 Minuten blockiert.

## Funktionen

**Schema:** [xtk:session](s-xtk-session.md)

**static:**

Ja
