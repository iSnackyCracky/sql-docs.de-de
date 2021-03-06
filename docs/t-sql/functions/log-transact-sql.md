---
title: LOG (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/29/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- LOG
- LOG_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- float expressions
- logarithm of expression
- LOG function
ms.assetid: f7c39511-cd84-4362-93ba-0d93655217ee
caps.latest.revision: 42
author: MashaMSFT
ms.author: mathoma
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: 9723bc9e455f3593ad240d655dacae4e37686f0f
ms.sourcegitcommit: e02c28b0b59531bb2e4f361d7f4950b21904fb74
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39455624"
---
# <a name="log-transact-sql"></a>LOG (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Gibt den natürlichen Logarithmus des angegebenen **float**-Ausdrucks in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zurück.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
-- Syntax for SQL Server  
  
LOG ( float_expression [, base ] )  
```  
  
```  
-- Syntax for Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
LOG ( float_expression )  
```  
  
## <a name="arguments"></a>Argumente  
 *float_expression*  
 Ein [Ausdruck](../../t-sql/language-elements/expressions-transact-sql.md) vom Typ **float** oder von einem Typ, der implizit in **float** konvertiert werden kann.  
  
 *base*  
 Optionales ganzzahliges Argument, das die Basis des Logarithmus festlegt.  
  
**Gilt für** : [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] bis [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]
  
## <a name="return-types"></a>Rückgabetypen  
 **float**  
  
## <a name="remarks"></a>Remarks  
 Standardmäßig gibt **LOG()** den natürlichen Logarithmus zurück. Beginnend mit [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] können Sie die Basis des Logarithmus mithilfe des optionalen *base*-Parameters in einen anderen Wert ändern.  
  
 Der natürliche Logarithmus ist der Logarithmus zur Basis **e**, wobei **e** eine irrationale Konstante mit einem Wert von ungefähr 2,718281828 ist.  
  
 Der natürliche Logarithmus des exponentiellen Werts einer Zahl ist die Zahl selbst: LOG( EXP( *n* ) ) = *n*. Das Exponential des natürlichen Logarithmus einer Zahl ist die Zahl selbst: EXP( LOG( *n* ) ) = *n*.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-calculating-the-logarithm-for-a-number"></a>A. Berechnen des Logarithmus für eine Zahl.  
 Das folgende Beispiel berechnet den `LOG`-Wert für den angegebenen **float**-Ausdruck.  
  
```  
DECLARE @var float = 10;  
SELECT 'The LOG of the variable is: ' + CONVERT(varchar, LOG(@var));  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
-------------------------------------  
The LOG of the variable is: 2.30259  
  
(1 row(s) affected)  
```  
  
### <a name="b-calculating-the-logarithm-of-the-exponent-of-a-number"></a>B. Berechnen des Logarithmus des Exponenten einer Zahl.  
 Das folgende Beispiel berechnet den `LOG`-Wert für den Exponenten einer Zahl.  
  
```  
SELECT LOG (EXP (10));  
  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
----------------------------------  
10  
(1 row(s) affected)  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Beispiele: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] und [!INCLUDE[ssPDW](../../includes/sspdw-md.md)].  
  
### <a name="c-calculating-the-logarithm-for-a-number"></a>C. Berechnen des Logarithmus für eine Zahl  
 Das folgende Beispiel berechnet den `LOG`-Wert für den angegebenen **float**-Ausdruck.  
  
```  
SELECT LOG(10);  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```
 ----------------`  
  
 2.30
 ```  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Mathematische Funktionen &#40;Transact-SQL&#41;](../../t-sql/functions/mathematical-functions-transact-sql.md)   
 [EXP &#40;Transact-SQL&#41;](../../t-sql/functions/exp-transact-sql.md)   
 [LOG10 &#40;Transact-SQL&#41;](../../t-sql/functions/log10-transact-sql.md)  
  
  

