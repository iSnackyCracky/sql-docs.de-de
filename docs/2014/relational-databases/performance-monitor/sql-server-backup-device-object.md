---
title: SQL Server, Sicherungsmedium-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:Backup Device
- Backup Device object
ms.assetid: 52e7febf-d5e0-4674-945b-aacc40a9ad6e
caps.latest.revision: 18
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: ec64b929da7e8e6be90f2b99b93b18adc89ce932
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37329420"
---
# <a name="sql-server-backup-device-object"></a>SQL Server, Sicherungsmedium-Objekt
  Das **Sicherungsmedium** -Objekt stellt Leistungsindikatoren bereit, die mit denen für Sicherungs- und Wiederherstellungsvorgänge verwendeten Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherungsmedien überwacht werden können. Überwachen Sie Sicherungsmedien, wenn Sie den Durchsatz oder den Fortschritt und die Leistung der Sicherungs- und Wiederherstellungsvorgänge auf jedem Medium einzeln bestimmen möchten. Wenn Sie den Durchsatz des gesamten Sicherungs- oder Wiederherstellungsvorgangs der Datenbank überwachen möchten, sollten Sie den **Sicherungs-/Wiederherstellungsdurchsatz/Sekunde** -Leistungsindikator des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Databases** object. Weitere Informationen finden Sie unter [SQL Server, Databases Object](sql-server-databases-object.md).  
  
 In dieser Tabelle wird der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Sicherungsmedium** beschrieben.  
  
|Sicherungsmedium-Leistungsindikatoren von SQL Server|Description|  
|---------------------------------------|-----------------|  
|**Mediumsdurchsatz Bytes/Sekunde**|Durchsatz von Lese-/Schreibvorgängen für ein Sicherungsmedium. Dieser Leistungsindikator ist nur vorhanden, während der Sicherungs- oder Wiederherstellungsvorgang ausgeführt wird.|  
  
## <a name="see-also"></a>Siehe auch  
 [Sicherungsmedien &#40;SQL Server&#41;](../backup-restore/backup-devices-sql-server.md)   
 [Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;](monitor-resource-usage-system-monitor.md)  
  
  
