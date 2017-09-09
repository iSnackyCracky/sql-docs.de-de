---
title: DBCC DROPCLEANBUFFERS (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/16/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DROPCLEANBUFFERS
- DBCC_DROPCLEANBUFFERS_TSQL
- DROPCLEANBUFFERS_TSQL
- DBCC DROPCLEANBUFFERS
dev_langs:
- TSQL
helpviewer_keywords:
- clean buffers
- cold buffer cache
- buffer pools [SQL Server]
- dropping buffers
- removing buffers
- DBCC DROPCLEANBUFFERS statement
ms.assetid: a4121927-f2ce-4926-aa2c-9b1519dac048
caps.latest.revision: 35
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: d1a7a1507e230995df1c2b67a8499a12270b535c
ms.contentlocale: de-de
ms.lasthandoff: 09/01/2017

---
# <a name="dbcc-dropcleanbuffers-transact-sql"></a>DBCC DROPCLEANBUFFERS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw_md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

Entfernt alle leeren Puffer aus dem Pufferpool und die columnstore-Objekte aus der columnstore-Objektpool an.
  
![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntax
Die Syntax für SQLServer: 

```sql
DBCC DROPCLEANBUFFERS [ WITH NO_INFOMSGS ]  
```  
Die Syntax für Azure SQL Datawarehouse und Parallel Datawarehouse:

```sql  
DBCC DROPCLEANBUFFERS ( COMPUTE | ALL ) [ WITH NO_INFOMSGS ]  
```  
  
## <a name="arguments"></a>Argumente  
 WITH NO_INFOMSGS  
 Alle Informationsmeldungen werden unterdrückt. Informationsmeldungen unterdrückt werden immer auf [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] und [!INCLUDE[ssPDW](../../includes/sspdw-md.md)].  
  
 COMPUTE  
 Löschen Sie von jeder Serverknoten Abfrageplancache befinden.  
  
 ALL  
 Löschen Sie auf jedem Knoten der COMPUTE- und aus dem Knoten "Zugriffssteuerung" Abfrageplancache befinden. Dies ist die Standardeinstellung, wenn Sie keinen Wert angeben.  
  
## <a name="remarks"></a>Hinweise  
Verwenden Sie DBCC DROPCLEANBUFFERS, um Abfragen mit einem frischen Puffercache zu testen, ohne den Server herunterzufahren und neu zu starten.
Um leere Puffer aus Buffer Pool und die columnstore-Objekte aus der columnstore-Objektpool löschen, zunächst mithilfe CHECKPOINT einen frischen Puffercache erzeugen. Dadurch wird erzwungen, dass alle modifizierten Seiten der aktuellen Datenbank auf den Datenträger geschrieben und die Puffer geleert werden. Anschließend können Sie durch Ausführen des DBCC DROPCLEANBUFFERS-Befehls alle Puffer aus dem Pufferpool entfernen.
  
## <a name="result-sets"></a>Resultsets  
DBCC DROPCLEANBUFFERS auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zurückgibt:
  
```sql
DBCC execution completed. If DBCC printed error messages, contact your system administrator.  
```  
  
## <a name="permissions"></a>Berechtigungen  

Gilt für: SQLServer, Parallel Datawarehouse 

- Erfordert die Mitgliedschaft in der festen Serverrolle **sysadmin** .  

Gilt für: Azure SQL Data Warehouse

- Erfordert die Mitgliedschaft in der festen Serverrolle "DB_OWNER".  
  
## <a name="see-also"></a>Siehe auch  
[DBCC &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md)  
[CHECKPOINT &#40;Transact-SQL&#41;](../../t-sql/language-elements/checkpoint-transact-sql.md)  
  
  
