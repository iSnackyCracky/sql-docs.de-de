---
title: SQL Server-Agent-Eigenschaften (Seite Erweitert)|Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.advanced.f1
ms.assetid: a4d798ee-4c18-40d4-b6af-63d17503738c
caps.latest.revision: 16
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 3825ba87f9012a7dcc33fb8585a2d2c4f83e9d6e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37328840"
---
# <a name="sql-server-agent-properties-advanced-page"></a>SQL Server-Agent-Eigenschaften (Seite Erweitert)
  Mithilfe dieser Seite können Sie die erweiterten Eigenschaften des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Diensts anzeigen und ändern.  
  
## <a name="options"></a>Tastatur  
 **SQL Server-Ereignisweiterleitung**  
 Durch die Optionen in dieser Kategorie wird die Ereignisweiterleitung aktiviert und konfiguriert.  
  
 **Ereignisse an anderen Server weiterleiten**  
 Leitet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Ereignisse an einen anderen Server weiter.  
  
 **Server**  
 Wählen Sie den Namen des Servers aus, an den Ereignisse weitergeleitet werden sollen.  
  
 **Ereignisse ohne Behandlung**  
 Leitet nur Ereignisse ohne Behandlung an den angegebenen Server weiter. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent leitet nur Ereignisse weiter, auf die keine Warnung reagiert.  
  
 **Alle Ereignisse**  
 Leitet alle Ereignisse weiter. Wenn eine Warnung in der lokalen Instanz auf das Ereignis reagiert, leitet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] das Ereignis weiter und verarbeitet auch die Warnung.  
  
 **Bei diesem Schweregrad des Ereignisses oder darüber**  
 Leitet nur Ereignisse weiter, deren Schweregrad der angegebenen Ebene entspricht oder darüber liegt.  
  
 **Bedingung für 'CPU im Leerlauf'**  
 Durch die Optionen in dieser Kategorie werden die Bedingungen definiert, unter denen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Aufträge ausführt, für die CPU-Leerlaufzeitpläne festgelegt sind.  
  
 **Bedingung für 'CPU im Leerlauf' definieren**  
 Definiert die Bedingungen, unter denen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent die CPU als im Leerlauf befindlich betrachtet.  
  
 **bei durchschnittlicher CPU-Nutzung unter**  
 Prozentualer Wert der CPU-Nutzung, unter dem die CPU als im Leerlauf befindlich betrachtet wird.  
  
 **und Verbleiben unterhalb dieser Stufe für**  
 Die Zeitspanne, für die die durchschnittliche CPU-Nutzung unterhalb des angegebenen Wertes liegen muss, bevor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Aufträge dem CPU-Leerlaufzeitplan entsprechend ausführt.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen und Zuweisen von Zeitplänen zu Aufträgen](create-and-attach-schedules-to-jobs.md)   
 [Verwalten von Ereignissen](manage-events.md)  
  
  
