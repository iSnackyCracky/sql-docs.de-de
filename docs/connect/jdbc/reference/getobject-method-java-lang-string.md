---
title: GetObject-Methode (java.lang.String) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- SQLServerCallableStatement.getObject (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: a1e955ce-13db-4828-ad59-d9b6a8b2c6cc
caps.latest.revision: 14
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 82618a47bc45d9d204e7c37305289796e77e5a60
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32837265"
---
# <a name="getobject-method-javalangstring"></a>getObject-Methode (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Ruft den Wert des angegebenen Parameters unter Berücksichtigung des Parameternamens als Objekt in der Programmiersprache Java ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public java.lang.Object getObject(java.lang.String sCol)  
```  
  
#### <a name="parameters"></a>Parameter  
 *sCol*  
  
 Ein **Zeichenfolge** , die den Namen des Parameters enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein **Objekt** Wert.  
  
## <a name="exceptions"></a>Ausnahmen  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Hinweise  
 Diese GetObject-Methode wird von der GetObject-Methode in der java.sql.CallableStatement-Schnittstelle angegeben.  
  
 Von dieser Methode wird der Wert der angegebenen Spalte als Java-Objekt zurückgegeben. Beim Typ des Java-Objekts handelt es sich um den standardmäßigen Java-Objekttyp, der dem SQL-Typ der Spalte entspricht. Die Grundlage hierfür bildet die in der JDBC-Spezifikation angegebene Zuordnung für integrierte Typen. Bei einem SQL-NULL-Wert wird vom Treiber ein Java-NULL-Wert zurückgegeben.  
  
 Diese Methode kann auch zum Lesen datenbankspezifischer, abstrakter Datentypen verwendet werden. In der JDBC 2.0-API wird das Verhalten der GetObject-Methode erweitert, um Daten von SQL-benutzerdefinierte Typen zu materialisieren. Wenn eine Spalte einen strukturierten oder unterschiedlichen Wert enthält, wird das Verhalten dieser Methode ist, als handele es sich um einen Aufruf von `getObject(columnIndex, this.getStatement().getConnection().getTypeMap())`.  
  
 Ab der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] JDBC Driver 3.0:  
  
-   Ein Wert vom Typ **Datum** wird als java.sql.Date-Objekt zurückgegeben werden.  
  
-   Ein Wert vom Typ **Zeit** wird als java.sql.Time-Objekt zurückgegeben werden.  
  
-   Ein Wert vom Typ **datetime2** wird als java.sql.Timestamp-Objekt zurückgegeben werden.  
  
-   Ein Wert vom Typ **"DateTimeOffset"** wird als microsoft.sql.DateTimeOffset-Objekt zurückgegeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [GetObject-Methode &#40;SQLServerCallableStatement&#41;](../../../connect/jdbc/reference/getobject-method-sqlservercallablestatement.md)   
 [SQLServerCallableStatement-Elemente](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [SQLServerCallableStatement-Klasse](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
