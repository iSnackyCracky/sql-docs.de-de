---
title: "srv_rpcoptions (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: extended-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: reference
apiname: srv_rpcoptions
apilocation: opends60.dll
apitype: DLLExport
dev_langs: C++
helpviewer_keywords: srv_rpcoptions
ms.assetid: dbcce5d1-d5a1-4379-9597-04e43af5923d
caps.latest.revision: "30"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 2d180eb5082b85df82d0cbd141d48493c41de286
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="srvrpcoptions-extended-stored-procedure-api"></a>srv_rpcoptions (API für erweiterte gespeicherte Prozeduren)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Verwenden Sie stattdessen die CLR-Integration.  
  
 Gibt die Laufzeitoptionen für die derzeit remote gespeicherte Prozedur zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
DBUSMALLINT srv_rpcoptions ( SRV_PROC *  
srvproc   
);  
```  
  
## <a name="arguments"></a>Argumente  
 *srvproc*   
 Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das die remote gespeicherte Prozedur erhalten hat). Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Daten und Kommunikation zwischen der Anwendung und dem Client verwaltet.  
  
## <a name="returns"></a>Rückgabewert  
 Eine Bitmap mit den in einer logischen Darstellung ODER für die derzeit remote gespeicherte Prozedur verbundenen Laufzeitflags. Wenn keine aktuelle remote gespeicherte Prozedur vorhanden ist, wird 0 zurückgegeben und eine Meldung generiert.  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Tabelle werden die einzelnen Laufzeitflags beschrieben.  
  
|Laufzeitflag|Description|  
|--------------------|-----------------|  
|SRV_NOMETADATA|Der Client hat Ergebnisse ohne Metadateninformationen angefordert. Dieses Flag wird nur verwendet, wenn der Client mit einer Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kommuniziert. Eine Anwendung der API für erweiterte gespeicherte Prozeduren kann Metadateninformationen nicht auslassen.|  
|SRV_RECOMPILE|Der Client hat vor der Ausführung der remote gespeicherten Prozedur eine erneute Kompilierung angefordert. Dieses Flag gilt möglicherweise nicht für eine Anwendung der API für erweiterte gespeicherte Prozeduren.|  
  
> [!IMPORTANT]  
>  Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren. Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
  