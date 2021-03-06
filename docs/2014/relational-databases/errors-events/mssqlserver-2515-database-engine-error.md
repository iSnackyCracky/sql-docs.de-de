---
title: MSSQLSERVER_2515 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- 2515 (Database Engine error)
ms.assetid: af93aa29-70c9-4923-90af-aafadb20c1c6
caps.latest.revision: 21
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: a81cfe18d74dd6101825f1c88a6c6785a63b79f2
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37419949"
---
# <a name="mssqlserver2515"></a>MSSQLSERVER_2515
    
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|2515|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|DBCC_DIFF_MAP_OUT_OF_SYNC|  
|Meldungstext|Seite P_ID, Objekt-ID O_ID, Index-ID I_ID, Partitions-ID PN_ID, Zuordnungseinheits-ID A_ID (TYPE-Typ) wurde geändert, im differenziellen Sicherungsbitmuster jedoch nicht als geändert gekennzeichnet.|  
  
## <a name="explanation"></a>Erklärung  
 Die angegebene Seite verfügt über eine Protokollfolgenummer, die höher ist als die differenzielle Referenzprotokollfolgenummer im Sicherungs-Manager der Datenbank oder die differenzielle Basisprotokollfolgenummer im Dateikontrollblock der Datei, je nachdem, welche neuer ist. Die Seite ist jedoch im differenziellen Sicherungsbitmuster nicht als geändert markiert.  
  
 Es wird nur eine Seite pro Datenbank gemeldet, weil diese Prüfung nur vorgenommen wird, wenn das differenzielle Bitmuster als fehlerfrei bekannt ist.  
  
## <a name="user-action"></a>Benutzeraktion  
  
### <a name="look-for-hardware-failure"></a>Hardwarefehlersuche  
 Führen Sie eine Hardwarediagnose aus, und beheben Sie alle Probleme. Überprüfen Sie auch das Systemprotokoll und das Anwendungsprotokoll von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sowie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll, um festzustellen, ob der Fehler aufgrund eines Hardwarefehlers aufgetreten ist. Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.  
  
 Lagern Sie verschiedene Hardwarekomponenten aus, um das Problem zu isolieren, falls Beschädigungsprobleme bei permanenten Daten auftreten. Stellen Sie sicher, dass beim System der Schreibcache auf dem Datenträgercontroller nicht aktiviert ist. Wenden Sie sich an Ihren Hardwarehersteller, falls Sie beim Schreibcache das Problem vermuten.  
  
 Letztendlich kann es vorteilhaft sein, wenn Sie zu einem neuen Hardwaresystem wechseln. Der Wechsel kann die Neuformatierung der Laufwerke und eine Neuinstallation des Betriebssystems beinhalten.  
  
### <a name="restore-from-backup"></a>Sicherungswiederherstellung  
 Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.  
  
### <a name="run-dbcc-checkdb"></a>Ausführen von DBCC CHECKDB  
 Führen Sie DBCC CHECKDB ohne eine REPAIR-Klausel aus, um das Ausmaß der Beschädigung festzustellen, falls keine fehlerfreie Sicherung verfügbar ist. DBCC CHECKDB empfiehlt die Verwendung einer REPAIR-Klausel. Führen Sie dann DBCC CHECKDB mit der entsprechenden REPAIR-Klausel aus, um die Beschädigung zu reparieren.  
  
> [!CAUTION]  
>  Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.  
  
 Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.  
  
### <a name="results-of-running-repair-options"></a>Ergebnis der Ausführung von REPAIR-Optionen  
 Durch Ausführen von REPAIR wird das differenzielle Bitmuster ungültig. Sie können eine differenzielle Sicherung erst nach einer vollständigen Datenbanksicherung ausführen. Die vollständige Datenbanksicherung bietet eine Grundlage für die Neuerstellung des differenziellen Bitmusters.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md)   
 [MSSQLSERVER_2516](mssqlserver-2516-database-engine-error.md)  
  
  
