---
title: MSSQLSERVER_9790 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 9790 (Database Engine error)
ms.assetid: 83fd379f-5deb-4f97-8cb4-282e3d3fed94
caps.latest.revision: 13
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 84e445191cb6b4783d46bb0ec67f71bda93e1a58
ms.sourcegitcommit: ee661730fb695774b9c483c3dd0a6c314e17ddf8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2018
ms.locfileid: "34324851"
---
# <a name="mssqlserver9790"></a>MSSQLSERVER_9790
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|9790|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|SB3_XMIT_ERROR_ENTRANCE_BROKER_SINGLE_USER|  
|Meldungstext|Die eingehende Nachricht kann nicht geroutet werden. Die MSDB-Systemdatenbank, die Routinginformationen enthält, befindet sich im Einzelbenutzermodus.|  
  
## <a name="explanation"></a>Erklärung  
Beim Klassifizieren einer empfangenen Nachricht ist ein Fehler aufgetreten, da die MSDB-Datenbank im SINGLE USER-Modus war.  
  
## <a name="user-action"></a>Benutzeraktion  
Ändern Sie die MSDB-Datenbank mit dem Befehl ALTER DATABASE auf den MULTI USER-Modus.  
  
