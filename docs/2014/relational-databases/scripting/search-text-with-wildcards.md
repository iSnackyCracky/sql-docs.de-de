---
title: Suchen von Text mit Platzhaltern| Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- vs.wildcards
- vswildcardsbuilder
helpviewer_keywords:
- searches [SQL Server Management Studio], wildcards
- Query Editor [SQL Server Management Studio], wildcard searches
- wildcard options [SQL Server Management Studio]
ms.assetid: 449600f8-cc87-4b3f-878a-59c158a88a40
caps.latest.revision: 22
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 32a088a9f868c1063d8d6650b759b855d1192ac2
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37172371"
---
# <a name="search-text-with-wildcards"></a>Suchen von Text mit Platzhaltern
  Mit den folgenden Ausdrücken lassen sich Zeichen oder Ziffern im Feld **Suchen nach** im Dialogfeld [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **in** ersetzen.  
  
#### <a name="to-search-using-wildcards"></a>So suchen Sie mit Platzhaltern  
  
1.  Um die Verwendung von Platzhaltern im Feld **Suchen nach** bei der Schnellsuche, **In Dateien suchen**, **Schnellersetzung**oder **In Dateien ersetzen** zu aktivieren, wählen Sie unter **Suchoptionen** nacheinander **Verwenden** und dann **Platzhalter**aus.  
  
2.  Die dreieckige Schaltfläche für die **Verweisliste** neben dem Feld **Suchen nach** ist jetzt aktiviert. Klicken Sie auf diese Schaltfläche, um eine Liste der verfügbaren Platzhalter anzuzeigen. Wenn Sie ein Element aus der Liste für die **Verweisliste** auswählen, wird es in die **Suchen nach** -Zeichenfolge eingefügt.  
  
 Die folgende Tabelle enthält eine Beschreibung der Platzhalter, die unter **Verweisliste**verfügbar sind.  
  
|expression|Syntax|Description|  
|----------------|------------|-----------------|  
|Ein einzelnes Zeichen|?|Entspricht einem beliebigen einzelnen Zeichen.|  
|Eine einzelne Ziffer|#|Entspricht einer beliebigen einzelnen Ziffer. Beispiel: 7# entspricht Zahlen, die aus einer 7 bestehen, gefolgt von einer anderen Zahl, wie 71, nicht aber 17.|  
|Zeichen außerhalb des Zeichensatzes|[! ]|Entspricht einem einzelnen Zeichen, das nicht im Zeichensatz angegeben ist.|  
|Ein oder mehrere Zeichen|*|Entspricht einem oder mehreren Zeichen. Beispiel: new* entspricht einem beliebigen Text mit der Buchstabenfolge "new", z. B. newfile.txt.|  
|Zeichensatz|[ ]|Entspricht einem einzelnen Zeichen, das im Zeichensatz angegeben ist.|  
  
## <a name="see-also"></a>Siehe auch  
 [Suchen und Ersetzen](search-and-replace.md)   
 [Suchen von Text mit regulären Ausdrücken](search-text-with-regular-expressions.md)  
  
  
