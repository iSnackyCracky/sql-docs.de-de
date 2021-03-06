---
title: Mehrere Rangfolgeneinschränkungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- multiple precedence constraints
- precedence executables [Integration Services]
- precedence constraints [Integration Services], multiple
- constrained executables [Integration Services]
ms.assetid: 71c53ead-3d19-4bc1-aafd-e5b32595b420
caps.latest.revision: 44
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 60cd55a656849f3cb5eee9cac879a88d8d85ad4e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37231458"
---
# <a name="multiple-precedence-constraints"></a>Mehrere Rangfolgeneinschränkungen
  Eine Rangfolgeneinschränkung verbindet zwei ausführbare Dateien: zwei Tasks, zwei Container oder einen Task und einen Container. Sie werden als ausführbare Datei der Rangfolge und als eingeschränkte ausführbare Datei bezeichnet. Eine eingeschränkte ausführbare Datei kann mehrere Rangfolgeneinschränkungen haben. Weitere Informationen finden Sie unter [Precedence Constraints](control-flow/precedence-constraints.md).  
  
 Wenn Sie komplexe Einschränkungsszenarien durch Gruppieren von Einschränkungen zusammenfassen, können Sie eine komplexe Ablaufsteuerung in Paketen implementieren. Z. B. in der folgenden Abbildung Task D mit dem Task A durch eine `Success` -Einschränkung verlinkt, Task D ist mit dem Task B durch verknüpft eine `Failure` -Einschränkung, und Task D ist mit dem Task C durch eine `Success` Einschränkung. Die Rangfolgeneinschränkungen zwischen Task D und Task A, zwischen Task D und Task B sowie zwischen Task D und Task C nehmen an einer logischen *AND* -Beziehung teil. Damit Task D ausgeführt wird, muss Task A erfolgreich ausgeführt werden, bei Task B muss ein Fehler auftreten, und Task C muss erfolgreich ausgeführt werden.  
  
 ![Durch Rangfolgeneinschränkungen verknüpfte Tasks](media/precedenceconstraints.gif "Durch Rangfolgeneinschränkungen verknüpfte Tasks")  
  
## <a name="logicaland-property"></a>LogicalAnd-Eigenschaft  
 Falls ein Task oder ein Container mehrere Einschränkungen aufweist, gibt die `LogicalAnd`-Eigenschaft an, ob eine Rangfolgeneinschränkung einzeln oder zusammen mit anderen Einschränkungen ausgewertet wird.  
  
 Sie können festlegen, die `LogicalAnd` Eigenschaft mit der **Rangfolgeneinschränkungs-Editor** in [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer oder im Fenster Eigenschaften, die [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] bietet.  
  
## <a name="related-tasks"></a>Related Tasks  
 [Festlegen der Eigenschaften von Rangfolgeneinschränkungen](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md)  
  
  
