---
title: SQLSetEnvAttr | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/16/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
apitype: DLLExport
helpviewer_keywords:
- SQLSetEnvAttr function
ms.assetid: d4114571-feca-4330-b2e4-7bfd1050b812
caps.latest.revision: 32
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: 570b70f0616fa7627b56ef196cba7983630bedf3
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39547690"
---
# <a name="sqlsetenvattr"></a>SQLSetEnvAttr
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  Die [ODBC Programmer's Reference](http://go.microsoft.com/fwlink/?LinkId=45250) definiert, wie ODBC-Treiber die **SQLSetEnvAttr** -Attributspezifikationen aus Anwendungen interpretieren sollen, die in die ODBC 2.*x* - oder ODBC 3.*x* -API geschrieben wurden. Der ODBC-Treiber von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Native Client entspricht diesen Regeln.  
  
 Eines der Attribute ist, das von **SQLSetEnvAttr** gesteuert wird, bestimmt, ob Verbindungspooling verwendet werden soll. Wenn Verbindungspooling mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber verwendet wird, muss für den *DriverCompletion* -Parameter SQL_DRIVER_NOPROMPT festgelegt werden, wenn eine Verbindung mit [SQLDriverConnect](../../relational-databases/native-client-odbc-api/sqldriverconnect.md) oder **SQLConnect**hergestellt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [SQLSetEnvAttr-Funktion](http://go.microsoft.com/fwlink/?LinkId=59369)   
 [ODBC-API-Implementierungsdetails](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
