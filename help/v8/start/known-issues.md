---
title: Bekannte Probleme in Campaign v8
description: Bekannte Probleme in der neuesten Campaign-Version
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: b9dd9e76be14067740426b6cddfa2c5fcddf3158
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Bekannte Probleme{#known-issues}

Diese Seite listet bekannte Probleme auf, die in den **letzten Campaign v8-Versionen** festgestellt wurden. Zusätzlich werden [auf dieser Seite](ac-guardrails.md) Einschränkungen von Campaign v8 aufgeführt.


>[!NOTE]
>
>Adobe veröffentlicht diese Liste bekannter Probleme nach eigenem Ermessen. Sie basiert auf der Anzahl der Kundenberichte, dem Schweregrad und der Verfügbarkeit einer Problemumgehung. Wenn ein Problem, auf das Sie stoßen, nicht aufgelistet ist, entspricht es möglicherweise nicht den Kriterien für die Veröffentlichung auf dieser Seite.

## Campaign v8.3.8{#8.3-issues}

### Problem mit der Aktivität &quot;Datenquelle ändern&quot; {#issue-2}

#### Beschreibung{#issue-2-desc}

Beim Einfügen von Daten in eine Snowflake Cloud-Datenbank mit einer Campaign-**Abfrage** und der Aktivität **Datenquelle ändern** schlägt der Prozess fehl, wenn in den Daten ein umgekehrter Schrägstrich vorhanden ist. Die Quellzeichenfolge wird nicht mit Escape-Zeichen versehen, wodurch die Daten auf Snowflake nicht korrekt verarbeitet werden.

Dieses Problem tritt nur auf, wenn sich der umgekehrte Schrägstrich am Ende der Zeichenfolge befindet, z. B.: `Barker\`.


#### Reproduktionsschritte{#issue-2-repro}

1. Stellen Sie eine Verbindung zur Client-Konsole her und erstellen Sie einen Workflow.
1. Fügen Sie eine **Abfrage**-Aktivität hinzu und konfigurieren Sie sie.
1. Wählen Sie Daten mit den oben beschriebenen Eigenschaften aus.
1. Fügen Sie die Aktivität **Datenquelle ändern** hinzu und konfigurieren Sie sie so, dass die Snowflake Cloud-Datenbank ausgewählt ist.
1. Führen Sie den Workflow aus und sehen Sie sich die Workflow-Protokolle an, um den Fehler zu finden.


#### Fehlernachricht{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### Problemumgehung{#issue-2-workaround}

Die Problemumgehung besteht darin, Daten auszuschließen, die umgekehrte Schrägstriche am Ende der Zeichenfolge enthalten, oder sie aus der Quelldatei zu entfernen.


#### Interner Verweis{#issue-2-ref}

Referenz: NEO-45549


### Eine Datei konnte nicht mit der Aktivität &quot;Laden (Datei)&quot; auf den Server hochgeladen werden {#issue-3}

#### Beschreibung{#issue-3-desc}

Beim Hochladen einer Datei auf den Campaign-Server mit der Aktivität **Laden (Datei)** hört der Vorgang bei 100 % auf, endet jedoch nie.

#### Reproduktionsschritte{#issue-3-repro}

1. Stellen Sie eine Verbindung zur Client-Konsole her und erstellen Sie einen Workflow.
1. Fügen Sie die Aktivität **Laden (Datei)** hinzu und konfigurieren Sie sie.
1. Wählen Sie die Option **Auf Server hochladen**.
1. Wählen Sie die Datei auf Ihrem lokalen Computer aus.
1. Klicken Sie auf **Hochladen**.


#### Fehlernachricht{#issue-3-error}

Der Prozess endet nie.

#### Problemumgehung{#issue-3-workaround}

Die Lösung besteht darin, eine ältere Client-Konsole zu verwenden. Damit können Sie die Datei auf den Server hochladen.

Als Campaign-Administrator können Sie die Client-Konsole für Campaign v8.3.1 in der [Adobe-Software-Verteilung](https://experience.adobe.com/#/downloads/content/software-distribution/de/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=target-version%3Acampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc&amp;layout=list&amp;p.offset=0&amp;p.limit=4){target=&quot;_blank&quot;} herunterladen.

Auf [dieser Seite](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=de){target=&quot;_blank&quot;} erfahren Sie, wie Sie auf die Adobe-Software-Verteilung zugreifen können.

Auf [dieser Seite](connect.md) erfahren Sie, wie Sie Ihre Client-Konsole aktualisieren.

#### Interner Verweis{#issue-3-ref}

Referenz: NEO-47269