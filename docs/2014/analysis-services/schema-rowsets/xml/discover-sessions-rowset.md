---
title: DISCOVER_SESSIONS-Rowset | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- DISCOVER_SESSIONS rowset
ms.assetid: 47a79542-3142-4e62-a66f-6c4dbfe0f5c0
caps.latest.revision: 18
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 2b9c137aafe16ad999bba5213afaaf92c15e1c35
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37218110"
---
# <a name="discoversessions-rowset"></a>DISCOVER_SESSIONS-Rowset
  Stellt Informationen zur Ressourcenverwendung und Aktivität der zurzeit geöffneten Sitzungen auf dem Server bereit.  
  
## <a name="rowset-columns"></a>Rowsetspalten  
 Die `DISCOVER_SESSIONS` Rowset enthält die folgenden Spalten.  
  
|Spaltenname|Typindikator|Länge|Description|  
|-----------------|--------------------|------------|-----------------|  
|`SESSION_COMMAND_COUNT`|`DBTYPE_I4`||Die Anzahl der Befehle, deren Ausführung seit dem Beginn der Sitzung gestartet wurde.|  
|`SESSION_CONNECTION_ID`|`DBTYPE_I4`||Der Verbindungsbezeichner für die Sitzung.|  
|`SESSION_CPU_TIME_MS`|`DBTYPE_UI8`||Die CPU-Zeit in Millisekunden, die seit dem Beginn der Sitzung von allen Anforderungen beansprucht wurde.|  
|`SESSION_CURRENT_DATABASE`|`DBTYPE_WSTR`||Der Name der Datenbank, die von der aktuellen Befehlsausführung verwendet wurde, oder die Datenbank, die von dem zuletzt ausgeführten Befehl verwendet wurde.|  
|`SESSION_ELAPSED_TIME_MS`|`DBTYPE_UI8`||Seit dem Start der Sitzung verstrichene Zeit in Millisekunden.|  
|`SESSION_ID`|`DBTYPE_WSTR`||Die eindeutige Sitzungs-ID als GUID.|  
|`SESSION_IDLE_TIME_MS`|`DBTYPE_UI8`||Die Leerlaufzeit in Millisekunden seit dem Start der Sitzung.|  
|`SESSION_LAST_COMMAND`|`DBTYPE_WSTR`||Der Text des zurzeit ausgeführten Befehls oder der zuletzt ausgeführte Befehl.|  
|`SESSION_LAST_COMMAND_CPU_TIME_MS`|`DBTYPE_UI8`||Die von `SESSION_LAST_COMMAND` verwendete CPU-Zeit in Millisekunden.|  
|`SESSION_LAST_COMMAND_ELAPSED_TIME_MS`|`DBTYPE_UI8`||Die seit dem Start von `SESSION_LAST_COMMAND` verstrichene Zeit in Millisekunden.|  
|`SESSION_LAST_COMMAND_END_TIME`|`DBTYPE_DBTIMESTAMP`||Die UTC-Serverzeit zu dem Zeitpunkt, als die Ausführung des letzten Befehls beendet wurde.|  
|`SESSION_LAST_COMMAND_START_TIME`|`DBTYPE_DBTIMESTAMP`||Die UTC-Serverzeit zu dem Zeitpunkt, als die Ausführung des letzten Befehls gestartet wurde.|  
|`SESSION_PROPERTIES`|`DBTYPE_WSTR`||Zur künftigen Verwendung reserviert.|  
|`SESSION_READ_KB`|`DBTYPE_UI8`||Der akkumulierte Wert der seit dem Start der Sitzung vom Datenträger gelesenen Daten in KB.|  
|`SESSION_READS`|`DBTYPE_UI8`||Die akkumulierte Anzahl der seit dem Start der Sitzung erfolgten Lesevorgänge auf dem Datenträger.|  
|`SESSION_SPID`|`DBTYPE_I4`||Die Sitzungs-ID.|  
|`SESSION_START_TIME`|`DBTYPE_DBTIMESTAMP`||Das Datum und die Uhrzeit des Sitzungsstarts als UTC-Zeit für den Server.|  
|`SESSION_STATUS`|`DBTYPE_I4`||Der Aktivitätsstatus der Sitzung<br /><br /> 0 bedeutet "Leerlauf": Zurzeit keine Aktivität.<br /><br /> 1 bedeutet "Aktiv": Die Sitzung führt einige angeforderte Aufgaben aus.<br /><br /> 2 bedeutet "Blockiert": Die Sitzung wartet darauf, dass einige Ressourcen angehaltene Aufgaben fortsetzen.<br /><br /> 3 bedeutet "Abgebrochen": die Sitzung als abgebrochen markiert wurde.|  
|`SESSION_USED_MEMORY`|`DBTYPE_I4`||Die Größe des zurzeit von der Sitzung verwendeten Speichers in KB. Der gemeldete Wert ist die RAM-Verwendung nach SPID, ohne Unterscheidung zwischen verkleinerbarem und nicht verkleinerbarem Arbeitsspeicher. Im Gegensatz zu anderen DMVs, die Informationen zur Speicherauslastung zur Verfügung stellen, unterteilt DISCOVER_SESSIONS die Speicherauslastung nicht nach Kategorie.<br /><br /> Beachten Sie, dass SESSION_USED_MEMORY in der Regel zu wenige Informationen zur tatsächlichen Speicherauslastung bereitstellt, da von mehreren Sitzungen gemeinsam genutzte Objekte ausgeschlossen sind.  Nur die eindeutig zur Sitzung gehörigen Objekte werden in der Arbeitsspeicherberechnung dargestellt.|  
|`SESSION_USER_NAME`|`DBTYPE_WSTR`||Der Sitzungsbenutzername.|  
|`SESSION_WRITE_KB`|`DBTYPE_UI8`||Der akkumulierte Wert der seit dem Start der Sitzung auf den Datenträger geschriebenen Daten in KB.|  
|`SESSION_WRITES`|`DBTYPE_UI8`||Die akkumulierte Anzahl der seit dem Start der Sitzung erfolgten Schreibvorgänge auf dem Datenträger.|  
  
 Dieses Schemarowset ist nicht sortiert.  
  
## <a name="restriction-columns"></a>Einschränkungsspalten  
 Die `DISCOVER_SESSIONS` Rowset kann auf die in der folgenden Tabelle aufgeführten Spalten eingeschränkt werden.  
  
|Spaltenname|Typindikator|Einschränkungsstatus|  
|-----------------|--------------------|-----------------------|  
|SESSION_ID|DBTYPE_WSTR|Optional.|  
|SESSION_SPID|DBTYPE_I4|Optional.|  
|SESSION_CONNECTION_ID|DBTYPE_I4|Optional.|  
|SESSION_USER_NAME|DBTYPE_WSTR|Optional.|  
|SESSION_CURRENT_DATABASE|DBTYPE_WSTR|Optional.|  
|SESSION_ELAPSED_TIME_MS|DBTYPE_UI8|Optional.|  
|SESSION_CPU_TIME_MS|DBTYPE_UI8|Optional.|  
|SESSION_IDLE_TIME_MS|DBTYPE_UI8|Optional.|  
|SESSION_STATUS|DBTYPE_I4|Optional.|  
  
## <a name="see-also"></a>Siehe auch  
 [XML for Analysis – Schemarowsets](xml-for-analysis-schema-rowsets.md)  
  
  
