---
title: Nachverfolgen von personalisierten Links
description: Erfahren Sie, wie Sie personalisierte Links in E-Mails verfolgen
feature: Personalization
role: User
level: Beginner
exl-id: d0e00b40-e7dd-4484-b37c-fd3f3ac70fda
source-git-commit: 6e465ec24f72d0b30c4fc287da5d4c4bcaeda05b
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 50%

---

# Nachverfolgen von personalisierten Links {#tracking-personalized-links}

Die Links in E-Mail-Inhalten, die eine Personalisierung enthalten, benötigen eine bestimmte Syntax, um nachverfolgt zu werden.

Durch die Verwendung von JavaScript in E-Mail-Inhalten (HTML oder Text) können Sie dynamische Inhalte mit zwei Einschränkungen generieren und an die Empfänger senden:

* Das Script kann nicht direkt auf die Datenbank zugreifen (SQL-Funktion und API-Funktionen sind nicht verfügbar),
* Adobe Campaign muss in der Lage sein, URLs zu erkennen, damit Links verfolgt werden können.

## Anweisungen zur Vorab-Bearbeitung {#pre-processing-instructions}

Sie können spezifische Anweisungen zur Vorab-Bearbeitung hinzufügen, um die URL zu skripten und zu tracken. Diese Anweisungen müssen in JavaScript geschrieben sein und mit `<%@` beginnen.

Beispiel:

```
<%@ value object="myObject" xpath="@myField" %>
```

Diese Anweisung ruft den Wert des Felds `myField` aus dem `myObject` ab.

## URL-Erkennung {#url-detection}

Zur Tracking-Erkennung bettet Adobe Campaign [Tidy](https://www.html-tidy.org/) ein, um die HTML-Quelle zu analysieren und das Muster zu erkennen. Es werden alle URLs des Inhalts aufgelistet, damit sie einzeln verfolgt werden können. Adobe Campaign verwendet wiederum Tidy, um die URL (`http://myurl.com`) durch eine URL zu ersetzen, die auf den Weiterleitungs-Server von Adobe Campaign verweist.

Zum Beispiel wird im ursprünglichen Inhalt `http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>` für einen bestimmten Empfänger durch `http://emailing.customer.com/r/?id=h617791,71ffa3,71ffa8&p1=CustomerName` ersetzt. 

Wobei:

* &quot;h&quot; bedeutet HTML-Inhalt (oder &quot;t&quot; für Textinhalte).
* 617791 ist die Nachrichtenkennung/BroadLog-Kennung (hexadezimal).
* 71ffa3 ist die NmsDelivery-Kennung (hexadezimal).
* 71ffa8 ist die NmsTrackingUrl-Kennung (hexadezimal).
* p1, p2 usw. sind alle Parameter, die in der URL ersetzt werden sollen.

### Beispiel einer Nichterkennung {#non-detection-example}

`<%= getURL("http://mynewsletter.com") %>` funktioniert und sendet den eigentlichen Inhalt der Web-Seite per E-Mail an die Empfänger. Es wird jedoch keiner der Links verfolgt. Der Grund dafür ist, dass der MTA `"<%=getURL(..."` für jede E-Mail vor dem Senden ausführt. Dies kann für jeden Empfänger unterschiedlich sein, weswegen Adobe Campaign die zu verfolgenden URLs nicht kennt und ihnen eine Tag-ID zuweist.

Wenn die herunterzuladende Seite für alle Empfängerinnen und Empfänger identisch ist, empfiehlt es sich, Folgendes zu verwenden:

```
<%@ include url="http://mynewsletter.com" %>
```

In diesem Fall wird die Seite während der Analyse vor der Tracking-Erkennung heruntergeladen. Dadurch kann Adobe Campaign die Links ermitteln, eine Tag-ID zuweisen und sie verfolgen.

### Empfohlenes Muster {#recommended-pattern}

Nach der Verarbeitung `<%@` Anweisungen sollte die zu trackende URL die folgende Syntax aufweisen:

```
<a href="http://myurl.com/a.php?param1=aaa&param2=<%=escapeUrl(recipient.xxx)%>&param3=<%=escapeUrl(recipient.xxx)%>">
```

>[!IMPORTANT]
>
>Alle anderen Muster werden von Adobe nicht unterstützt und sollten vermieden werden, um potenzielle Sicherheitslücken zu verhindern.

## URL-Parameter {#url-parameters}

Um sicherzustellen, dass personalisierte URLs korrekt getrackt werden, müssen Sie die `escapeUrl()`-Funktion oder die entsprechende Kodierungsmethode für die Parameter in Ihren URLs verwenden.

**Beispiel:**

```
<a href="http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>">Click here</a>
```

Dadurch wird sichergestellt, dass der personalisierte Parameter von Adobe Campaign korrekt codiert und verfolgt wird.

## Looping mit `<%@ foreach %>` {#foreach}

Mit der `<%@ foreach %>` können Sie Arrays von Objekten durchlaufen, die im Versand geladen werden, um einzelne Links zu den Objekten zu verfolgen.

### Syntax

```
<%@ foreach object="myObject" xpath="myLink" index="3" item="myItem" %>
  <!-- Content to repeat -->
<%@ end %>
```

**Parameter:**

* **`object`**: Name des Objekts, von dem aus gestartet werden soll (normalerweise ein zusätzliches Scriptobjekt, es kann sich jedoch auch um einen Versand handeln)
* **`xpath`** (optional): XPath der Sammlung, die durchlaufen werden soll. Der Standardwert ist &quot;.“, was bedeutet, dass das Objekt das Array ist, in dem eine Schleife erzeugt werden soll
* **`index`** (optional): Wenn xpath nicht &quot;.“ ist und Objekt ist ein Array selbst, Elementindex des Objekts (beginnt bei 0)
* **`item`** (optional): Name eines neuen Objekts, auf das mit `<%@ value %>` innerhalb der foreach-Schleife zugegriffen werden kann. Standard ist der Name der Relation im Schema

### Beispiel

Laden Sie in den Versandeigenschaften/der Versandpersonalisierung ein Array von Artikeln und eine Beziehungstabelle zwischen Empfänger und Artikeln.

Sie können Links zu diesen Artikeln mit individuellem Tracking anzeigen:

```
<%@ foreach object="articleList" item="article" %>
  <a href="http://example.com/article.jsp?id=<%@ value object="article" xpath="@id" %>">
    <%@ value object="article" xpath="@title" %>
  </a>
<%@ end %>
```

Auf diese Weise kann Adobe Campaign verfolgen, auf welchen Artikel die einzelnen Empfänger geklickt haben, anstatt nur zu verfolgen, dass auf einen Artikellink geklickt wurde.

## Best Practices {#best-practices}

* Verwenden Sie immer die `escapeUrl()` für dynamische URL-Parameter
* Verwenden Sie `<%@ foreach %>`, wenn Sie einzelne Elemente in Sammlungen verfolgen müssen
* Testen des Trackings vor dem Versand, um sicherzustellen, dass alle Links ordnungsgemäß funktionieren
* Überprüfen, ob personalisierte Links im Versandinhalt korrekt formatiert sind
* Überprüfen Sie die Trackinglogs, um sicherzustellen, dass personalisierte Parameter korrekt erfasst werden

## Verwandte Themen {#related-topics}

* [Erfahren Sie, wie Sie verfolgte Links konfigurieren](tracked-links.md)
* [Erfahren Sie, wie Sie URL-Tracking-Optionen konfigurieren](url-tracking.md)
* [Erfahren Sie, wie Sie Personalisierungsfelder hinzufügen](personalization-fields.md)

