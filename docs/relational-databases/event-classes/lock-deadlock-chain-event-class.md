---
title: Lock:Deadlock Chain (Ereignisklasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Deadlock Chain event class
ms.assetid: 9883127b-aa34-4235-88cc-c161cd2112cc
caps.latest.revision: 35
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: db5a4b43cfed4523af9a56df5a709ce8de0d46a6
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39565214"
---
# <a name="lockdeadlock-chain-event-class"></a>Lock:Deadlock Chain (Ereignisklasse)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  Die Lock:Deadlock Chain-Ereignisklasse wird für jeden an einem Deadlock Beteiligten erstellt.  
  
 Verwenden Sie die Lock:Deadlock Chain-Ereignisklasse, um zu überwachen, wann Deadlockbedingungen auftreten. Diese Informationen sind nützlich, wenn ermittelt werden soll, ob Deadlocks eine deutliche Auswirkung auf die Leistung der Anwendung haben und welche Objekte daran beteiligt sind. Sie können den Anwendungscode, der diese Objekte ändert, untersuchen, um festzustellen, ob die Deadlocks durch Änderungen minimiert werden können.  
  
## <a name="lockdeadlock-chain-event-class-data-columns"></a>Datenspalten der Lock:Deadlock Chain-Ereignisklasse  
  
|Datenspaltenname|Datentyp|und Beschreibung|Column ID|Filterbar|  
|----------------------|---------------|-----------------|---------------|----------------|  
|BinaryData|**image**|ID der LOCK-Ressource.|2|Benutzerkontensteuerung|  
|DatabaseID|**int**|ID der Datenbank, zu der diese Ressource gehört. [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] zeigt den Namen der Datenbank an, wenn die ServerName-Datenspalte in der Ablaufverfolgung aufgezeichnet wird und der Server verfügbar ist. Der Wert für eine Datenbank kann mithilfe der DB_ID-Funktion ermittelt werden.|3|Benutzerkontensteuerung|  
|DatabaseName|**nvarchar**|Name der Datenbank, zu der die Ressource gehört.|35|Benutzerkontensteuerung|  
|EventClass|**int**|Ereignistyp = 59.|27|nein|  
|EventSequence|**int**|Sequenz eines bestimmten Ereignisses innerhalb der Anforderung.|51|nein|  
|EventSubClass|**int**|Der Typ der Ereignisunterklasse.<br /><br /> 101 = Lock-Ressourcentyp<br /><br /> 102 = Exchange-Ressourcentyp|21|Benutzerkontensteuerung|  
|IntegerData|**int**|Deadlocknummer. Die Nummern werden beginnend mit 0 zugewiesen, wenn der Server gestartet wird, und werden bei jedem Deadlock erhöht.|25|Benutzerkontensteuerung|  
|IntegerData2|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|55|Benutzerkontensteuerung|  
|IsSystem|**int**|Gibt an, ob das Ereignis bei einem Systemprozess oder einem Benutzerprozess aufgetreten ist. 1 = System, 0 = Benutzer.|60|Benutzerkontensteuerung|  
|LoginSid|**image**|Sicherheits-ID (SID) des angemeldeten Benutzers. Diese Informationen finden Sie in der sys.server_principals-Katalogsicht. Die SID ist für jede Anmeldung beim Server eindeutig.|41|Benutzerkontensteuerung|  
|Mode|**int**|0 = NULL - Kompatibel mit allen anderen Sperrmodi (LCK_M_NL)<br /><br /> 1 = Schemastabilitätssperre (LCK_M_SCH_S)<br /><br /> 2 = Schemaänderungssperre (LCK_M_SCH_M)<br /><br /> 3 = Freigegebene Sperre (LCK_M_S)<br /><br /> 4 = Updatesperre (LCK_M_U)<br /><br /> 5 = Exklusive Sperre (LCK_M_X)<br /><br /> 6 = Beabsichtigte freigegebene Sperre (LCK_M_IS)<br /><br /> 7 = Beabsichtigte Updatesperre (LCK_M_IU)<br /><br /> 8 = Beabsichtigte exklusive Sperre (LCK_M_IX)<br /><br /> 9 = Freigegebene Sperre mit beabsichtigter Updatesperre (LCK_M_SIU)<br /><br /> 10 = Freigegebene Sperre mit beabsichtigter exklusiver Sperre (LCK_M_SIX)<br /><br /> 11 = Updatesperre mit beabsichtigter exklusiver Sperre (LCK_M_UIX)<br /><br /> 12 = Massenupdatesperre (LCK_M_BU)<br /><br /> 13 = Freigegebene Sperren für Schlüsselbereich und Ressource (LCK_M_RS_S)<br /><br /> 14 = Freigegebene Sperre für Schlüsselbereich und Updatesperre für Ressource (LCK_M_RS_U)<br /><br /> 15 = Einfügungssperre für Schlüsselbereich und NULL-Sperre für Ressource (LCK_M_RI_NL)<br /><br /> 16 = Einfügungssperre für Schlüsselbereich und freigegebene Ressourcensperre (LCK_M_RI_S)<br /><br /> 17 = Einfügungssperre für Schlüsselbereich und Updatesperre (LCK_M_RI_U)<br /><br /> 18 = Einfügungssperre für Schlüsselbereich und exklusive Ressourcensperre (LCK_M_RI_X)<br /><br /> 19 = Exklusive Sperren für Schlüsselbereich und freigegebene Ressource (LCK_M_RX_S)<br /><br /> 20 = Exklusive Sperren für Schlüsselbereich und Update (LCK_M_RX_U)<br /><br /> 21 = Exklusive Sperren für Schlüsselbereich und Ressource (LCK_M_RX_X)|32|Benutzerkontensteuerung|  
|ObjectID|**int**|ID des gesperrten Objekts, soweit verfügbar und anwendbar.|22|Benutzerkontensteuerung|  
|ObjectID2|**bigint**|Die ID des verbundenen Objekts bzw. der verbundenen Entität, soweit verfügbar und anwendbar.|56|Benutzerkontensteuerung|  
|OwnerID|**int**|1 = TRANSACTION<br /><br /> 2 = CURSOR<br /><br /> 3 = SESSION<br /><br /> 4 = SHARED_TRANSACTION_WORKSPACE<br /><br /> 5 = EXCLUSIVE_TRANSACTION_WORKSPACE|58|Benutzerkontensteuerung|  
|RequestID|**int**|Die ID der Anforderung, die die Anweisung enthält.|49|Benutzerkontensteuerung|  
|ServerName|**nvarchar**|Name der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz, für die eine Ablaufverfolgung ausgeführt wird.|26|nein|  
|SessionLoginName|**nvarchar**|Der Anmeldename des Benutzers, der die Sitzung gestartet hat. Wenn Sie beispielsweise mithilfe von Login1 eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen und eine Anweisung als Login2 ausführen, zeigt SessionLoginName den Wert Login1 an und LoginName den Wert Login2. Diese Spalte zeigt die Windows-Anmeldenamen für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und [!INCLUDE[msCoName](../../includes/msconame-md.md)] an.|64|Benutzerkontensteuerung|  
|SPID|**int**|Die ID der Sitzung, in der das Ereignis aufgetreten ist.|12|Benutzerkontensteuerung|  
|StartTime|**datetime**|Zeitpunkt, zu dem das Ereignis begonnen hat (falls vorhanden).|14|Benutzerkontensteuerung|  
|TextData|**ntext**|Vom Ressourcentyp abhängiger Textwert.|1|Benutzerkontensteuerung|  
|TransactionID|**bigint**|Die vom System zugewiesene ID der Transaktion.|4|Benutzerkontensteuerung|  
|Typ|**int**|1 = NULL_RESOURCE<br /><br /> 2 = DATABASE<br /><br /> 3 = FILE<br /><br /> 5 = OBJECT<br /><br /> 6 = PAGE<br /><br /> 7 = KEY<br /><br /> 8 = EXTENT<br /><br /> 9 = RID<br /><br /> 10 = APPLICATION<br /><br /> 11 = METADATA<br /><br /> 12 = AUTONAMEDB<br /><br /> 13 = HOBT<br /><br /> 14 = ALLOCATION_UNIT|57|Benutzerkontensteuerung|  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [sp_trace_setevent &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql.md)   
 [sys.dm_tran_locks &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql.md)  
  
  
