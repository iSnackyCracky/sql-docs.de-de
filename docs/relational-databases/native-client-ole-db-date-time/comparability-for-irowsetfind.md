---
title: Vergleichbarkeit für ' irowsetfind ' | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: native-client-ole-db-date-time
ms.reviewer: ''
ms.suite: sql
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IRowsetFind comparability [ODBC]
ms.assetid: 7d148b56-9bbe-4e55-b31f-43f115705402
caps.latest.revision: 14
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: 5ed2021b5ee56c1fa9d3bc4dbae2d653b1c0bdc1
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39537010"
---
# <a name="comparability-for-irowsetfind"></a>Vergleichbarkeit für 'IRowsetFind'
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  Für die date/time-Typen unterstützt IRowsetFind die folgenden Vergleiche:  
  
-   LT  
  
-   LE  
  
-   EQ  
  
-   GE  
  
-   GT  
  
-   NE  
  
-   IGNORE  
  
 Bei dem Versuch eines anderen Vergleichs wird DB_E_BADCOMPAREOP zurückgegeben. Dieses Verhalten stimmt mit der OLE DB-Spezifikation überein.  
  
## <a name="see-also"></a>Siehe auch  
 [Date and Time Improvements &#40;OLE DB&#41; (Verbesserungen bei Datum und Uhrzeit &#40;OLE DB&#41;)](../../relational-databases/native-client-ole-db-date-time/date-and-time-improvements-ole-db.md)  
  
  
