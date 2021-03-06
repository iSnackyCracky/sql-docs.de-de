---
title: MSrepl_commands (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-tables
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- MSrepl_commands
- MSrepl_commands_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSrepl_commands system table
ms.assetid: 53b9f9cd-9429-47a0-aba2-908fc60e7036
caps.latest.revision: 24
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 7eec90fb29378f4cea3530093f2b505b87593fd8
ms.sourcegitcommit: a431ca21eac82117492d7b84c398ddb3fced53cc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2018
ms.locfileid: "39102398"
---
# <a name="msreplcommands-transact-sql"></a>MSrepl_commands (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Die **MSrepl_commands** -Tabelle enthält Zeilen mit replizierten Befehlen. Diese Tabelle wird in der Verteilungsdatenbank gespeichert.  
  
|Spaltenname|Datentyp|Description|  
|-----------------|---------------|-----------------|  
|**publisher_database_id**|**int**|Die ID der Verlegerdatenbank.|  
|**xact_seqno**|**varbinary(16)**|Die Transaktionssequenznummer.|  
|**type**|**int**|Der Befehlstyp.|  
|**article_id**|**int**|Die ID des Artikels.|  
|**originator_id**|**int**|Die ID des Urhebers.|  
|**command_id**|**int**|Die Befehls-ID.|  
|**verbleiben**|**bit**|Gibt an, ob es sich um einen Teilbefehl handelt.|  
|**Befehl**|**varbinary(1024)**|Der Befehlswert.|  
|**Hashkey**|**int**|Intern-nur zur Verwendung.|  
|**originator_lsn**|**varbinary(16)**|Identifiziert die LSN des Befehls in der Ausgangsveröffentlichung. Wird in der Peer-zu-Peer-Transaktionsreplikation verwendet.|  
  
## <a name="see-also"></a>Siehe auch  
 [Replikationstabellen &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Replikationssichten &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)   
 [Sp_replcmds &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-replcmds-transact-sql.md)  
  
  
