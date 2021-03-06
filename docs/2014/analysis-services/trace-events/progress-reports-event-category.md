---
title: Progress Reports-Ereigniskategorie | Microsoft-Dokumentation
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
- progress events [Analysis Services]
- Progress Reports event category
- event classes [Analysis Services], progress reports
ms.assetid: c130f160-28ef-49bc-9ee6-da47dc9aab2a
caps.latest.revision: 22
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: b7e1925c6479c2530283700941e9382ee932a8e0
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37205720"
---
# <a name="progress-reports-event-category"></a>Fortschrittsbericht (Ereigniskategorie)
  Die Progress Reports-Ereigniskategorie enthält die in der folgenden Tabelle beschriebenen Ereignisklassen.  
  
|Ereignisklasse|Ereignis-ID|Description|  
|-----------------|--------------|-----------------|  
|Progress Report Begin|5|Sammelt alle Progress Report Begin-Ereignisse seit dem Start der Ablaufverfolgung.|  
|Progress Report End|6|Sammelt alle Progress Report End-Ereignisse seit dem Start der Ablaufverfolgung.|  
|Progress Report Current|7|Sammelt alle Progress Report Current-Ereignisse seit dem Start der Ablaufverfolgung. Beispielsweise enthalten während der Verarbeitung die Current Reports Verarbeitungsinformationen zu den verarbeiteten Objekten (Dimensionen, Partitionen, Cube usw.).|  
|Progress Report Error|8|Sammelt alle Progress Report Error-Ereignisse seit dem Start der Ablaufverfolgung.|  
  
 Jedes Progress Report Begin-Ereignis beginnt mit einem Datenstrom aus Progress-Ereignissen und wird durch ein Progress Report End-Ereignis beendet. Der Datenstrom kann jede beliebige Anzahl von Progress Report Current- und Progress Report Error-Ereignissen enthalten.  
  
 Informationen zu den Spalten, die den einzelnen Progress Reports-Ereignisklassen zugeordnet sind, finden Sie unter [Progress Reports Data Columns](progress-reports-data-columns.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Analysis Services-Ablaufverfolgungsereignisse](analysis-services-trace-events.md)  
  
  
