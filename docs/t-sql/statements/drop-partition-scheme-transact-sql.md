---
title: DROP PARTITION SCHEME (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- DROP PARTITION SCHEME
- DROP_PARTITION_SCHEME_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- DROP PARTITION SCHEME statement
- deleting partition schemes
- dropping partition schemes
- removing partition schemes
- partition schemes [SQL Server], removing
ms.assetid: 6efbc87c-1c92-4e43-96a7-e0f30f1db185
caps.latest.revision: 17
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 2a0d5add7ab611df190b2201c228c71acfc5e665
ms.sourcegitcommit: 05e18a1e80e61d9ffe28b14fb070728b67b98c7d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/04/2018
ms.locfileid: "37789971"
---
# <a name="drop-partition-scheme-transact-sql"></a>DROP PARTITION SCHEME (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Entfernt ein Partitionsschema aus der aktuellen Datenbank. Partitionsschemas werden mit [CREATE PARTITION SCHEME](../../t-sql/statements/create-partition-scheme-transact-sql.md) erstellt und mit [ALTER PARTITION SCHEME](../../t-sql/statements/alter-partition-scheme-transact-sql.md) geändert.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
DROP PARTITION SCHEME partition_scheme_name [ ; ]  
```  
  
## <a name="arguments"></a>Argumente  
 *partition_scheme_name*  
 Der Name des zu löschenden Partitionsschemas.  
  
## <a name="remarks"></a>Remarks  
 Ein Partitionsschema kann nur gelöscht werden, wenn das Partitionsschema zurzeit nicht von Tabellen oder Indizes verwendet wird. Falls Tabellen oder Indizes das Partitionsschema verwenden, gibt DROP PARTITION SCHEME einen Fehler zurück. Die Dateigruppen selbst werden mit DROP PARTITION SCHEME nicht entfernt.  
  
## <a name="permissions"></a>Berechtigungen  
 Die folgenden Berechtigungen können für DROP PARTITION SCHEME verwendet werden:  
  
-   ALTER ANY DATASPACE-Berechtigung. Diese Berechtigung gilt standardmäßig für Mitglieder der festen Serverrolle **sysadmin** und für Mitglieder der festen Datenbankrollen **db_owner** und **db_ddladmin** .  
  
-   CONTROL- oder ALTER-Berechtigung für die Datenbank, in der das Partitionsschema erstellt wurde.  
  
-   Die CONTROL SERVER-Berechtigung oder ALTER ANY DATABASE-Berechtigung auf dem Server der Datenbank, in der das Partitionsschema erstellt wurde.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird das `myRangePS1`-Partitionsschema aus der aktuellen Datenbank gelöscht:  
  
```  
DROP PARTITION SCHEME myRangePS1;  
```  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [CREATE PARTITION SCHEME &#40;Transact-SQL&#41;](../../t-sql/statements/create-partition-scheme-transact-sql.md)   
 [ALTER PARTITION SCHEME &#40;Transact-SQL&#41;](../../t-sql/statements/alter-partition-scheme-transact-sql.md)   
 [sys.partition_schemes &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-partition-schemes-transact-sql.md)   
 [EVENTDATA &#40;Transact-SQL&#41;](../../t-sql/functions/eventdata-transact-sql.md)   
 [sys.data_spaces &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-data-spaces-transact-sql.md)   
 [sys.destination_data_spaces &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-destination-data-spaces-transact-sql.md)   
 [sys.partitions &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-partitions-transact-sql.md)   
 [sys.tables &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-tables-transact-sql.md)   
 [sys.indexes &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-indexes-transact-sql.md)   
 [sys.index_columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-index-columns-transact-sql.md)  
  
  
