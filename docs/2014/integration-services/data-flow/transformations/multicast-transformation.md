---
title: Transformation für Multicast | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multicasttrans.f1
helpviewer_keywords:
- multiple outputs
- Multicast transformation
- datasets [Integration Services], multiple outputs
- multiple transformations
ms.assetid: 32194784-1684-40cd-9f91-1aba4d8360d3
caps.latest.revision: 44
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: ead69f8be189f80fedb30493a7c8be64178d3e39
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37231440"
---
# <a name="multicast-transformation"></a>Transformation für Multicast
  Die Multicasttransformation verteilt ihre Eingabe an mindestens eine Ausgabe. Diese Transformation ist mit der Transformation für bedingtes Teilen vergleichbar. Beide Transformationen leiten eine Ausgabe an mehrere Ausgaben weiter. Der Unterschied zwischen den beiden Transformationen besteht darin, dass die Multicasttransformation jede Zeile an jede Ausgabe weiterleitet, während die Transformation für bedingtes Teilen eine Zeile an eine einzelne Ausgabe weiterleitet. Weitere Informationen finden Sie unter [Conditional Split Transformation](conditional-split-transformation.md).  
  
 Zum Konfigurieren der Multicasttransformation fügen Sie Ausgaben hinzu.  
  
 Mithilfe der Multicasttransformation kann ein Paket logische Kopien von Daten erstellen. Dies ist hilfreich, wenn das Paket mehrere Transformationen auf dieselben Daten anwenden muss. Angenommen, eine Kopie der Daten wird aggregiert und nur die Zusammenfassungsinformationen werden in das Ziel geladen, während die andere Kopie der Daten mit Nachschlagewerten und abgeleiteten Spalten erweitert wird, bevor sie in das Ziel geladen wird.  
  
 Diese Transformation weist eine Eingabe und mehrere Ausgaben auf. Eine Fehlerausgabe wird nicht unterstützt.  
  
## <a name="configuration-of-the-multicast-transformation"></a>Konfiguration der Multicasttransformation  
 Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.  
  
 Weitere Informationen zu den Eigenschaften, die Sie im Dialogfeld **Transformations-Editor für Multicast** festlegen können, finden Sie unter [Multicast Transformation Editor](../../multicast-transformation-editor.md).  
  
 Weitere Informationen zu den Eigenschaften, die Sie programmgesteuert festlegen können, finden Sie unter [Common Properties](../../common-properties.md).  
  
## <a name="related-tasks"></a>Related Tasks  
 Informationen zum Festlegen der Eigenschaften dieser Komponente finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](../set-the-properties-of-a-data-flow-component.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenfluss](../data-flow.md)   
 [SQL Server Integration Services-Transformationen](integration-services-transformations.md)  
  
  
