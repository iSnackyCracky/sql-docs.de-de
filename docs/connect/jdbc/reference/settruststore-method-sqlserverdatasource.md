---
title: setTrustStore-Methode (SQLServerDataSource)
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
- setTrustStore Method (SQLServerDataSource)
apilocation:
- setTrustStore Method (SQLServerDataSource)
apitype: Assembly
ms.assetid: bab5485d-4547-426c-adbe-44e2b5702d1d
caps.latest.revision: 15
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: cf5d6034fbf2e9ce9d1c1b58909146dbcf56f0c6
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MTE75
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38042280"
---
# <a name="settruststore-method-sqlserverdatasource"></a>setTrustStore-Methode (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Legt den Pfad (einschließlich Dateiname) zur trustStore-Zertifikatsdatei fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public void setTrustStore(java.lang.String trustStore)  
```  
  
#### <a name="parameters"></a>Parameter  
 *trustStore*  
  
 Eine **Zeichenfolge** mit dem Pfad (einschließlich des Dateinamens) der trustStore-Zertifikatsdatei.  
  
## <a name="remarks"></a>Remarks  
 Ist die trustStore-Eigenschaft nicht angegeben oder auf NULL festgelegt, wird der zu verwendende Zertifikatspeicher von [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] mithilfe der Suchregeln der Trust-Manager-Factory ermittelt. Die Vertrauenswürdigkeitsinformationen werden von der SunX509-Standardklasse „TrustManagerFactory“ an folgenden Speicherorten und in der folgenden Reihenfolge gesucht:  
  
-   1. Eine von der Java Virtual Machine (JVM)-Systemeigenschaft "javax.net.ssl.trustStore" angegebene Datei  
  
-   2. "\<Java-Home >/Lib/Security/Jssecacerts" Datei.  
  
-   3. "\<Java-Home >/Lib/Security/Cacerts" Datei.  
  
 Weitere Informationen finden Sie in der Dokumentation zur SunX509 TrustManager-Schnittstelle auf der Website von Sun Microsystems.  
  
 Ist die trustStore-Eigenschaft auf eine Zeichenfolge oder auf eine leere Zeichenfolge ("") festgelegt, wird die trustStore-Datei anhand dieses Werts gesucht, um das SSL-Zertifikat des Servers zu überprüfen.  
  
 Die trustStorePassword-Eigenschaft kann zusammen mit der trustStore-Eigenschaft angegeben werden, und deren Wert wird zum Öffnen der trustStore-Datei verwendet. Weitere Informationen finden Sie unter [setTrustStorePassword](../../../connect/jdbc/reference/settruststorepassword-method-sqlserverdatasource.md).  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [SQLServerDataSource-Elemente](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource-Klasse](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
