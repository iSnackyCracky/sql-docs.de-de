---
title: FT:Crawl Stopped-Ereignisklasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Crawl Stopped event class
ms.assetid: dbc91bf7-687c-4083-9694-02f3e102c175
caps.latest.revision: 29
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: 13a49f74d9a795e453ab2841a01ac99e5eb55416
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39557980"
---
# <a name="ftcrawl-stopped-event-class"></a>FT:Crawl Stopped-Ereignisklasse
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  Die **:Crawl Stopped** -Ereignisklasse zeigt an, dass eine Volltextdurchforstung (Auffüllung) beendet wurde. Die Beendigung kann aus einem erfolgreichen Abschließen der Durchforstung oder aus einem schwerwiegenden Fehler erfolgen.  
  
## <a name="ftcrawl-stopped-event-class-data-columns"></a>Datenspalten der FT:Crawl Stopped-Ereignisklasse  
  
|Datenspaltenname|Datentyp|und Beschreibung|Column ID|Filterbar|  
|----------------------|---------------|-----------------|---------------|----------------|  
|**DatabaseID**|**int**|Die ID der Datenbank, in der die Volltextdurchforstung beendet wurde. Der Wert für eine Datenbank kann mithilfe der DB_ID-Funktion ermittelt werden.|3|Benutzerkontensteuerung|  
|**EventClass**|**int**|Ereignistyp = 156.|27|nein|  
|**EventSequence**|**int**|Sequenz eines bestimmten Ereignisses innerhalb der Anforderung.|51|nein|  
|**IsSystem**|**int**|Gibt an, ob das Ereignis bei einem Systemprozess oder einem Benutzerprozess aufgetreten ist. 1 = System, 0 = Benutzer.|60|Benutzerkontensteuerung|  
|**ObjectID**|**int**|Vom System zugewiesene ID des Objekts. Die Volltextdurchforstung wurde für den Volltextindex in diesem Objekt beendet.|22|Benutzerkontensteuerung|  
|**SessionLoginName**|**nvarchar**|Der Anmeldename des Benutzers, der die Sitzung gestartet hat. Wenn Sie z. B. mit Login1 eine Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen und mit Login2 eine Anweisung ausführen, zeigt **SessionLoginName** Login1 an, und **LoginName** zeigt Login2 an. Diese Spalte zeigt die Windows-Anmeldenamen für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und [!INCLUDE[msCoName](../../includes/msconame-md.md)] an.|64|Benutzerkontensteuerung|  
|**SPID**|**int**|Die ID der Sitzung, in der das Ereignis aufgetreten ist.|12|Benutzerkontensteuerung|  
|**StartTime**|**datetime**|Zeitpunkt, zu dem das Ereignis begonnen hat (falls vorhanden).|14|Benutzerkontensteuerung|  
|**TransactionID**|**bigint**|Die vom System zugewiesene ID der Transaktion.|4|Benutzerkontensteuerung|  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [sp_trace_setevent &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql.md)  
  
  
