---
title: MSSQLSERVER_10507 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- 10507 (Database Engine error)
ms.assetid: cd83fa81-ac37-4eda-a3c3-17610b051de2
caps.latest.revision: 10
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 7614a550b0a7e60ac1d8d355fa68299aa8812e90
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37410129"
---
# <a name="mssqlserver10507"></a>MSSQLSERVER_10507
    
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|10507|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|PG_STMT_DOES_NOT_MATCH|  
|Meldungstext|Die Planhinweisliste kann nicht erstellt werden kann ' %. \*ls, da die Anweisung vom angegebenen `@stmt` und `@module_or_batch`, oder durch `@plan_handle` und `@statement_start_offset`, stimmt nicht mit einer beliebigen Anweisung in das angegebene Modul oder batch. Ändern Sie die Werte, um eine Übereinstimmung mit einer Anweisung im Modul oder Batch herzustellen.|  
  
## <a name="explanation"></a>Erklärung  
 Eine Anweisung im festgelegten Modul oder Batch konnte nicht der angegebenen Anweisung bzw. dem Offsetwert der Anweisung zugeordnet werden.  
  
## <a name="user-action"></a>Benutzeraktion  
 Ändern Sie die angegebenen Parameterwerte, um eine Übereinstimmung mit einer Anweisung im Modul oder Batch herzustellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Planhinweislisten](../performance/plan-guides.md)   
 [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql)   
 [sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
