---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 1%
---
# LinkEdit

Steuerelement zum Bearbeiten von Links.

![LinkEdit-Steuerelement](assets/linkedit.7cb7bf14.png)

## Eigenschaften

**backColor - Zeichenfolge** Hintergrundfarbe (btnshadow, weiß).

**border - string** Ändert den Stil des Kontrollentwurfs (solid, double, inset, outset, none).

**choiceButton - boolean** Blendet die Auswahlschaltfläche aus oder ein (standardmäßig ausgeblendet).

**computeStringExpr - Zeichenfolge** Berechneter Feldausdruck.

**computetstringKey - Zeichenfolge** Aktualisiert die berechnete Zeichenfolge und nicht den Fremdschlüssel.

**computeStringAlias - Zeichenfolge** Alias für berechnete Zeichenfolge.

**createMode - Zeichenfolge** Erstellt die Relation, wenn sie nicht vorhanden ist (keine, inline), mit dem standardmäßigen Bearbeitungsmodus.

**externalKey - boolean** Verwendet den externen Schlüssel.

**font-size - integer** Ändert die Schriftgröße.

**form - Zeichenfolge** Erzwingt die Link-Bearbeitung.

**label - Zeichenfolge** Zugeordnete Bezeichnung.

**loadEntityOnChange - Boolescher Wert** Lädt die Entität neu, wenn sich die Relation ändert.

**mandatory - boolean** leert leere Werte ab.

**noAutoComplete - Boolescher Wert** Deaktiviert den automatischen Vervollständigungsmodus.

**noEdition - Boolesch** Die Relation kann nicht geändert werden.

**nolabel - Boolesch** Blendet die zugehörige Beschriftung aus.

**notifyPathList - Zeichenfolge** Liste der XPaths, die von den verknüpften Elementen durch Kommas getrennt sind und im Kontext geladen werden sollen.

**noTransaction - boolean** Deaktiviert den Transaktionsmodus.

**noZoom - Boolescher Wert** Kein Link-Bearbeitungsformular.

**orderBy - Element** Planung von Auswahlmöglichkeiten.

**readOnly - boolean** Erzwingt, dass das Steuerelement schreibgeschützt ist.

**erforderlich - boolesch** Das Feld ist obligatorisch.

**schema - Zeichenfolge** Schema der Relation.

**serialize - boolean** Speichert die letzte Auswahl in der Benutzerkonfiguration.

**sysFilter - Element** Einschränkung der Auswahl.

**xpathMandatory - Zeichenfolge** Pfad zu einer booleschen Eigenschaft, die angibt, ob die Relation leer sein kann oder nicht.

## Bemerkungen

Beispiele:

```xml
<input xpath="operator">
  <sysFilter>
    <condition expr="@type= 1/>
  </sysFilter>
  <orderBy>
    <node expr="@name"/>
  </orderBy>
</input>

<input xpath="/tmp/recipient" type="linkEdit" label="Recipient"
       schema="nms:recipient">
```
