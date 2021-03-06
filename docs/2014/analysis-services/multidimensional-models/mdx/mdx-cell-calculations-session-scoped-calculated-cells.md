---
title: Erstellen im Bereich einer Sitzung berechnete Zellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- session-scoped calculated members [MDX]
ms.assetid: f2d14a89-6286-4e74-9afb-091076f93f21
caps.latest.revision: 14
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 1df213e83122d3d93a57c2bbdd131741043ffe7c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37232090"
---
# <a name="creating-session-scoped-calculated-cells"></a>Erstellen berechneter Zellen im Bereich einer Sitzung
    
> [!IMPORTANT]  
>  Diese Syntax wurde als veraltet markiert. Sie sollten stattdessen MDX-Zuweisungen verwenden. Weitere Informationen zu Zuweisungen finden Sie unter [Grundlegendes MDX-Skript &#40;MDX&#41;](the-basic-mdx-script-mdx.md).  
  
 Wenn Sie berechnete Zellen erstellen möchten, die für alle Abfragen in derselben Sitzung verfügbar sind, verwenden Sie entweder die [CREATE CELL CALCULATION](/sql/mdx/mdx-data-definition-create-cell-calculation) -Anweisung oder die [ALTER CUBE](/sql/mdx/mdx-data-definition-alter-cube) -Anweisung. Beide Anweisungen führen zum selben Ergebnis.  
  
## <a name="create-cell-calculation-syntax"></a>Syntax von CREATE CELL CALCULATION  
  
> [!IMPORTANT]  
>  Diese Syntax wurde als veraltet markiert. Sie sollten stattdessen MDX-Zuweisungen verwenden. Weitere Informationen zu Zuweisungen finden Sie unter [Grundlegendes MDX-Skript &#40;MDX&#41;](the-basic-mdx-script-mdx.md).  
  
 Verwenden Sie folgende Syntax, wenn Sie mit der CREATE CELL CALCULATION-Anweisung eine berechnete Zelle im Bereich einer Sitzung definieren möchten:  
  
```  
CREATE CELL CALCULATION Cube_Expression.<CREATE CELL CALCULATION body clause>  
  
<CREATE CELL CALCULATION body clause> ::=CellCalc_Identifier FOR String_Expression AS 'MDX_Expression'   
   [ <CREATE CELL CALCULATION property clause> [ , <CREATE CELL CALCULATION property clause> ... ] ]  
  
<CREATE CELL CALCULATION property clause> ::=  
   ( CONDITION = 'Logical_Expression' ) |   
   ( DISABLED = { TRUE | FALSE } ) |   
   ( DESCRIPTION =String_Expression ) |   
   ( CALCULATION_PASS_NUMBER = Integer_Expression ) |   
   ( CALCULATION_PASS_DEPTH = Integer_Expression ) |   
   ( SOLVE_ORDER = Integer_Expression ) |   
   ( FORMAT_STRING = String_Expression ) |   
   ( CellProperty_Identifier = Scalar_Expression )  
```  
  
## <a name="alter-cube-syntax"></a>Syntax von ALTER CUBE  
  
> [!IMPORTANT]  
>  Diese Syntax wurde als veraltet markiert. Sie sollten stattdessen MDX-Zuweisungen verwenden. Weitere Informationen zu Zuweisungen finden Sie unter [Grundlegendes MDX-Skript &#40;MDX&#41;](the-basic-mdx-script-mdx.md).  
  
 Verwenden Sie folgende Syntax, wenn Sie mit der ALTER CUBE -Anweisung eine berechnete Zelle im Bereich einer Sitzung definieren möchten:  
  
```  
ALTER CUBE Cube_Identifier CREATE CELL CALCULATION  
FOR String_Expression AS 'MDX_Expression'   
   [ <CREATE CELL CALCULATION property clause> [ , <CREATE CELL CALCULATION property clause> ... ] ]  
  
<CREATE CELL CALCULATION property clause> ::=  
   ( CONDITION = 'Logical_Expression' ) |   
   ( DISABLED = { TRUE | FALSE } ) |   
   ( DESCRIPTION =String_Expression ) |   
   ( CALCULATION_PASS_NUMBER = Integer_Expression ) |   
   ( CALCULATION_PASS_DEPTH = Integer_Expression ) |   
   ( SOLVE_ORDER = Integer_Expression ) |   
   ( FORMAT_STRING = String_Expression ) |   
   ( CellProperty_Identifier = Scalar_Expression )  
```  
  
 Der `String_Expression` -Wert enthält eine Liste der orthogonalen, eindimensionalen MDX-Mengenausdrücke, von denen jeder aufgelöst zu einer der Mengenkategorien gehören muss, die in der folgenden Tabelle aufgelistet sind.  
  
|Kategorie|Description|  
|--------------|-----------------|  
|Leere Menge|Ein MDX-Mengenausdruck, der zu einer leeren Menge aufgelöst wird. In diesem Fall ist der Gültigkeitsbereich der berechneten Zelle gleich dem gesamten Cube.|  
|Menge mit einem einzelnen Element|Ein MDX-Mengenausdruck, der zu einem einzelnen Element aufgelöst wird.|  
|Menge von Ebenenelementen|Ein MDX-Mengenausdruck, der zu den Elementen einer einzelnen Ebene aufgelöst wird. Ein Beispiel hierfür ist die *Level_Expression*.`Members` MDX-Funktion. Um berechnete Elemente einzuschließen, verwenden die *Level_Expression*.`AllMembers` MDX-Funktion.<br /><br /> Weitere Informationen finden Sie unter [AllMembers &#40;MDX&#41;](/sql/mdx/allmembers-mdx).|  
|Menge nachfolgender Werte|Ein MDX-Mengenausdruck, der zu den nachfolgenden Werten eines angegebenen Elements aufgelöst wird. Ein Beispiel hierfür ist die `Descendants`(*Member_Expression*, *Level_Expression*, *Desc_Flag*)-Funktion von MDX.<br /><br /> Weitere Informationen finden Sie unter [Descendants &#40;MDX&#41;](/sql/mdx/descendants-mdx).|  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Zellenberechnungen in MDX &#40;MDX&#41;](../../multidimensional-models-olap-logical-cube-objects/calculations.md)  
  
  
