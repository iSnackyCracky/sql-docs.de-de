---
title: Verwenden Sie einblickwidgets zum Überwachen von Servern und Datenbanken in SQL Operations Studio (Vorschau) | Microsoft-Dokumentation
description: Informationen Sie zu einblickwidgets in SQL Operations Studio (Vorschau).
ms.custom: tools|sos
ms.date: 11/15/2017
ms.prod: sql
ms.technology: ssops
ms.reviewer: alayu; sstein
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 79918d899fa978404dde63bf9257ffb9fc52d185
ms.sourcegitcommit: c8f7e9f05043ac10af8a742153e81ab81aa6a3c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2018
ms.locfileid: "39082852"
---
# <a name="manage-servers-and-databases-with-insight-widgets-in-includename-sosincludesname-sos-shortmd"></a>Verwalten von Servern und Datenbanken mit einblickwidgets in [!INCLUDE[name-sos](../includes/name-sos-short.md)]

Einblickwidgets nutzen, die Transact-SQL (T-SQL) Abfragen, die Sie zum Überwachen von Servern und-Datenbanken verwenden und wandelt sie in aussagekräftige Visualisierungen. 

Einblicke sind anpassbare Diagramme und Grafiken, die Server- und datenbanküberwachung Dashboards hinzugefügt. Zeigen Sie auf einen Blick Erkenntnisse von Ihren Servern und Datenbanken, und klicken Sie dann weitere Details anzuzeigen Sie, und starten Sie Verwaltungsaktionen, die Sie definieren. 

Sie können die awesome Server- und Management-Dashboards wie im folgenden Beispiel erstellen:

![Datenbank-dashboard](media/insight-widgets/database-dashboard.png)


Um Sie richtig einsteigen und verschiedene Arten von einblickwidgets erstellen, finden Sie in den folgenden Tutorials:

- [Erstellen eines benutzerdefinierten Einblicks-Widgets](tutorial-build-custom-insight-sql-server.md)
- *Aktivieren Sie integrierte einblickwidgets*
   - [Aktivieren der Einblicke für die Leistungsüberwachung](tutorial-qds-sql-server.md)
   - [Aktivieren Sie die Tabelle Speicherplatz Nutzung Einblicke](tutorial-table-space-sql-server.md)


## <a name="sql-queries"></a>SQL-Abfragen 

[!INCLUDE[name-sos](../includes/name-sos-short.md)] versucht, zu vermeiden, aber einer anderen Sprache oder hohem Benutzeroberfläche damit versucht wird, verwenden Sie T-SQL so weit wie möglich mit Minimalkonfiguration JSON. Konfigurieren von einblickwidgets mit T-SQL nutzt die zahllosen Anzahl der vorhandenen Quellen nützliche T-SQL-Abfragen, die in aussagekräftige Widgets umgewandelt werden können.

Einblickwidgets bestehen aus einem oder zwei T-SQL-Abfragen:
* *Insights-Widget-Abfrage* ist obligatorisch, und ist die Abfrage, die angezeigten Daten im daraufhin angezeigten Widget zurückgibt.
* *Insights-Details-Abfrage* ist nur erforderlich, wenn Sie eine Detailseite Insight erstellen.

Eine Insight-Widget-Abfrage definiert ein Dataset, das eine Anzahl, oder Diagramm gerendert wird. Insights-Details-Abfrage werden relevante Einblicke Detailinformationen in einem Tabellenformat in der Insight-Bereich "Details" aufgelistet. 

[!INCLUDE[name-sos](../includes/name-sos-short.md)] Insight-Widget-Abfragen ausgeführt, Resultset der Abfrage des Diagramms Dataset zugeordnet, und rendert ihn. Wenn Benutzer einen Einblick in die Details öffnen, führt die Abfrage der Insight-Details, und gibt das Ergebnis in einer Rasteransicht in das Dialogfeld.

Die grundlegende Idee ist, eine T-SQL-Abfrage auf eine Weise zu schreiben, damit es als ein Dataset mit einer Anzahl, Diagramm- und Graph-Widget verwendet werden kann. 

## <a name="summary"></a>Zusammenfassung

Bestimmen das Verhalten der Insight-Widgets, die T-SQL-Abfrage und Resultset. Das Schreiben einer Abfrage für ein Diagramm oder die Zuordnung eines richtigen Diagrammtyps für vorhandene Abfrage ist die wichtige Überlegung zum Erstellen einer effektiven Insight-Widget.



## <a name="additional-resources"></a>Weitere Ressourcen
- [Abfrage-Editor](tutorial-sql-editor.md)

