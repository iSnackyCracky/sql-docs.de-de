---
title: Erstellen von Spaltenaliasen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], aliases
- aliases [SQL Server], columns
ms.assetid: e2e1c166-8ea7-47a2-b6a7-e419bf0fa3bb
caps.latest.revision: 9
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 942279e0c731439f013bee345b5202fb7fed5960
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37291930"
---
# <a name="create-column-aliases-visual-database-tools"></a>Erstellen von Spaltenaliasen (Visual Database Tools)
  Zur Arbeitserleichterung können Sie Aliase für Spaltennamen, Berechnungen und zusammengefasste Werte erstellen. Beispielsweise können Sie einen Spaltenalias mit folgenden Funktionen erstellen:  
  
-   Erstellen eines Spaltennamens, z. B. "Total Amount" für einen Ausdruck wie `(quantity * unit_price)` oder für eine Aggregatfunktion.  
  
-   Erstellen einer Kurzform für einen Spaltennamen, z. B. `"d_id"` für `"discounts.stor_id."`  
  
 Wenn Sie einen Spaltenalias definiert haben, können Sie den Alias in einer SELECT-Abfrage zum Angeben der Ausgabe der Abfrageergebnisse verwenden.  
  
### <a name="to-create-a-column-alias"></a>So erstellen Sie einen Spaltenalias  
  
1.  Suchen Sie im Bereich **Kriterien**die Zeile mit der Datenspalte, für die Sie einen Alias erstellen möchten, und markieren Sie diese ggf. für die Ausgabe. Wenn die Datenspalte noch nicht im Datenblatt vorhanden ist, fügen Sie sie hinzu.  
  
2.  Geben Sie in der zu dieser Zeile gehörigen Spalte **Alias** den Alias ein. Der Alias muss allen Namenskonventionen für SQL entsprechen. Wenn der eingegebene Aliasname Leerzeichen enthält, wird er vom Abfrage- und Sicht-Designer automatisch in Trennzeichen eingeschlossen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen von Spalten zu Abfragen &#40;Visual Database Tools&#41;](visual-database-tools.md)   
 [Sortieren und gruppieren Abfrageergebnisse &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md)   
 [Zusammenfassen von Abfrageergebnissen &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md)   
 [Ausführen grundlegender Vorgänge mit Abfragen &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
