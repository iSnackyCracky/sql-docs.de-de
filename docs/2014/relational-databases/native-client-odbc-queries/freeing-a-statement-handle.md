---
title: Freigeben eines Anweisungshandles | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- reusing statement handles
- freeing statement handles
- statements [ODBC], statement handles
- SQLFreeStmt function
- ODBC applications, statements
- statement handles [ODBC]
ms.assetid: 96fdff84-0ca7-460a-a240-94ee826ea41c
caps.latest.revision: 31
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 3da32585644e0bd7d3a572ef2052f387e4d33232
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37426729"
---
# <a name="freeing-a-statement-handle"></a>Freigeben eines Anweisungshandles
  Es ist effizienter, Anweisungshandles wieder zu verwenden, als sie zu löschen und neu zuzuordnen. Vor dem Ausführen einer neuen SQL-Anweisung für ein Anweisungshandle sollten Anwendungen überprüfen, ob die aktuellen Anweisungseinstellungen korrekt sind. Dazu zählen beispielsweise Anweisungsattribute, Parameterbindungen und Resultsetbindungen. Im allgemeinen Parameter und Resultsets legt fest, für die alte SQL-Anweisung aufgehoben werden muss, durch den Aufruf [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) mit dem SQL_RESET_PARAMS und SQL_UNBIND "Optionen", und klicken Sie dann die Bindung erneut für die neue SQL-Anweisung.  
  
 Wenn die Anwendung mithilfe der Anweisung abgeschlossen ist, ruft er [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) um die Anweisung freizugeben. Beachten Sie, dass **SQLDisconnect** alle Anweisungen für eine Verbindung automatisch freigibt.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausführen von Abfragen &#40;ODBC&#41;](executing-queries-odbc.md)  
  
  
