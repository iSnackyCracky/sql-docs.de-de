---
title: RAND (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: sql-data-warehouse, database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- RAND
- RAND_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- RAND function
- values [SQL Server], random float
- random float value
ms.assetid: 363c84d6-b9fa-49ba-9a75-e44f27535ff6
caps.latest.revision: 22
author: MashaMSFT
ms.author: mathoma
manager: craigg
monikerRange: =azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: 8e7217f3acbd09c6986a7c60e96db522fdacf0f4
ms.sourcegitcommit: e02c28b0b59531bb2e4f361d7f4950b21904fb74
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39452087"
---
# <a name="rand-transact-sql"></a>RAND (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-asdw-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-asdw-xxx-md.md)]

  Gibt einen **float**-Pseudozufallswert von ausschließlich 0 bis 1 zurück.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
RAND ( [ seed ] )  
```  
  
## <a name="arguments"></a>Argumente  
 *seed*  
 Ein ganzzahliger [Ausdruck](../../t-sql/language-elements/expressions-transact-sql.md) (**tinyint**, **smallint** oder **int**), der den Ausgangswert zurückgibt. Wenn *seed* nicht angegeben ist, weist [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] einen zufälligen Ausgangswert zu. Für einen bestimmten Ausgangswert ist das zurückgegebene Ergebnis immer gleich.  
  
## <a name="return-types"></a>Rückgabetypen  
 **float**  
  
## <a name="remarks"></a>Remarks  
 Bei wiederholten Aufrufen von RAND() mit demselben Ausgangswert werden dieselben Ergebnisse zurückgegeben.  
  
 Wenn für eine bestimmte Verbindung RAND() mit einem angegebenen Ausgangswert aufgerufen wird, führen alle nachfolgenden Aufrufe von RAND() zu Ergebnissen, die auf dem RAND()-Ausgangsaufruf basieren. Durch die folgende Abfrage wird z. B. immer dieselbe Nummernreihenfolge zurückgegeben.  
  
```  
SELECT RAND(100), RAND(), RAND()   
```  
  
## <a name="examples"></a>Beispiele  
 Das folgende Beispiel führt zu vier Zufallszahlen, die von der RAND-Funktion generiert werden.  
  
```  
DECLARE @counter smallint;  
SET @counter = 1;  
WHILE @counter < 5  
   BEGIN  
      SELECT RAND() Random_Number  
      SET @counter = @counter + 1  
   END;  
GO  
```  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Mathematische Funktionen &#40;Transact-SQL&#41;](../../t-sql/functions/mathematical-functions-transact-sql.md)  
  
  
