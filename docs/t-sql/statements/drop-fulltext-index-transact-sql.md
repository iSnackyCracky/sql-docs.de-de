---
title: DROP FULLTEXT INDEX (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- DROP_FULLTEXT_INDEX_TSQL
- DROP FULLTEXT INDEX
dev_langs:
- TSQL
helpviewer_keywords:
- deleting full-text indexes
- removing full-text indexes
- full-text indexes [SQL Server], removing
- DROP FULLTEXT INDEX statement
- dropping full-text indexes
ms.assetid: 7443a4ab-1d43-4a22-bbba-a07f620892cb
caps.latest.revision: 33
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: cb5ff7ff811ad7e05d6f8fdc1e54ca6423d7622a
ms.sourcegitcommit: 05e18a1e80e61d9ffe28b14fb070728b67b98c7d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/04/2018
ms.locfileid: "37782911"
---
# <a name="drop-fulltext-index-transact-sql"></a>DROP FULLTEXT INDEX (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Entfernt einen Volltextindex aus einer angegebenen Tabelle oder einer indizierten Sicht.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
DROP FULLTEXT INDEX ON table_name  
```  
  
## <a name="arguments"></a>Argumente  
 *table_name*  
 Der Name der Tabelle oder indizierten Sicht, die den zu entfernenden Volltextindex enthält.  
  
## <a name="remarks"></a>Remarks  
 Es ist nicht nötig, alle Spalten aus dem Volltextindex zu löschen, bevor Sie den DROP FULLTEXT INDEX-Befehl verwenden.  
  
## <a name="permissions"></a>Berechtigungen  
 Der Benutzer muss über die ALTER-Berechtigung für die Tabelle oder die indizierte Sicht verfügen oder ein Mitglied der festen Serverrolle **sysadmin** oder der festen Datenbankrollen **db_owner** oder **db_ddladmin** sein.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird der in der `JobCandidate`-Tabelle enthaltene Volltextindex gelöscht.  
  
```  
USE AdventureWorks2012;  
GO  
DROP FULLTEXT INDEX ON HumanResources.JobCandidate;  
GO  
```  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [sys.fulltext_indexes &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql.md)   
 [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/alter-fulltext-index-transact-sql.md)   
 [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/create-fulltext-index-transact-sql.md)   
 [Volltextsuche](../../relational-databases/search/full-text-search.md)  
  
  
