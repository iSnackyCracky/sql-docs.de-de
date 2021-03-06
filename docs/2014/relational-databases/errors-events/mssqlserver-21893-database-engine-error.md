---
title: MSSQLSERVER_21893 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- 21893 (Database Engine error)
ms.assetid: 1ab1195a-fe2a-4e06-b871-b177b6bea1fe
caps.latest.revision: 7
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 7160179d5a2253cc0f42215c70cf1d4b1a814852
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37407609"
---
# <a name="mssqlserver21893"></a>MSSQLSERVER_21893
    
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|21893|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|SQLErrorNum21893|  
|Meldungstext|Die Abonnenten (%s) des ursprünglichen Verlegers '%s' werden bei dem umgeleitetem Verleger '%s' nicht als Remoteserver angezeigt. Führen Sie `sp_addlinkedserver` auf dem umgeleiteten Verleger aus, um diese Abonnenten als Remoteserver hinzuzufügen.|  
  
## <a name="explanation"></a>Erklärung  
 `sp_validate_redirected_publisher` verwendet die abonnementmetadatentabellen von der Verlegerdatenbank beim Remoteserver ab, um seine zugeordneten Abonnenten zu identifizieren, und stellt sicher, dass in "Master.dbo.sysservers" für die Abonnenten zugehörige Einträge vorliegen. Dieser Fehler wird zurückgegeben, wenn einer der identifizierten Abonnenten nicht vorhanden ist.  
  
 Dies wird jedoch nicht als schwerwiegender Fehler angesehen. Agents, in denen dieser Fehler auftritt, protokollieren den Fehler als Information, werden aber nicht beendet, da sich das Nichtvorhandensein entsprechender Abonnenteneinträge beim neuen Verleger nur beschränkt auf die Replikation auswirkt. Ohne einen entsprechenden Eintrag für einen Abonnenten in „sysservers“ schlagen einige Abonnementverwaltungsaktivitäten möglicherweise fehl, wenn sie über [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ausgeführt werden. Diese gleichen Aktivitäten können jedoch erfolgreich ausgeführt werden, indem die gespeicherten Verwaltungsprozeduren explizit ausgeführt werden.  
  
## <a name="user-action"></a>Benutzeraktion  
 Führen Sie `sp_addlinkedserver` für jeden identifizierten Abonnenten auf dem umgeleiteten Verleger aus, um diese Abonnenten als Remoteserver hinzuzufügen. Führen Sie dann `sp_serveroption` aus, um das Abonnentenbit für den Server festzulegen.  
  
  
