---
title: Sys. partition_parameters (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- partition_parameters_TSQL
- partition_parameters
- sys.partition_parameters_TSQL
- sys.partition_parameters
dev_langs:
- TSQL
helpviewer_keywords:
- sys.partition_parameters catalog view
ms.assetid: 2012ed9d-3ea3-4c29-9b78-dfa54a392dce
caps.latest.revision: 23
author: edmacauley
ms.author: edmaca
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: 4444a2595ab083cc5d270057e5d9f7b0f8d68188
ms.sourcegitcommit: b70b99c2e412b4d697021f3bf1a92046aafcbe37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2018
ms.locfileid: "40394032"
---
# <a name="syspartitionparameters-transact-sql"></a>sys.partition_parameters (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Enthält eine Zeile für jeden Parameter einer Partitionsfunktion.  
  
|Spaltenname|Datentyp|Description|  
|-----------------|---------------|-----------------|  
|**function_id**|**int**|ID der Partitionsfunktion, zu der dieser Parameter gehört|  
|**parameter_id**|**int**|ID des Parameters. Ist innerhalb der Partitionsfunktion eindeutig und beginnt mit 1.|  
|**system_type_id**|**tinyint**|ID des Systemtyps des Parameters. Entspricht der Spalte **system_type_id** der Katalogsicht **sys.types** .|  
|**max_length**|**smallint**|Die maximale Länge des Parameters in Byte.|  
|**Mit einfacher Genauigkeit**|**tinyint**|Genauigkeit des Parameters, wenn dieser numerisch ist. Andernfalls ist der Wert 0.|  
|**Skalieren**|**tinyint**|Dezimalstellen des Parameters, wenn dieser numerisch ist. Andernfalls ist der Wert 0.|  
|**collation_name**|**sysname**|Name der Sortierung des Parameters, wenn dieser auf Zeichen basiert. Andernfalls ist der Wert NULL.|  
|**user_type_id**|**int**|Die ID des Typs. Ist in der Datenbank eindeutig. Für Systemdatentypen gilt **user_type_id** = **system_type_id**.|  
  
## <a name="permissions"></a>Berechtigungen  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Weitere Informationen finden Sie unter [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Partitionieren von Katalogsichten &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/partition-function-catalog-views-transact-sql.md)   
 [Katalogsichten &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [sys.partition_functions &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-partition-functions-transact-sql.md)   
 [Sys. partition_range_values &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-partition-range-values-transact-sql.md)  
  
  
