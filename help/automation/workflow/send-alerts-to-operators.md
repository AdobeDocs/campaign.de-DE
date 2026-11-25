---
product: campaign
title: Senden personalisierter Warnungen an Benutzer
description: Erfahren Sie, wie Sie personalisierte Warnungen an Benutzer senden
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 41a009f6-d1e9-40c9-8494-3bbb4bd3d134
TQID: 'https://experienceleague.adobe.com/dNaZR5YIugp9CIju-jKPHqztQu75IurMvxJtbTILOTY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 75%
---
# Senden personalisierter Warnungen an Benutzer{#sending-personalized-alerts-to-operators}



In diesem Beispiel möchten wir einem Benutzer eine Warnung senden, die den Namen der Profile enthält, die einen Newsletter geöffnet, aber nicht auf den darin enthaltenen Link geklickt haben.

Die Felder für Vor- und Nachname der Profile sind mit der Zielgruppendimension **[!UICONTROL Empfänger]** verknüpft, während die Aktivität **[!UICONTROL Warnung]** mit der Zielgruppendimension **[!UICONTROL Operator]** verknüpft ist. Deshalb ist bei den beiden Zielgruppendimensionen kein Feld verfügbar, um eine Abstimmung vorzunehmen, die Felder für Vor- und Nachname abzurufen und in der Warnungsaktivität anzuzeigen.

Deshalb muss der folgende Workflow erstellt werden:

1. Wählen Sie mit der Aktivität **[!UICONTROL Abfrage]** die gewünschten Daten aus.
1. Fügen Sie die Aktivität **[!UICONTROL JavaScript-Code]** in den Workflow ein, um die Population aus der Abfrage in der Instanzvariablen zu speichern.
1. Verwenden Sie die Aktivität **[!UICONTROL Test]**, um die Populationsgröße festzustellen.
1. Verwenden Sie die Aktivität **[!UICONTROL Warnung]**, um je nach Ergebnis der **[!UICONTROL Test]**-Aktivität eine Warnung an einen Benutzer zu senden.

![Workflow mit einer Abfrage-, JavaScript-Code- und Testaktivität; die Verzweigung „True“ führt zu einer Warnungsaktivität, „False“ bis Ende 2.](assets/uc_operator_1.png)

## Die Population in der Instanzvariablen speichern {#saving-the-population-to-the-instance-variable}

Fügen Sie den unten stehenden Code zur Aktivität **[!UICONTROL JavaScript-Code]** hinzu.

```
var query = xtk.queryDef.create(  
    <queryDef schema="temp:query" operation="select">  
      <select>  
       <node expr="[target/recipient.@firstName]"/>  
       <node expr="[target/recipient.@lastName]"/>  
      </select>  
     </queryDef>  
  );  
  var items = query.ExecuteQuery();
```

Achten Sie darauf, dass der JavaScript-Code mit Ihren Workflow-Informationen übereinstimmt.

* Das Tag **[!UICONTROL queryDef schema]** sollte mit dem Namen der in der Abfrageaktivität verwendeten Zielgruppendimension übereinstimmen.
* Das Tag **[!UICONTROL node expr]** sollte mit dem Namen der Felder übereinstimmen, die Sie abrufen möchten.

![JavaScript-Code-Skript mit Hervorhebung des :query-Schemas „queryDef“ und der Zielknoten „firstName“ und „lastName“.](assets/uc_operator_3.png)

Um diese Informationen abzurufen, gehen Sie wie folgt vor:

1. Klicken Sie in der Aktivität **[!UICONTROL Abfrage]** mit der rechten Maustaste auf die ausgehende Transition und wählen Sie dann **[!UICONTROL Zielgruppe anzeigen...]**.

   ![Rechtsklick-Menü in der ausgehenden Transition der Abfrage -Aktivität mit ausgewählter Zielgruppe anzeigen.](assets/uc_operator_4.png)

1. Klicken Sie mit der rechten Maustaste auf die Liste und wählen Sie dann **[!UICONTROL Liste konfigurieren]** aus.

   ![Einträge der Zielliste, die im Kontextmenü geöffnet und die Option Liste konfigurieren ausgewählt sind.](assets/uc_operator_5.png)

1. Die Zielgruppendimension der Abfrage und die Feldnamen werden in der Liste angezeigt.

   ![Registerkarte „Listenspalten konfigurieren“ mit hervorgehobenem :query-Element und Feldern der Zielgruppendimension.](assets/uc_operator_6.png)

## Populationsgröße überprüfen {#testing-the-population-count}

Fügen Sie den unten stehenden Code in die **[!UICONTROL Test]**-Aktivität ein, um zu überprüfen, ob die ausgewählte Population zumindest 1 Profil enthält.

```
var.recCount>0
```

![Testen Sie die Aktivität mit einer bedingten Verzweigung „True“ mithilfe der Bedingung vars.recCount>0 und der Standardverzweigung „False“.](assets/uc_operator_7.png)

## Warnung einrichten {#setting-up-the-alert}

Nachdem die Population zur Instanzvariablen mit den gewünschten Feldern hinzugefügt wurde, können Sie jetzt diese Informationen zur Aktivität **[!UICONTROL Warnung]** hinzufügen.

Fügen Sie zu diesem Zweck den unten stehenden Code in das Tab **[!UICONTROL Quelle]** ein:

```
<ul>
<%
var items = new XML(instance.vars.items)
for each (var item in items){
%>
<li><%= item.target.@firstName %> <%= item.target.@lastName %></li>
<%
} %></ul>
```

>[!NOTE]
>
>Mit dem Befehl **[!UICONTROL &lt;%= item.target.recipient.@fieldName %>]** können Sie eines der Felder hinzufügen, die mit der Aktivität **[!UICONTROL JavaScript-Code]** in der Instanzvariablen gespeichert wurden.\
>Sie können beliebig viele Felder hinzufügen, vorausgesetzt diese wurden in den JavaScript-Code eingefügt.

![Warnaktivität, die einem Benutzer zugewiesen ist, mit einer Meldung, die gespeicherte Elemente in einer Schleife durchläuft, um Vor- und Nachnamen aufzulisten.](assets/uc_operator_8.png)
