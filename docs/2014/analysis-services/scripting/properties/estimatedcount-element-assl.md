---
title: EstimatedCount-Element (ASSL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- EstimatedCount Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- EstimatedCount
helpviewer_keywords:
- EstimatedCount element
ms.assetid: ce84b54a-8ab2-42f4-a7dd-e10a3d41cb4d
caps.latest.revision: 32
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: a69d67554d0090e0e586421986bc97ba556c84a4
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37300850"
---
# <a name="estimatedcount-element-assl"></a>EstimatedCount-Element (ASSL)
  Enthält die geschätzte Anzahl von Elementen eines Attributs, gemäß der Definition vom Benutzer.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<AggregationDesignAttribute> <!-- or DimensionAttribute -->  
      ...  
   <EstimatedCount>...</EstimatedCount>  
   ...  
</AggregationDesignAttribute>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Description|  
|--------------------|-----------------|  
|Datentyp und -länge|Long|  
|Standardwert|InclusionThresholdSetting|  
|Cardinality|0-1: Optionales Element, das nur einmal auftreten kann.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[AggregationDesignAttribute](../data-type/aggregationdesignattribute-data-type-assl.md), [DimensionAttribute-Objekt](../data-type/dimensionattribute-data-type-assl.md)|  
|Untergeordnete Elemente|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Wert wird vom Benutzer zugewiesen und wird verwendet, durch die [AggregationDesign-Element &#40;ASSL&#41;](../objects/aggregationdesign-element-assl.md).  
  
 Die Elemente, die den übergeordneten Elementen von entsprechen `EstimatedCount` im Analysis Management Objects (AMO)-Objektmodell werden <xref:Microsoft.AnalysisServices.AggregationDesignAttribute> und <xref:Microsoft.AnalysisServices.DimensionAttribute>.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaften &#40;ASSL&#41;](properties-assl.md)  
  
  
