---
title: SMALLDATETIMEFROMPARTS (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- SMALLDATETIMEFROMPARTS
- SMALLDATETIMEFROMPARTS_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- SMALLDATETIMEFROMPARTS function
ms.assetid: 7467fdab-e588-419c-9e29-42caec34a9ea
caps.latest.revision: 14
author: MashaMSFT
ms.author: mathoma
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: 2cf9461c5c03e0a3c73dc80e89c095297d206e90
ms.sourcegitcommit: e02c28b0b59531bb2e4f361d7f4950b21904fb74
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39451275"
---
# <a name="smalldatetimefromparts-transact-sql"></a>SMALLDATETIMEFROMPARTS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-all-md](../../includes/tsql-appliesto-ss2012-all-md.md)]

  Gibt einen **smalldatetime**-Wert für das angegebene Datum und die Uhrzeit zurück.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
SMALLDATETIMEFROMPARTS ( year, month, day, hour, minute )  
```  
  
## <a name="arguments"></a>Argumente  
 *year*  
 Ganzzahliger Ausdruck, der ein Jahr angibt.  
  
 *month*  
 Ganzzahliger Ausdruck, der einen Monat angibt.  
  
 *day*  
 Ganzzahliger Ausdruck, der einen Tag angibt.  
  
 *hour*  
 Ganzzahliger Ausdruck, der die Stunden angibt.  
  
 *minute*  
 Ganzzahliger Ausdruck, der die Minuten angibt.  
  
## <a name="return-types"></a>Rückgabetypen  
 **smalldatetime**  
  
## <a name="remarks"></a>Remarks  
 Diese Funktion dient als Konstruktor für einen vollständig initialisierten **smalldatetime**-Wert. Wenn die Argumente nicht gültig sind, wird ein Fehler ausgegeben. Wenn erforderliche Argumente den Wert NULL haben, wird NULL zurückgegeben.  
  
 Diese Funktion kann remote auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]-Servern oder höher ausgeführt werden. Eine Remoteausführung auf Servern mit einer Version vor [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ist nicht möglich.  
  
## <a name="examples"></a>Beispiele  
  
```  
SELECT SMALLDATETIMEFROMPARTS ( 2010, 12, 31, 23, 59 ) AS Result  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
Result  
---------------------------  
2011-01-01 00:00:00  
  
(1 row(s) affected)  
```  
  

