---
title: Value-Element (ASSL) | Microsoft Docs
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
- Value Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- Value
helpviewer_keywords:
- Value element
ms.assetid: a2fad411-73fd-42df-b4e1-df2cb8454182
caps.latest.revision: 36
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 5b31ced28db41575887a07ccf6c6e303aea5aaf1
ms.contentlocale: de-de
ms.lasthandoff: 09/01/2017

---
# <a name="value-element-assl"></a>Value-Element (ASSL)
  Enthält den Wert des übergeordneten Elements.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<AlgorithmParameter> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <Value>...</Value>  
   ...  
</AlgorithmParameter>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|Finden Sie in der folgenden Tabelle aus.|  
|Standardwert|Keine|  
|Kardinalität|1-1: Erforderliches Element, das nur einmal auftritt.|  
  
|Vorgänger oder übergeordnetes Element|Datentyp|  
|------------------------|---------------|  
|[AlgorithmParameter](../../../analysis-services/scripting/objects/algorithmparameter-element-assl.md)|Jeder simpleType|  
|[ServerProperty](../../../analysis-services/scripting/objects/serverproperty-element-assl.md)|Jeder simpleType|  
|Alle sonstigen|String|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[AlgorithmParameter](../../../analysis-services/scripting/objects/algorithmparameter-element-assl.md), [Anmerkung](../../../analysis-services/scripting/objects/annotation-element-assl.md), [Kpi](../../../analysis-services/scripting/objects/kpi-element-assl.md), [ReportFormatParameter](../../../analysis-services/scripting/objects/reportformatparameter-element-asl.md), [ReportParameter](../../../analysis-services/scripting/objects/reportparameter-element-assl.md), [ServerProperty](../../../analysis-services/scripting/objects/serverproperty-element-assl.md)|  
|Untergeordnete Elemente|Keine|  
  
## <a name="remarks"></a>Hinweise  
 Das **Value** -Element enthält den Wert, der dem übergeordneten Element zugeordnet ist. Der erwartete Wert des **Value** -Elements hängt vom übergeordneten Element ab (siehe folgende Tabelle).  
  
|Übergeordnetes Element|Erwarteter Wert|  
|--------------------|--------------------|  
|[AlgorithmParameter](../../../analysis-services/scripting/objects/algorithmparameter-element-assl.md)|Der Wert des Algorithmusparameters.|  
|[Anmerkung](../../../analysis-services/scripting/objects/annotation-element-assl.md)|Der Wert der Anmerkung.|  
|[KPI](../../../analysis-services/scripting/objects/kpi-element-assl.md)|Ein Multidimensional Expressions (MDX)-Ausdruck, der verwendet wird, um den Wert des Key Performance Indicator (KPI) zu berechnen.|  
|[ReportFormatParameter](../../../analysis-services/scripting/objects/reportformatparameter-element-asl.md)|Der Wert des Berichtsformatparameters.|  
|[ReportParameter](../../../analysis-services/scripting/objects/reportparameter-element-assl.md)|Ein MDX-Ausdruck, der verwendet wird, um den Wert des Berichtsparameters zu berechnen.|  
|[ServerProperty](../../../analysis-services/scripting/objects/serverproperty-element-assl.md)|Der Wert der Servereigenschaft für die gerade ausgeführte Instanz.|  
  
 Die Elemente, die den übergeordneten Elementen von entsprechen **Wert** im Objektmodell von Analysis Management Objects (AMO) sind <xref:Microsoft.AnalysisServices.AlgorithmParameter>, <xref:Microsoft.AnalysisServices.Annotation>, <xref:Microsoft.AnalysisServices.Kpi>, <xref:Microsoft.AnalysisServices.ReportParameter>, und <xref:Microsoft.AnalysisServices.ServerProperty>.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbankeigenschaften &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  