---
title: dm_clr_tasks (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.dm_clr_tasks
- sys.dm_clr_tasks_TSQL
- dm_clr_tasks
- dm_clr_tasks_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_clr_tasks dynamic management view
ms.assetid: 462b9061-09fa-4858-9707-03d6cc19c769
caps.latest.revision: 21
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: 89395a39dbe163c095ac98db6777be30e574918f
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39550730"
---
# <a name="sysdmclrtasks-transact-sql"></a>sys.dm_clr_tasks (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Gibt eine Zeile für alle CLR-Tasks (Common Language Runtime) zurück, die zurzeit ausgeführt werden. Ein [!INCLUDE[tsql](../../includes/tsql-md.md)] Batch, einen Verweis auf eine CLR-Routine enthält, erstellt einen separaten Task für die Ausführung des gesamten verwalteten Codes, in diesem Batch. Mehrere Anweisungen im Batch, die die Ausführung von verwaltetem Code benötigen, verwenden denselben CLR-Task. Der CLR-Task ist verantwortlich für die Verwaltung von Objekten und Status bezieht sich auf die Ausführung von verwaltetem Code als auch die Übergänge zwischen der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und der common Language Runtime.  
  
|Spaltenname|Datentyp|Description|  
|-----------------|---------------|-----------------|  
|**task_address**|**varbinary(8)**|Adresse des CLR-Tasks.|  
|**sos_task_address**|**varbinary(8)**|Adresse des zugrunde liegenden [!INCLUDE[tsql](../../includes/tsql-md.md)] Batch-Task.|  
|**appdomain_address**|**varbinary(8)**|Adresse der Anwendungsdomäne, in der dieser Task ausgeführt wird.|  
|**state**|**nvarchar(128)**|Aktueller Status des Tasks.|  
|**abort_state**|**nvarchar(128)**|Status, in dem sich der Abbruch zurzeit befindet (falls der Task abgebrochen wurde). Beim Abbrechen eines Tasks durchläuft dieser einen Status nach dem anderen.|  
|**type**|**nvarchar(128)**|Tasktyp.|  
|**affinity_count**|**int**|Affinität des Tasks.|  
|**forced_yield_count**|**int**|Häufigkeit, mit der der Task gezwungen war, seine Position freizugeben.|  
  
## <a name="permissions"></a>Berechtigungen  

Auf [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)], erfordert `VIEW SERVER STATE` Berechtigung.   
Auf [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)], erfordert die `VIEW DATABASE STATE` Berechtigung in der Datenbank.   
  
## <a name="see-also"></a>Siehe auch  
 [Dynamische Verwaltungssichten und -funktionen &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Dynamische Verwaltungssichten in Verbindung mit Common Language Runtime &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/common-language-runtime-related-dynamic-management-views-transact-sql.md)  
  
  

