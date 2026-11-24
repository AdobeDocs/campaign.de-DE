---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 23%
---
# batchDelete

Löscht die Datensätze einer Tabelle nach Paketen.

```text
batchDelete (table, pk [, where ])
```

## Parameter

**table** SQL-Name der Tabelle.

**pk** Feldname wird als Primärschlüssel verwendet.

**where** SQL-Eintragsfilterbedingung.

## Rückgabewert

Keine.

## Bemerkungen

Beispiel:

```javascript
      engine.batchDelete("NmsRecipient", "iRecipientId", "sName IS NULL")
```

Der Operator benötigt „SQL“-Rechte, um diese Funktion verwenden zu können. Andernfalls wird eine Ausnahme ausgelöst.

## Funktionen

**Methode der Klasse:** [DBEngine](c-dbengine.md)

**Verfügbar in:**

* Content-Management
* Versandeigenschaften
* Typologieregel
* JSSP
* SOAP-Methoden
* WebApp
* Workflow
