---
title: DISCOVER_COMMAND_OBJECTS-Rowset | Microsoft Docs
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: schema-rowsets
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: a580be3c487416c6f5c710553f2e4a4d9869e206
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
ms.locfileid: "34030331"
---
# <a name="discovercommandobjects-rowset"></a>DISCOVER_COMMAND_OBJECTS-Rowset
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Stellt Ressourcenverwendungs- und Aktivitätsinformationen über die Objekte bereit, die durch den Befehl, auf den verwiesen wird, verwendet werden.  
  
 **Gilt für:** tabellarische und mehrdimensionale Modelle  
  
## <a name="rowset-columns"></a>Rowsetspalten  
 Das **DISCOVER_COMMAND_OBJECTS** -Rowset enthält die folgenden Spalten.  
  
|Spaltenname|Typindikator|Einschränkung|Description|  
|-----------------|--------------------|-----------------|-----------------|  
|**SESSION_SPID**|**DBTYPE_I4**|ja|Die Sitzungs-ID.|  
|**SESSION_ID**|**DBTYPE_WSTR**|ja|Die eindeutige Sitzungs-ID als GUID.|  
|**SESSION_COMMAND_COUNT**|**DBTYPE_I4**||Die Sequenznummer des Befehls.|  
|**OBJECT_PARENT_PATH**|**DBTYPE_WSTR**|ja|Der Pfad zu dem übergeordneten Element des aktuellen Objekts.|  
|**OBJECT_ID**|**DBTYPE_WSTR**|ja|Die ID des Objekts, die bei dessen Erstellung definiert wurde.|  
|**OBJECT_VERSION**|**DBTYPE_I4**||Die Metadatenversionsnummer des Objekts, diese Nummer ändert sich jedes Mal, wenn das Objekt geändert wird.|  
|**OBJECT_DATA_VERSION**|**DBTYPE_I4**||Die Herkunftszahl der Daten in dem Objekt. Diese Zahl erhöht sich jedes Mal, wenn das Objekt verarbeitet wird.|  
|**OBJECT_CPU_TIME_MS**|**DBTYPE_I8**||Die CPU-Zeit in Millisekunden, die seit dem Start des Befehls vom Objekt beansprucht wurde.|  
|**OBJECT_READ_KB**|**DBTYPE_I8**||Der akkumulierte Wert der seit dem Start des Befehls von dem Objekt gelesenen Daten in KB.|  
|**OBJECT_READS**|**DBTYPE_I8**||Die akkumulierte Zahl der seit dem Start des Befehls von dem Objekt ausgeführten Lesevorgänge.|  
|**OBJECT_WRITE_KB**|**DBTYPE_I8**||Der akkumulierte Wert der seit dem Start des Befehls von dem Objekt geschriebenen Daten in KB.|  
|**OBJECT_WRITES**|**DBTYPE_I8**||Die akkumulierte Zahl der seit dem Start des Befehls von dem Objekt ausgeführten Schreibvorgänge.|  
|**OBJECT_ROWS_RETURNED**|**DBTYPE_I8**||Die Anzahl der seit dem Start des Befehls von dem Objekt an den Aufrufer zurückgegebenen Zeilen.|  
|**OBJECT_ROWS_SCANNED**|**DBTYPE_I8**||Die Anzahl der seit dem Start des Befehls von dem Objekt gescannten Zeilen.|  
  
 Dieses Schemarowset ist nicht sortiert.  
  
> [!IMPORTANT]  
>  Das DISCOVER_COMMAND_OBJECTS-Schemarowset meldet keine Aktivitäten durch DMV-Abfragen.  
  
## <a name="using-adomdnet-to-return-the-rowset"></a>Verwenden von ADOMD.NET zum Zurückgeben des Rowsets  
 Wenn Sie Metadaten mithilfe von ADOMD.NET und des Schemarowsets abrufen, können Sie entweder die GUID verwenden oder eine Referenz für ein Schemarowsetobjekt in der GetSchemaDataSet-Methode herstellen. Weitere Informationen finden Sie unter [Working with Schema Rowsets in ADOMD.NET](../../../analysis-services/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets.md).  
  
 Die folgende Tabelle enthält die GUID und die Zeichenfolgenwerte, die dieses Rowset identifizieren.  
  
|Argument|Wert|  
|--------------|-----------|  
|GUID|a07ccd44-8148-11d0-87bb-00c04fc33942|  
|ADOMDNAME|CommandObjects|  
  
## <a name="see-also"></a>Siehe auch  
 [XML for Analysis-Schemarowsets](../../../analysis-services/schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
  
