---
title: RollbackTransaction-Element (XMLA) | Microsoft-Dokumentation
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
- RollbackTransaction Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#RollbackTransaction
- microsoft.xml.analysis.rollbacktransaction
- urn:schemas-microsoft-com:xml-analysis#RollbackTransaction
helpviewer_keywords:
- RollbackTransaction command
ms.assetid: 40e7dc00-656f-412f-97f0-d05bf7caa196
caps.latest.revision: 13
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: eaaf3d92849e0d2ddb7f94686bb30e627d3abcb7
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37300800"
---
# <a name="rollbacktransaction-element-xmla"></a>RollbackTransaction-Element (XMLA)
  Rollback einer Transaktion für die aktuelle Sitzung mit einer Instanz von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<Command>  
   <RollbackTransaction />  
</Command>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Description|  
|--------------------|-----------------|  
|Datentyp und -länge|InclusionThresholdSetting|  
|Standardwert|InclusionThresholdSetting|  
|Cardinality|0-n: Optionales Element, das mehr als einmal auftreten kann.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[Befehl](../xml-elements-properties/command-element-xmla.md)|  
|Untergeordnete Elemente|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Hinweise  
 Der `RollbackTransaction`-Befehl führt ein Rollback für alle aktiven Transaktionen, die explizit durch das `BeginTransaction`-Element definiert sind, auf der aktuellen Sitzung durch. Wenn keine aktive Transaktion vorhanden ist, tritt ein Fehler auf. Wenn bereits eine aktive Transaktion vorhanden ist, die [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] -Instanz den Verweiszähler den Verweiszähler der Transaktionen, für die aktuelle Sitzung 0 (null), der für alle aktiven Transaktionen.  
  
## <a name="see-also"></a>Siehe auch  
 [BeginTransaction-Element &#40;XMLA&#41;](begintransaction-element-xmla.md)   
 [Cancel-Element &#40;XMLA&#41;](cancel-element-xmla.md)   
 [CommitTransaction-Element &#40;XMLA&#41;](committransaction-element-xmla.md)   
 [Befehle &#40;XMLA&#41;](xml-elements-commands.md)  
  
  
