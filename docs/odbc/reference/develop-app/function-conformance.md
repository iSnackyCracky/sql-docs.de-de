---
title: Funktion Konformität | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- conformance levels [ODBC], function
- function conformance levels [ODBC]
- data sources [ODBC], conformance levels
- ODBC drivers [ODBC], conformance levels
ms.assetid: bb5d68cf-d238-481e-babc-2e9401b4700e
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 182b53071f5d7d4c3486a84f789954e12772e0bc
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32914255"
---
# <a name="function-conformance"></a>Funktion Konformität
In der folgenden Tabelle gibt an, dem Konformitätsgrad für jede ODBC-Funktion, in denen dies gut definiert ist.  
  
|Funktion|Konformitätsgrad|  
|--------------|-----------------------|  
|**SQLAllocHandle**|Core|  
|**SQLBindCol**|Core|  
|**SQLBindParameter**|Core [1]|  
|**SQLBrowseConnect**|Ebene 1|  
|**SQLBulkOperations**|Ebene 1|  
|**SQLCancel**|Core [1]|  
|**SQLCloseCursor**|Core|  
|**SQLColAttribute**|Core [1]|  
|**SQLColumnPrivileges**|Ebene 2|  
|**SQLColumns**|Core|  
|**SQLConnect**|Core|  
|**SQLCopyDesc**|Core|  
|**SQLDataSources**|Core|  
|**SQLDescribeCol**|Core [1]|  
|**SQLDescribeParam**|Ebene 2|  
|**SQLDisconnect**|Core|  
|**SQLDriverConnect**|Core|  
|**SQLDrivers**|Core|  
|**SQLEndTran**|Core [1]|  
|**SQLExecDirect**|Core|  
|**SQLExecute**|Core|  
|**SQLFetch**|Core|  
|**SQLFetchScroll**|Core [1]|  
|**SQLForeignKeys**|Ebene 2|  
|**SQLFreeHandle**|Core|  
|**SQLFreeStmt**|Core|  
|**SQLGetConnectAttr**|Core|  
|**SQLGetCursorName**|Core|  
|**SQLGetData**|Core|  
|**SQLGetDescField**|Core|  
|**SQLGetDescRec**|Core|  
|**SQLGetDiagField**|Core|  
|**SQLGetDiagRec**|Core|  
|**SQLGetEnvAttr**|Core|  
|**SQLGetFunctions**|Core|  
|**SQLGetInfo**|Core|  
|**SQLGetStmtAttr**|Core|  
|**SQLGetTypeInfo**|Core|  
|**SQLMoreResults**|Ebene 1|  
|**SQLNativeSql**|Core|  
|**SQLNumParams**|Core|  
|**SQLNumResultCols**|Core|  
|**SQLParamData**|Core|  
|**SQLPrepare**|Core|  
|**SQLPrimaryKeys**|Ebene 1|  
|**SQLProcedureColumns**|Ebene 1|  
|**SQLProcedures**|Ebene 1|  
|**SQLPutData**|Core|  
|**SQLRowCount**|Core|  
|**SQLSetConnectAttr**|Core [2]|  
|**SQLSetCursorName**|Core|  
|**SQLSetDescField**|Core [1]|  
|**SQLSetDescRec**|Core|  
|**SQLSetEnvAttr**|Core [2]|  
|**SQLSetPos**|Ebene 1 [1]|  
|**SQLSetStmtAttr**|Core [2]|  
|**SQLSpecialColumns**|Core [1]|  
|**SQLStatistics**|Core|  
|**SQLTablePrivileges**|Ebene 2|  
|**SQLTables**|Core|  
  
 [1] wichtige Features dieser Funktion sind nur zur höheren Übereinstimmungsebenen verfügbar.  
  
 [2] bestimmte Attribute auf benutzerdefinierte Werte festlegen, hängt von den Konformitätsgrad ab. Weitere Informationen finden Sie im nächsten Abschnitt [Attribut Konformität](../../../odbc/reference/develop-app/attribute-conformance.md).
