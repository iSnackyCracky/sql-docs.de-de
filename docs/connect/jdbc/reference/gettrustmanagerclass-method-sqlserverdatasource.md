---
title: GetTrustManagerClass-Methode (SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- SQLServerDataSource.getTrustManagerClass
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: ''
caps.latest.revision: 1
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: af45b8bc98888e2c87eb75569fe2417a7d33abc3
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="gettrustmanagerclass-method-sqlserverdatasource"></a>GetTrustManagerClass-Methode (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Gibt den Zeichenfolgenwert der TrustManagerClass Verbindungseigenschaft zurück.
  
## <a name="syntax"></a>Syntax  
  
```  
  
public java.lang.String getTrustManagerClass()  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein **Zeichenfolge** , den Wert der Verbindungseigenschaft TrustManagerClass oder Null enthält, wenn kein Wert festgelegt ist.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die TrustManagerClass-Eigenschaft nicht festgelegt ist, die [GetTrustManagerClass](../../../connect/jdbc/reference/gettrustmanagerclass-method-sqlserverdatasource.md) Methode gibt null zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [SQLServerDataSource-Elemente](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource-Klasse](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
