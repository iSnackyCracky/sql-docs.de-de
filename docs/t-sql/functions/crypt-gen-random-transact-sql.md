---
title: CRYPT_GEN_RANDOM (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- CRYPT_GEN_RANDOM_TSQL
- CRYPT_GEN_RANDOM
dev_langs:
- TSQL
helpviewer_keywords:
- CRYPT_GEN_RANDOM function
ms.assetid: b74bd9d4-758e-4b94-89a0-76dcda6d8c42
caps.latest.revision: 11
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: a97e2afca882d168f4ca0f6143680f85ccd002ae
ms.sourcegitcommit: 05e18a1e80e61d9ffe28b14fb070728b67b98c7d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/04/2018
ms.locfileid: "37781041"
---
# <a name="cryptgenrandom-transact-sql"></a>CRYPT_GEN_RANDOM (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Diese Funktion gibt eine von der Crypto API (CAPI) generierte Kryptografie-Zufallszahl aus. `CRYPT_GEN_RANDOM` gibt eine hexadezimale Zahl mit der Länge einer angegebenen Anzahl Bytes zurück.
  
![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntax  
  
```sql
CRYPT_GEN_RANDOM ( length [ , seed ] )   
```  
  
## <a name="arguments"></a>Argumente  
*length*  
Die Länge der Zahl in Bytes, die von `CRYPT_GEN_RANDOM` erstellt wird. Das *length*-Argument weist einen **int**Datentyp und einen Wertebereich zwischen 1 und 8000 auf. `CRYPT_GEN_RANDOM` gibt NULL für einen **int**-Wert außerhalb dieses Bereichs zurück. 
  
*seed*  
Eine optionale Hexadezimalzahl für die Verwendung als zufälliger Ausgangswert. Die Länge von *seed* muss mit dem Wert des *length*-Arguments übereinstimmen. Das *seed*-Argument weist den Datentyp **varbinary(8000)** auf.
  
## <a name="returned-types"></a>Rückgabetypen  
**varbinary(8000)**
  
## <a name="permissions"></a>Berechtigungen  
Diese Funktion ist öffentlich und erfordert keine besonderen Berechtigungen.
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-generating-a-random-number"></a>A. Generieren einer Zufallszahl  
In diesem Beispiel wird eine Zufallszahl von 50 Byte Länge generiert:
  
```sql
SELECT CRYPT_GEN_RANDOM(50) ;  
```  
  
In diesem Beispiel wird mithilfe eines Seeds von 4 Byte eine Zufallszahl von 4 Byte Länge generiert:
  
```sql
SELECT CRYPT_GEN_RANDOM(4, 0x25F18060) ;  
```  
  
## <a name="see-also"></a>Siehe auch
[RAND &#40;Transact-SQL&#41;](../../t-sql/functions/rand-transact-sql.md)
  
  
