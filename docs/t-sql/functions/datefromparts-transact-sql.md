---
title: DATEFROMPARTS (Transact-SQL) | Microsoft-Dokumentation
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
- DATEFROMPARTS_TSQL
- DATEFROMPARTS
dev_langs:
- TSQL
helpviewer_keywords:
- DATEFROMPARTS function
ms.assetid: 5b885376-87aa-41f1-9e18-04987aead250
caps.latest.revision: 16
author: MashaMSFT
ms.author: mathoma
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: 0ab4606f5c82a7b94aebb055a3dbd8baf80a9c60
ms.sourcegitcommit: e02c28b0b59531bb2e4f361d7f4950b21904fb74
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39454254"
---
# <a name="datefromparts-transact-sql"></a>DATEFROMPARTS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-all-md](../../includes/tsql-appliesto-ss2012-all-md.md)]

Diese Funktion gibt einen **date**-Wert zurück, der den angegebenen Jahres-, Monats- und Tageswerten zugeordnet wird.
  
![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntax  
  
```sql
DATEFROMPARTS ( year, month, day )  
```  
  
## <a name="arguments"></a>Argumente  
*year*  
Ein ganzzahliger Ausdruck, der ein Jahr angibt.
  
*month*  
Ein ganzzahliger Ausdruck, der einen Monat angibt (von 1 bis 12).
  
*day*  
Ein ganzzahliger Ausdruck, der einen Tag angibt.
  
## <a name="return-types"></a>Rückgabetypen
**Datum**
  
## <a name="remarks"></a>Remarks  
`DATEFROMPARTS` gibt einen **date**-Wert zurück, bei dem die Datumskomponente auf das angegebene Jahr, den Monat und den Tag und die Uhrzeitkomponente auf den Standardwert festgelegt sind. Bei ungültigen Argumenten löst `DATEFROMPARTS` einen Fehler aus. `DATEFROMPARTS` gibt NULL zurück, wenn mindestens ein erforderliches Argument den Wert NULL enthält.
  
Diese Funktion kann das Remoting zu [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]-Servern und höher verarbeiten. Sie kann nicht das Remoting zu Servern einer niedrigeren Version als [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] verarbeiten.
  
## <a name="examples"></a>Beispiele  
In diesem Beispiel wird die `DATEFROMPARTS`-Funktion in Aktion dargestellt.
  
```sql
SELECT DATEFROMPARTS ( 2010, 12, 31 ) AS Result;  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
Result  
----------------------------------  
2010-12-31  
  
(1 row(s) affected)  
```  
  
## <a name="see-also"></a>Siehe auch
[date &#40;Transact-SQL&#41;](../../t-sql/data-types/date-transact-sql.md)
  
  

