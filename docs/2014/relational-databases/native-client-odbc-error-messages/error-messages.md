---
title: Fehlermeldungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], types
- ODBC error handling, message types
- errors [ODBC], types
ms.assetid: 46c0c22e-d105-4d5b-bb9d-5694472e8651
caps.latest.revision: 33
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f3012d1e13de482dbcf173191bfd75dae9599b7c
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37421819"
---
# <a name="error-messages"></a>Fehlermeldungen
  Der Text, der von zurückgegebenen Meldungen der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber befindet sich der *MessageText* Parameter **SQLGetDiagRec**. Die Quelle eines Fehlers wird im Header der Meldung angegeben:  
  
 [Microsoft][ODBC-Treiber-Manager]  
 Diese Fehler werden vom ODBC-Treiber-Manager ausgelöst.  
  
 [Microsoft][ODBC-Cursorbibliothek]  
 Diese Fehler werden von der ODBC-Cursorbibliothek ausgelöst.  
  
 [Microsoft][SQL Server Native Client]  
 Diese Fehler werden erstellt, indem die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber. Wenn keine anderen Knoten entweder mit den Namen einer Netzwerkbibliothek oder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vorhanden sind, trat der Fehler im Treiber auf.  
  
 [Microsoft] [SQL Server Native Client] [*Net-Transportname*]  
 Diese Fehler werden erstellt, indem die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Netzwerkbibliothek, in denen *Net-Transportname* ist der Anzeigename des eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client-Netzwerktransports (z. B. Named Pipes, Shared Memory, TCP/IP-Sockets oder VIA). Die restliche Fehlermeldung enthält die aufgerufene Netzwerkbibliotheksfunktion und die von der TDS-Funktion in der zugrunde liegenden Netzwerk-API aufgerufene Funktion. Die *PfNative* mit diesen Fehlern zurückgegebene Fehlercode ist, den Fehlercode aus der zugrunde liegenden Netzwerkprotokollstapel.  
  
 [Microsoft][SQL Server Native Client][[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]  
 Diese Fehler werden von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgelöst. Die übrige Fehlermeldung entspricht dem Text der Fehlermeldung aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Die *PfNative* Code, die mit diesen Fehlern zurückgegebene ist die Fehlernummer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Weitere Informationen über eine Liste mit Fehlermeldungen (und ihren Nummern), die zurückgegeben werden kann [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], finden Sie unter der Beschreibung und den Fehlerspalten Spalten von der **Sysmessages** -Systemtabelle in der **master** Datenbank [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [Behandlung von Fehlern und Meldungen](handling-errors-and-messages.md)  
  
  
