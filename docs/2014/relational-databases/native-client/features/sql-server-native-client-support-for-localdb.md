---
title: SQL Server Native Client-Unterstützung für LocalDB | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 127569d1-a9f7-49bf-a561-c084986a8871
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 1da6a606a8a79aa96cff1cd9b51dd234fe729b94
ms.sourcegitcommit: 79d4dc820767f7836720ce26a61097ba5a5f23f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2018
ms.locfileid: "40393649"
---
# <a name="sql-server-native-client-support-for-localdb"></a>SQL Server Native Client-Unterstützung für LocalDB
  Ab [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]ist eine vereinfachte Version von SQL Server mit dem Namen LocalDB verfügbar. In diesem Thema wird erläutert, wie in einer LocalDB-Instanz eine Verbindung mit einer Datenbank hergestellt wird.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu LocalDB, einschließlich der Installation von LocalDB und der Konfiguration der LocalDB-Instanz, finden Sie unter:  
  
-   [SQL Server Express LocalDB-Verweis](../../sql-server-express-localdb-reference.md)  
  
-   [SQL Server 2014 Express LocalDB](../../../database-engine/configure-windows/sql-server-2016-express-localdb.md)  
  
 Zusammenfassend erlaubt LocalDB Ihnen Folgendes:  
  
-   Verwenden Sie `sqllocaldb.exe i`, um den Namen der Standardinstanz zu ermitteln.  
  
-   Verwenden der `AttachDBFilename` Schlüsselwort für Verbindungszeichenfolgen angeben, welche Datenbankdatei der Server anfügen soll. Bei Verwendung `AttachDBFilename`, wenn Sie nicht den Namen der Datenbank mit angeben der **Datenbank** Schlüsselwort für Verbindungszeichenfolgen, die Datenbank wird aus der LocalDB-Instanz entfernt werden, wenn die Anwendung geschlossen wird.  
  
-   Geben Sie in der Verbindungszeichenfolge eine LocalDB-Instanz an:  
  
```  
SERVER=(localdb)\v11.0  
```  
  
 Falls notwendig können Sie eine LocalDB-Instanz mit "sqllocaldb.exe" erstellen. Sie können auch "sqlcmd.exe" verwenden, um Datenbanken in einer LocalDB-Instanz hinzuzufügen und zu ändern. Beispiel: `sqlcmd -S (localdb)\v11.0`.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server Native Client-Features](sql-server-native-client-features.md)  
  
  
