---
title: FeatureSet-Element (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- FeatureSet element
ms.assetid: f2070c53-4a5c-4c11-ac38-96ee200c84f0
caps.latest.revision: 14
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: fb596ca38310bce4b9be6f1061952ebc2756fc73
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37226510"
---
# <a name="featureset-element-dta"></a>FeatureSet-Element (DTA)
  Enthält die physischen Entwurfsstrukturen (Indizes oder indizierte Sichten), die der Datenbankoptimierungsratgeber bei der Analyse verwenden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <FeatureSet>...</FeatureSet>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Description|  
|--------------------|-----------------|  
|**Datentyp und -länge**|`string`, keine maximale Länge.|  
|**Zulässige Werte**|**IDX_IV**<br /> Indizes und indizierte Sichten.<br /><br /> **IDX**<br /> Nur Indizes.<br /><br /> **IV**<br /> Nur indizierte Sichten.<br /><br /> **NCL_IDX**<br /> Nur nicht gruppierte Indizes.<br /><br /> Verwenden Sie einen dieser Werte mit diesem Element.|  
|**Standardwert**|**IDX**|  
|**Vorkommen**|Einmalig erforderlich für jedes `TuningOptions`-Element, es sei denn, das `DropOnlyMode`-Element wird verwendet. Wenn `DropOnlyMode` wird verwendet, können keine `FeatureSet`. Diese Elemente schließen sich gegenseitig aus.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Elemente|  
|------------------|--------------|  
|**Übergeordnetes Element**|[TuningOptions-Element &#40;DTA&#41;](tuningoptions-element-dta.md)|  
|**Untergeordnete Elemente**|Keine.|  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung dieses Elements finden Sie unter [Beispiel für eine einfache XML-Eingabedatei &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).  
  
## <a name="see-also"></a>Siehe auch  
 
  [XML-Eingabedateireferenz &amp;#40;Datenbankoptimierungsratgeber&amp;#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
