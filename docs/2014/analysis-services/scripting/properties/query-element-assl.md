---
title: Abfrage-Element (ASSL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- Query Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
helpviewer_keywords:
- Query element
ms.assetid: 832c3337-de6d-43b2-8f1c-75bdba76539b
caps.latest.revision: 12
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 2917bfe5a0050a3e3baa17838dffc1e1d94a0172
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37308410"
---
# <a name="query-element-assl"></a>Query-Element (ASSL)
  Enthält den Text der Abfrage, die für die Benachrichtigung ausgeführt werden muss.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<QueryNotification>  
   <Query>...</Query>  
</QueryNotification>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Description|  
|--------------------|-----------------|  
|Datentyp und -länge|Zeichenfolge|  
|Standardwert|InclusionThresholdSetting|  
|Cardinality|1-1: Erforderliches Element, das nur einmal auftritt.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnetes Element|[QueryNotification](../objects/querynotification-element-assl.md)|  
|Untergeordnete Elemente|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Hinweise  
 Das Element, das dem übergeordneten entspricht `Query` im Objekt Analysis Management Objects (AMO) Modell ist <xref:Microsoft.AnalysisServices.QueryNotification>.  
  
## <a name="see-also"></a>Siehe auch  
 [ProactiveCachingQueryBinding-Datentyp &#40;ASSL&#41;](../data-type/binding-data-type-assl.md)   
 [Eigenschaften &#40;ASSL&#41;](properties-assl.md)  
  
  
