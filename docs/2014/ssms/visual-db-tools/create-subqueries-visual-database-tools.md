---
title: Erstellen von Unterabfragen (Visual Database Tools) | Microsoft-Dokumentation
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
- search criteria [SQL Server], subqueries
- nested queries
- subqueries [SQL Server], SQL pane
ms.assetid: 34f6b9b4-ca3a-4a4f-9594-36e513f1c547
caps.latest.revision: 11
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 1232ba9cd9fd4d13a90e6467f8365b958af9957f
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37315120"
---
# <a name="create-subqueries-visual-database-tools"></a>Erstellen von Unterabfragen (Visual Database Tools)
  Sie können die Ergebnisse einer Abfrage als Eingabe für eine andere Abfrage verwenden. Sie können die Ergebnisse einer Unterabfrage in einer Anweisung verwenden, die die IN( )-Funktion, den EXISTS-Operator oder die FROM-Klausel gebraucht.  
  
 Sie können eine Unterabfrage erstellen, indem Sie sie entweder direkt im SQL-Bereich eingeben oder indem Sie eine Abfrage kopieren und in eine andere einfügen.  
  
### <a name="to-define-a-subquery-in-the-sql-pane"></a>So definieren Sie eine Unterabfrage im SQL-Bereich  
  
1.  Erstellen Sie die primäre Abfrage.  
  
2.  Markieren Sie im SQL-Bereich die SQL-Anweisung, und kopieren Sie sie mit **Kopieren** in die Zwischenablage.  
  
3.  Dann rufen Sie die neue Abfrage auf und fügen die erste Abfrage mit **Einfügen** in die WHERE- oder FROM-Klausel der neuen Abfrage ein.  
  
     Angenommen, Sie haben zwei Tabellen, `products` und `suppliers`, und möchten eine Abfrage erstellen, in der alle Produkte von Lieferanten aus Schweden angezeigt werden. Dazu erstellen Sie die erste Abfrage anhand der Tabelle `suppliers` , um alle schwedischen Lieferanten zu herauszusuchen:  
  
    ```  
    SELECT supplier_id  
    FROM supplier  
    WHERE (country = 'Sweden')  
    ```  
  
     Kopieren Sie diese Abfrage mit dem Befehl Kopieren in die Zwischenablage. Die zweite Abfrage erstellen Sie anhand der Tabelle `products` , in der die erforderlichen Produktinformationen aufgeführt werden:  
  
    ```  
    SELECT product_id, supplier_id, product_name  
    FROM products  
    ```  
  
     Fügen Sie der zweiten Abfrage im SQL-Bereich eine WHERE-Klausel hinzu. Dann fügen Sie die erste Abfrage aus der Zwischenablage ein. Setzen Sie die erste Abfrage in Klammern, sodass das Endergebnis wie folgt aussieht:  
  
    ```  
    SELECT product_id, supplier_id, product_name  
    FROM products  
    WHERE supplier_id IN  
       (SELECT supplier_id  
      FROM supplier  
      WHERE (country = 'Sweden'))  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Unterstützte Abfragetypen &#40;Visual Database Tools&#41;](visual-database-tools.md)   
 [Angeben von Suchkriterien &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md)  
  
  
