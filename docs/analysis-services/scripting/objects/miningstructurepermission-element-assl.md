---
title: Miningstructurepermissions-Element (ASSL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- MiningStructurePermission Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- MiningStructurePermission
helpviewer_keywords:
- MiningStructurePermission element
ms.assetid: 4ba2bfd2-9003-4eed-8049-a74d452894ea
caps.latest.revision: 43
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 22713569509019e9d0aac30f82c898c73a034fda
ms.contentlocale: de-de
ms.lasthandoff: 09/01/2017

---
# <a name="miningstructurepermission-element-assl"></a>MiningStructurePermissions-Element (ASSL)
  Definiert den Berechtigungen, die Elemente einer [Rolle](../../../analysis-services/scripting/objects/role-element-assl.md) Element besitzen, für ein einzelnes [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) Element.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<MiningStructurePermissions>  
   <MiningStructurePermission xsi:type="Permission">  
      <AllowDrillthrough>...</AllowDrillthrough>  
  
      <!-- This element also inherits all the child elements listed in Permission -->  
   </MiningStructurePermission>  
</MiningStructurePermissions>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|[Berechtigung](../../../analysis-services/scripting/data-type/permission-data-type-assl.md)|  
|Standardwert|Keine|  
|Kardinalität|0-n: Optionales Element, das mehr als einmal auftreten kann.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[MiningStructurePermissions](../../../analysis-services/scripting/collections/miningstructurepermissions-element-assl.md)|  
|Untergeordnete Elemente|Keine|  
  
## <a name="remarks"></a>Hinweise  
 Das entsprechende Element im Objektmodell von Analysis Management Objects (AMO) ist <xref:Microsoft.AnalysisServices.MiningStructurePermission>.  
  
 In [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], die Berechtigung **AllowDrillthrough** wurde erweitert, damit auf eine Miningstruktur angewendet. Wenn Sie diese Berechtigung einer Rolle zuordnen, kann jeder Benutzer, der ein Mitglied dieser Rolle ist, die Miningstruktur mit der folgenden Syntax direkt abfragen:  
  
```  
SELECT <structure column list> FROM <structure>.CASES  
```  
  
 Darüber hinaus Wenn **AllowDrillthrough** aktiviert ist auf die Miningstruktur und das Miningmodell, können Benutzer, die nicht im Miningmodell enthalten waren, mithilfe der folgenden Syntax strukturspalten Abfragen:  
  
```  
SELECT StructureColumn('<structure column name>' FROM <model>.CASES  
```  
  
 Zum Beispiel erstellen Sie nur mit Spalten für Kundenschlüssel, Kundeneinkommen und Kundenkäufe ein Modell. Mit Drillthrough kann ein Benutzer andere Strukturspalten zurückgeben, die nicht im Miningmodell enthalten waren, z. B. Kundenkontaktinformationen.  
  
 Aus diesem Grund zum Schutz sensibler oder persönlicher Informationen sollten, erstellen Sie die Datenquellensicht aus, um persönliche Informationen verborgen sind, und gewähren Sie **AllowDrillthrough** -Berechtigung für eine Miningstruktur nur bei Bedarf.  
  
 Weitere Informationen finden Sie unter [Drillthroughabfragen &#40;Data Mining&#41;](../../../analysis-services/data-mining/drillthrough-queries-data-mining.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.AnalysisServices.MiningModel.AllowDrillThrough%2A>   
 <xref:Microsoft.AnalysisServices.AdomdClient.MiningModel.AllowDrillThrough%2A>   
 [Objekte &#40; ASSL &#41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  