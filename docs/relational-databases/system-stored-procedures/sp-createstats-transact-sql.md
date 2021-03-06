---
title: Sp_createstats (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_createstats_TSQL
- sp_createstats
dev_langs:
- TSQL
helpviewer_keywords:
- sp_createstats
ms.assetid: 8204f6f2-5704-40a7-8d51-43fc832eeb54
caps.latest.revision: 47
author: edmacauley
ms.author: edmaca
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: 75e05e36dfea3a36fa01d08ca79b22c3abb7e2c4
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39555160"
---
# <a name="spcreatestats-transact-sql"></a>sp_createstats (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Ruft die [CREATE STATISTICS](../../t-sql/statements/create-statistics-transact-sql.md) einspaltige Statistiken für Spalten zu erstellen, die nicht bereits die erste Spalte in einem Statistikobjekt-Anweisung. Das Erstellen von Statistiken für einzelne Spalten erhöht die Anzahl von Histogrammen und kann zur Verbesserung von Kardinalitätsschätzungen, Abfrageplänen und Abfrageleistung führen. Die erste Spalte eines Statistikobjekts verfügt über ein Histogramm, während andere Spalten kein Histogramm enthalten.  
  
 sp_createstats ist für Anwendungen wie Vergleichstests hilfreich, wenn Abfrageausführungszeiten ein kritischer Faktor sind, und es zu lange dauert, bis der Abfrageoptimierer Statistiken für einzelne Spalten generiert hat. In den meisten Fällen ist es nicht erforderlich, Sp_createstats zu verwenden. der Abfrageoptimierer Statistiken für einzelne Spalten generiert, wie erforderlich, um die Abfrage zu verbessern. Abfragepläne bei der **AUTO_CREATE_STATISTICS** aktiviert ist.  
  
 Weitere Informationen zu Statistiken finden Sie unter [Statistik](../../relational-databases/statistics/statistics.md). Weitere Informationen zum Generieren von Statistiken für einzelne Spalten finden Sie unter den **AUTO_CREATE_STATISTICS** option [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql-set-options.md).  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sp_createstats   
    [   [ @indexonly =   ] { 'indexonly'   | 'NO' } ]   
    [ , [ @fullscan =    ] { 'fullscan'    | 'NO' } ]   
    [ , [ @norecompute = ] { 'norecompute' | 'NO' } ]  
    [ , [ @incremental = ] { 'incremental' | 'NO' } ]  
```  
  
## <a name="arguments"></a>Argumente  
 [  **@indexonly=** ] **"Indexonly"**  
 Erstellt Statistiken nur für Spalten, die sich in einem vorhandenen Index befinden und nicht der ersten Spalte in einer beliebigen Indexdefinition entsprechen. **Indexonly** ist **char(9)**. Der Standardwert ist NO.  
  
 [  **@fullscan=** ] **"Fullscan"**  
 Verwendet die [CREATE STATISTICS](../../t-sql/statements/create-statistics-transact-sql.md) -Anweisung mit der **Option "FULLSCAN"** Option. **Option "FULLSCAN"** ist **char(9)**.  Der Standardwert ist NO.  
  
 [  **@norecompute=** ] **"Norecompute"**  
 Verwendet die [CREATE STATISTICS](../../t-sql/statements/create-statistics-transact-sql.md) -Anweisung mit der **NORECOMPUTE** Option. **NoRecompute** ist **char(12)**.  Der Standardwert ist NO.  
  
 [  **@incremental=** ] **"inkrementell"**  
 Verwendet die [CREATE STATISTICS](../../t-sql/statements/create-statistics-transact-sql.md) -Anweisung mit der **inkrementell = ON** Option. **Inkrementelle** ist **char(12)**.  Der Standardwert ist NO.  
  
## <a name="return-code-values"></a>Rückgabecodewerte  
 0 (Erfolg) oder 1 (Fehler)  
  
## <a name="result-sets"></a>Resultsets  
 Jedes neue Statistikobjekt hat den gleichen Namen wie die Spalte, für die es erstellt wurde.  
  
## <a name="remarks"></a>Hinweise  
 Sp_createstats nicht erstellen oder Aktualisieren von Statistiken für Spalten, die der ersten Spalte in einem vorhandenen Statistikobjekt entsprechen;  Dies schließt die erste Spalte der Statistiken für Indizes, Spalten mit Statistiken für einzelne Spalten generiert, mit der AUTO_CREATE_STATISTICS-Option und die erste Spalte der Statistiken erstellt wurden, mit der CREATE STATISTICS-Anweisung erstellt wurden. Sp_createstats werden keine Statistiken für die ersten Spalten deaktivierter Indizes erstellt, es sei denn, diese Spalte in einem anderen aktivierten Index verwendet wird. Sp_createstats erstellt keine Statistiken für Tabellen mit einem deaktivierten gruppierten Index.  
  
 Wenn die Tabelle einen Spaltensatz enthält, werden mit sp_createstats keine Statistiken für Sparsespalten erstellt. Weitere Informationen über spaltensätze und sparsespalten finden Sie unter [Verwenden von Spaltensätzen](../../relational-databases/tables/use-column-sets.md) und [Verwenden von Sparsespalten](../../relational-databases/tables/use-sparse-columns.md).  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die Mitgliedschaft in der festen Datenbankrolle "db_owner".  
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-create-single-column-statistics-on-all-eligible-columns"></a>A. Erstellen von Statistiken für einzelne Spalten für alle geeigneten Spalten  
 Im folgenden Beispiel wird eine Statistik für einzelne Spalten für alle geeigneten Spalten in der aktuellen Datenbank erstellt.  
  
```  
EXEC sp_createstats;  
GO  
```  
  
### <a name="b-create-single-column-statistics-on-all-eligible-index-columns"></a>B. Erstellen von Statistiken für einzelne Spalten für alle geeigneten Indexspalten  
 Im folgenden Beispiel werden Statistiken für einzelne Spalten für alle geeigneten Spalten erstellt, die sich bereits in einem Index befinden und nicht der ersten Spalte im Index entsprechen.  
  
```  
EXEC sp_createstats 'indexonly';  
GO  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Statistiken](../../relational-databases/statistics/statistics.md)   
 [CREATE STATISTICS &#40;Transact-SQL&#41;](../../t-sql/statements/create-statistics-transact-sql.md)   
 [ALTER DATABASE SET-Optionen &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql-set-options.md)   
 [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-show-statistics-transact-sql.md)   
 [DROP STATISTICS &#40;Transact-SQL&#41;](../../t-sql/statements/drop-statistics-transact-sql.md)   
 [UPDATE STATISTICS &#40;Transact-SQL&#41;](../../t-sql/statements/update-statistics-transact-sql.md)   
 [Datenbank-Engine gespeicherten Prozeduren &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/database-engine-stored-procedures-transact-sql.md)   
 [Gespeicherte Systemprozeduren &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
