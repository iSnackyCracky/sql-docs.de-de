---
title: SIGN (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- positive values [Integration Services]
- SIGN function
- negative values
ms.assetid: 1547db08-4329-4781-91c2-36898ed71b15
caps.latest.revision: 32
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: c61c52a44caf90e6e5c7e819d2d8e4e3707caed9
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37207380"
---
# <a name="sign-ssis-expression"></a>SIGN (SSIS-Ausdruck)
  Gibt das positive (+1) oder negative (-1) Vorzeichen oder Null (0) für einen numerischen Ausdruck zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
SIGN(numeric_expression)  
```  
  
## <a name="arguments"></a>Argumente  
 *numeric_expression*  
 Ein gültiger numerischer Ausdruck mit Vorzeichen. Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).  
  
## <a name="result-types"></a>Ergebnistypen  
 DT_I4  
  
## <a name="remarks"></a>Hinweise  
 SIGN gibt ein NULL-Ergebnis zurück, wenn das Argument NULL ist.  
  
## <a name="expression-examples"></a>Beispiele für Ausdrücke  
 In diesem Beispiel wird das Vorzeichen eines numerischen Literals zurückgegeben. Als Ergebnis wird -1 zurückgegeben.  
  
```  
SIGN(-123.45)  
```  
  
 In diesem Beispiel wird das Vorzeichen aus der Subtraktion der **StandardCost** -Spalte von der **DealerPrice** -Spalte zurückgegeben.  
  
```  
SIGN(DealerPrice - StandardCost)  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen &#40;SSIS-Ausdruck&#41;](functions-ssis-expression.md)  
  
  
