---
solution: Campaign v8
product: Adobe Campaign
title: PI-Ansicht beschränken
description: Erfahren Sie, wie Sie die PI-Ansicht einschränken
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 0%

---

# Einschränken der PI-Ansicht{#restricting-pii-view}

## Übersicht {#overview}

Wenn Sie möchten, dass Marketing-Benutzer auf Datendatensätze zugreifen können, aber keine personenbezogenen Daten (PIs) des Empfängers anzeigen können, wie z. B. Vorname, Nachname oder E-Mail-Adresse, wenden Sie die unten stehenden Richtlinien an, um den Datenschutz zu schützen und zu verhindern, dass Daten von regulären Kampagnenbetreibern missbraucht werden.

## Umsetzung {#implementation}

Den Schemas wurde ein spezifisches Attribut hinzugefügt, das auf beliebige Elemente oder Attribute angewendet werden kann. Es ergänzt das vorhandene Attribut **[!UICONTROL visibleIf]** . Dieses Attribut lautet: **[!UICONTROL accessibleIf]** . Wenn Sie einen XTK-Ausdruck enthalten, der sich auf den aktuellen Benutzerkontext bezieht, kann er z. B. **[!UICONTROL HasNamedRight]** oder **[!UICONTROL $(login)]** nutzen.

Nachfolgend finden Sie ein Beispiel für eine Empfängerschema-Erweiterung, die diese Verwendung zeigt:

```
<srcSchema desc="Recipient table (profiles" entitySchema="xtk:srcSchema" extendedSchema="xxl:nmsRecipientXl"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient"
           name="recipient" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Recipient table (profiles" img="xxl:recipient.png" label="Recipients"
           labelSingular="Recipient" name="recipient">
    <attribute name="firstName" accessibleIf="$(login)=='admin'"/>
    <attribute name="lastName" visibleIf="$(login)=='admin'"/>
    <attribute name="email" accessibleIf="$(login)=='admin'"/>
  </element>
</srcSchema>
```

Die Haupteigenschaften sind:

* **[!UICONTROL visibleIf]** : blendet die Felder aus den Metadaten aus, sodass sie nicht in einer Schemaansicht, Spaltenauswahl oder einem Ausdruckseditor aufgerufen werden können. Dabei werden jedoch keine Daten ausgeblendet, wenn der Feldname manuell in einen Ausdruck eingegeben wird, wird der Wert angezeigt.
* **[!UICONTROL accessibleIf]** : blendet die Daten aus der resultierenden Abfrage aus (durch leere Werte ersetzen). Wenn visibleIf leer ist, erhält es denselben Ausdruck wie **[!UICONTROL accessibleIf]** .

Die Verwendung dieses Attributs in Campaign hat folgende Konsequenzen:

* Daten werden nicht mit dem generischen Abfrageeditor in der Konsole angezeigt.
* In Übersichts- und Datensatzlisten (Konsole) sind keine Daten sichtbar.
* Daten werden in der Detailansicht schreibgeschützt.
* Daten können nur innerhalb von Filtern verwendet werden (d. h. bei Verwendung einiger Dichotomie-Strategien können Sie dennoch Werte erraten).
* Jeder Ausdruck, der mithilfe eines eingeschränkten Felds erstellt wurde, ist auf Folgendes beschränkt: lower(@email) wird so barrierefrei wie @email.
* In einem Workflow können Sie die eingeschränkte Spalte zur Zielpopulation als zusätzliche Spalte der Transition hinzufügen, sie steht aber für Adobe Campaign-Benutzer weiterhin nicht zur Verfügung.
* Beim Speichern der Zielpopulation in einer Gruppe (Liste) entsprechen die Eigenschaften der gespeicherten Felder den Datenquellen.
* Daten sind für JS-Code standardmäßig nicht verfügbar.

## Empfehlungen       {#recommendations}

In jedem Versand werden E-Mail-Adressen in die Tabellen **[!UICONTROL broadLog]** und **[!UICONTROL forecastLog]** kopiert: Daher müssen auch diese Felder geschützt werden.

Nachfolgend finden Sie ein Beispiel für die Log-Tabellen-Erweiterung, um dies zu implementieren:

```
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:broadLogRcp" img="nms:broadLog.png"
           label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:broadLog.png" label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema desc="Delivery messages being prepared." entitySchema="xtk:srcSchema"
           extendedSchema="nms:tmpBroadcast" img="" label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Delivery messages being prepared." label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:excludeLogRcp" img="nms:excludeLog.png"
           label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:excludeLog.png" label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
```

>[!CAUTION]
>
>Diese Einschränkung gilt nur für nicht technische Benutzer und isoliert keine Daten: Ein technischer Benutzer mit entsprechenden Berechtigungen kann Daten abrufen.
