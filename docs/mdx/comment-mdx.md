---
title: Kommentar (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 6469921572b8a1809e228fff0d25061475399ae7
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34740719"
---
# <a name="comment-mdx"></a>Kommentar (MDX)


  Zeigt vom Benutzer bereitgestellten Kommentartext an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
/* Comment_Text */      
```  
  
#### <a name="parameters"></a>Parameter  
 *Comment_Text*  
 Die Zeichenfolge, die den Text des Kommentars enthält.  
  
## <a name="remarks"></a>Hinweise  
 Der Server wertet nicht den Text zwischen den Kommentarzeichen / * und \*/. Kommentare können sowohl in einer eigenen Zeile als auch innerhalb einer MDX-Anweisung (Multidimensional Expressions) eingefügt werden. Mehrzeilige Kommentare müssen angegeben werden, indem Sie /\* und \*/.  
  
 Es gibt keine Maximallänge für Kommentare. Kommentare können geschachtelt sein; so ist `/* Test /*Comment*/ Text*/` ein Beispiel für einen geschachtelten Kommentar.  
  
## <a name="examples"></a>Beispiele  
 Das folgende Beispiel zeigt die Verwendung dieses Operators.  
  
```  
/* This member returns the gross profit margin for product types  
  and reseller types crossjoined by year. */  
SELECT   
    [Date].[Calendar].[Calendar Year].Members *  
    [Reseller].[Reseller Type].Children ON 0,  
    [Product].[Category].[Category].Members ON 1  
FROM /* Select from the Adventure Works cube. */  
    [Adventure Works]  
WHERE  
    [Measures].[Gross Profit Margin]  
```  
  
## <a name="see-also"></a>Siehe auch  
 [&#40;Kommentar&#41; &#40;MDX&#41;](../mdx/comment-mdx-double-slash.md)   
 [-- &#40;Kommentar&#41; &#40;MDX&#41;](../mdx/comment-mdx-operator-reference.md)   
 [MDX-Operatorreferenz &#40;MDX&#41;](../mdx/mdx-operator-reference-mdx.md)  
  
  
