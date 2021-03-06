---
title: Verzögerung (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 3c5479aa3ce855b554f34f72c5c86aa86eb04b9f
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34740879"
---
# <a name="lag-mdx"></a>Lag (MDX)


  Gibt das Element zurück, das eine angegebene Anzahl von Positionen vor einem angegebenen Element auf der Ebene des Elements liegt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
Member_Expression.Lag(Index)   
```  
  
## <a name="arguments"></a>Argumente  
 *Member_Expression*  
 Ein gültiger MDX-Ausdruck (Multidimensional Expressions), der ein Element zurückgibt.  
  
 *Index*  
 Ein gültiger numerischer Ausdruck, der die Anzahl der Elementpositionen angibt, die vor dem Element liegen sollen.  
  
## <a name="remarks"></a>Hinweise  
 Die Elementpositionen auf einer Ebene werden über die natürliche Reihenfolge der Attributhierarchie bestimmt. Die Nummerierung der Positionen basiert auf Null.  
  
 Wenn der angegebene Abstand 0 (null), ist die **Lag** Funktion gibt das angegebene Element selbst zurück.  
  
 Wenn der angegebene Abstand negativ ist, wird die **Lag** -Funktion ein nachfolgendes Element zurück.  
  
 `Lag(1)` entspricht der [PrevMember](../mdx/prevmember-mdx.md) Funktion. `Lag(-1)` entspricht der [NextMember](../mdx/nextmember-mdx.md) Funktion.  
  
 Die **Lag** Funktion ist vergleichbar mit der [führen](../mdx/lead-mdx.md) -Funktion, außer dass die **führen** Funktion sucht, in die entgegengesetzte Richtung auf die **Lag** Funktion. Somit ist `Lag(n)` äquivalent zu `Lead(-n)`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Wert December 2001 zurückgegeben:  
  
```  
SELECT [Date].[Fiscal].[Month].[February 2002].Lag(2) ON 0  
FROM [Adventure Works]  
  
```  
  
 Im folgenden Beispiel wird der Wert March 2002 zurückgegeben:  
  
```  
SELECT [Date].[Fiscal].[Month].[February 2002].Lag(-1) ON 0  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [MDX-Funktionsreferenz &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
