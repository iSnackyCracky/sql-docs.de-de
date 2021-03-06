---
title: SQLServerCallableStatement-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 30710a63-c05d-47d9-9cf9-c087a1c76373
caps.latest.revision: 20
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b3813574070c53f16cd04ff262d7134c87d4ea85
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32846295"
---
# <a name="sqlservercallablestatement-class"></a>SQLServerCallableStatement-Klasse
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Mit dieser Klasse kann der gespeicherte Prozedurname angegeben werden, der mit Eingabe- und Ausgabeparametern aufgerufen wird. Mit dieser Klasse kann der Rückgabestatus mit der Syntax "? = call( ?, ..)" abgerufen werden.  
  
 **Paket:** com.microsoft.sqlserver.jdbc  
  
 **Implementiert:** [ISQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
 **Erweitert:** [sqlserverpreparedstatement-Klasse](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public final class SQLServerCallableStatement  
```  
  
## <a name="remarks"></a>Hinweise  
 SQLServerCallableStatement können Sie den Namen der gespeicherten Prozedur aufrufen, zusammen mit Eingabe-und Ausgabeparameter angeben. SQLServerCallableStatement bietet auch die Möglichkeit zum Abrufen des Werts der Rückgabestatus mit der `? = call( ?, ..)` Syntax.  
  
 Diese Klasse unterstützt das Entpacken in die SQLServerCallableStatement-Klasse, ISQLServerCallableStatement-Schnittstelle, java.sql.CallableStatement-Schnittstelle, und die Klassen und Schnittstellen, die von SQLServerPreparedStatement für das Entpacken unterstützt werden. Weitere Informationen finden Sie unter [Wrapper und Schnittstellen](../../../connect/jdbc/wrappers-and-interfaces.md).  
  
 Wenn eines der SQLServerCallableStatement Methoden festlegen für einen Typ aufgerufen wird, wenn dieses Typs von Konflikten mit den angegebenen Typ [RegisterOutParameter](../../../connect/jdbc/reference/registeroutparameter-method-sqlservercallablestatement.md), mit der letzten Set-Methode der SQLServerCallableStatement verwendet wird. Dies kann jedoch zu Konvertierungsfehlern aufgrund von inkompatiblen Datentypen führen. Wenn ein SQLServerCallableStatement-Methode festlegen, wird nicht aufgerufen, mit dem ersten angegebenen Typs [RegisterOutParameter](../../../connect/jdbc/reference/registeroutparameter-method-sqlservercallablestatement.md) Aufruf wird verwendet.  
  
 Die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] JDBC Driver 3.0 ist kompatibel mit der JDBC 4.0-Empfehlung, die ein Resultset und updatezählungen abgerufen werden müssen, bevor Out-Parameter. Sollten OUT-Parameter vor Abschluss der Verarbeitung des Resultsets und der Updatezählungen abgerufen werden, gehen alle noch nicht verarbeiteten Resultsets und Updatezählungen verloren.  
  
## <a name="see-also"></a>Siehe auch  
 [SQLServerCallableStatement-Elemente](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [API-Referenz für JDBC-Treiber](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
