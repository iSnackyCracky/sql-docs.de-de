---
title: Gleichgeordnete Elemente (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: a4414e134d3b837406c3cb72566084029cf522c9
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34742849"
---
# <a name="siblings-mdx"></a>Siblings (MDX)


  Gibt die gleichgeordneten Elemente eines angegebenen Elements zurück, einschließlich des Elements selbst.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
Member_Expression.Siblings   
```  
  
## <a name="arguments"></a>Argumente  
 *Member_Expression*  
 Ein gültiger MDX-Ausdruck (Multidimensional Expressions), der ein Element zurückgibt.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das Standardmeasure für die gleichgeordneten Elemente von March 2003 (January 2003, February 2003 und March 2003) zurückgegeben.  
  
```  
SELECT [Date].[Calendar].[Month].[March 2003].Siblings ON 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>Siehe auch  
 [MDX-Funktionsreferenz &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
