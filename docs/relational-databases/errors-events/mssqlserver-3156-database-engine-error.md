---
title: MSSQLSERVER_3156 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 3156 (Database Engine error)
ms.assetid: 345d8ed4-177e-4ec3-bab3-25d30000e323
caps.latest.revision: 12
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 76dd17b4d914b63399881049e0af50172cc49983
ms.sourcegitcommit: ee661730fb695774b9c483c3dd0a6c314e17ddf8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2018
ms.locfileid: "34320391"
---
# <a name="mssqlserver3156"></a>MSSQLSERVER_3156
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|Ereignis-ID|3156|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|LDDB_CANT_WRITE|  
|Meldungstext|Die Datei '%ls' kann nicht in '%ls' wiederhergestellt werden. Verwenden Sie WITH MOVE, um einen gültigen Speicherort für die Datei zu identifizieren.|  
  
## <a name="explanation"></a>Erklärung  
Mit dieser allgemeinen Meldung werden die logischen oder physischen Dateinamen der Dateien angegeben, die aufgrund eines Problems mit dem angegebenen Speicherort nicht wiederhergestellt werden konnten.  
  
### <a name="possible-causes"></a>Mögliche Ursachen  
Die folgenden Ursachen sind möglich:  
  
-   Möglicherweise müssen Sie auf das angegebene Windows-Verzeichnis zugreifen.  
  
-   Möglicherweise haben Sie den Pfad falsch eingegeben, oder Sie haben einen Pfad angegeben, der nicht vorhanden ist.  
  
-   Der Dateiname wird möglicherweise für eine Datei verwendet, die nicht überschrieben werden kann.  
  
## <a name="user-action"></a>Benutzeraktion  
Suchen Sie in den Fehlerprotokollen nach anderen Meldungen, in denen weitere Details angegeben werden.  
  
Beheben Sie das Problem mit dem angegebenen Speicherort beispielsweise durch das Gewähren von Zugriff, oder verwenden Sie die Option WITH MOVE in Ihrer RESTORE-Anweisung, um die Datei zu verschieben.  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
[Wiederherstellen einer Datenbank an einem neuen Speicherort &#40;SQL Server&#41;](~/relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md)  
[Wiederherstellen von Dateien an einem neuen Speicherort &#40;SQL Server&#41;](~/relational-databases/backup-restore/restore-files-to-a-new-location-sql-server.md)  
[RESTORE &#40;Transact-SQL&#41;](~/t-sql/statements/restore-statements-transact-sql.md)  
  
