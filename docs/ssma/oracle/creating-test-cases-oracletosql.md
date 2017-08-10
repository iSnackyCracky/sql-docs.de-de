---
title: "Erstellen von Testfällen (OracleToSQL) | Microsoft Docs"
ms.prod: sql-non-specified
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Test Case Wizard
ms.assetid: 22f38901-ec35-4707-a911-784e6ad8dafb
caps.latest.revision: 7
author: sabotta
ms.author: carlasab
manager: v-thobro
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: c40ee9da718fec017381740d69b6fa71045572bd
ms.contentlocale: de-de
ms.lasthandoff: 08/02/2017

---
# <a name="creating-test-cases-oracletosql"></a>Erstellen von Testfällen (OracleToSQL)
Verwenden Sie den Testfall-Assistenten, um einen Test zu erstellen. Mit diesem Assistenten können Sie die Testfälle erstellen, durch Auswahl von Objekten überprüft und getestet, und geben Sie die Parameter testen.  
  
## <a name="starting-the-test-case-wizard"></a>Starten des Assistenten für Testfall  
Starten Sie den Testfall-Assistenten klicken Sie auf **neue Testfall...** aus der **Tester** Menü.  
  
Beim Starten überprüft des Assistenten für das Schema SSMATESTER_ORACLE auf dem Quellserver für die Oracle. Es ist der Tester Erweiterungsschema zum Speichern von erweiterten Objekten verwendet. Testfall Assistenten SSMATESTER_ORACLE gefunden, wird ein Dialogfeld angezeigt, das vorgeschlagen werden, um das Schema zu erstellen. (Diese Situation tritt in der Regel während der ersten Ausführung von SSMA Tester.)  
  
Wenn Sie im Dialogfenster erhalten, klicken Sie auf **Ja** SSMATESTER_ORACLE Schema auf dem Quellserver zu erstellen. Beachten Sie, dass Sie die Oracle-Berechtigungen zum Erstellen eines neuen Benutzers ein, und erstellen Objekte im Schema dieses Benutzers verfügen müssen.  
  
## <a name="overview-of-creating-test-cases-using-the-wizard"></a>Übersicht über das Erstellen von Testfällen, die mithilfe des Assistenten  
Das Verfahren zum Erstellen eines Testfalls besteht aus fünf Schritten:  
  
1.  [Initialisieren von Testfällen &#40; OracleToSQL &#41;](../../ssma/oracle/initializing-test-cases-oracletosql.md)  
  
2.  [Auswählen und Konfigurieren von Objekten zum Test &#40; OracleToSQL &#41;](../../ssma/oracle/selecting-and-configuring-objects-to-test-oracletosql.md)  
  
3.  [Auswählen und Konfigurieren von betroffenen Objekten &#40; OracleToSQL &#41;](../../ssma/oracle/selecting-and-configuring-affected-objects-oracletosql.md)  
  
4.  [Anpassen der Reihenfolge der Aufrufe &#40; OracleToSQL &#41;](../../ssma/oracle/customizing-calls-order-oracletosql.md)  
  
5.  [Beenden Testfall Vorbereitung &#40; OracleToSQL &#41;](../../ssma/oracle/finishing-test-case-preparation-oracletosql.md)  
  
## <a name="see-also"></a>Siehe auch  
[Testen von migriert Datenbankobjekte &#40; OracleToSQL &#41;](../../ssma/oracle/testing-migrated-database-objects-oracletosql.md)  
  
