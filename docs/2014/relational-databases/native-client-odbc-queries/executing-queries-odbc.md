---
title: Ausführen von Abfragen (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- ODBC applications, executing queries
- SQL Server Native Client ODBC driver, statements
- ODBC applications, statements
- SQL Server Native Client ODBC driver, queries
- queries [ODBC]
ms.assetid: d935bcba-8ce6-4159-8395-6c86431602ad
caps.latest.revision: 31
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 552a9d37d06ba145e371650dd56027ca38eb7c20
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37416279"
---
# <a name="executing-queries-odbc"></a>Ausführen von Abfragen (ODBC)
  Nachdem eine ODBC-Anwendung ein Verbindungshandle initialisiert und eine Verbindung zu einer Datenquelle hergestellt hat, weist sie dem Verbindungshandle ein oder mehrere Anweisungshandles zu. Die Anwendung kann dann ausführen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Anweisungen für das Anweisungshandle. Die übliche Reihenfolge bei der Ausführung einer SQL-Anweisung ist:  
  
1.  Festlegen aller erforderlichen Anweisungsattribute.  
  
2.  Erstellen der Anweisung.  
  
3.  Ausführen der Anweisung.  
  
4.  Abrufen der Resultsets.  
  
 Erst nachdem eine Anwendung alle Zeilen in sämtlichen von der SQL-Anweisung zurückgegebenen Resultsets abgerufen hat, kann sie eine weitere Abfrage über dasselbe Anweisungshandle ausführen. Wenn eine Anwendung feststellt, dass es nicht erforderlich ist, um alle Zeilen in einem bestimmten Resultset abzurufen, können sie den Rest des Resultsets durch Aufrufen von entweder Abbrechen [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) oder [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).  
  
 Wenn Sie in einer ODBC-Anwendung dieselbe SQL-Anweisung mehrfach mit unterschiedlichen Daten ausführen müssen, verwenden Sie bei der Erstellung der SQL-Anweisung eine Parametermarkierung in Form eines Fragezeichens (?):  
  
```  
INSERT INTO MyTable VALUES (?, ?, ?)  
```  
  
 Jede parametermarkierung kann dann an eine Programmvariable gebunden werden, durch den Aufruf [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md).  
  
 Nachdem alle SQL-Anweisungen ausgeführt und ihre Resultsets verarbeitet wurden, gibt die Anwendung das Anweisungshandle frei.  
  
 Die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber unterstützt mehrere Anweisungshandles pro Verbindungshandle. Transaktionen werden auf Verbindungsebene verwaltet, d. h. alle über sämtliche Anweisungshandles auf einem einzelnen Verbindungshandle ausgeführten Aufgaben werden als Bestandteil derselben Transaktion verwaltet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
-   [Zuordnen eines Anweisungshandles](allocating-a-statement-handle.md)  
  
-   [Erstellen einer SQL­Anweisung &#40;ODBC&#41;](constructing-an-sql-statement-odbc.md)  
  
-   [Erstellen von SQL-Anweisungen für Cursor](constructing-sql-statements-for-cursors.md)  
  
-   [Verwenden von Anweisungsparametern](using-statement-parameters.md)  
  
-   [Ausführen von Anweisungen &#40;ODBC&#41;](executing-statements/executing-statements-odbc.md)  
  
-   [Freigeben eines Anweisungshandles](freeing-a-statement-handle.md)  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
