---
title: Sicherungszeitachse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: backup-restore
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.POINTINTIMERESTORE.F1
- sql12.swb.backuptimeline.f1
helpviewer_keywords:
- Backup Timeline
ms.assetid: ae3565f2-ddb2-4469-a992-7531d4f9ebb8
caps.latest.revision: 23
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 5e0e93e56e0ba2dc2f6b6c435085ee8d370d2cd3
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37322360"
---
# <a name="backup-timeline"></a>Sicherungszeitachse
  Verwenden Sie das Dialogfeld **Sicherungszeitachse** , um Sicherungen zum Wiederherstellen einer Datenbank entsprechend einem bestimmten Zeitpunkt zu suchen und anzugeben. Auf das Dialogfeld **Sicherungszeitachse** greifen Sie zu, indem Sie im Bereich **Datenbank wiederherstellen (Seite „Allgemein“)** auf **Zeitachse** klicken. In diesem Dialogfeld können Sie eine Zeitachse der für die Datenbank ausgeführten Wiederherstellungsvorgänge anzeigen.  
  
 Der Datenbankwiederherstellungsberater stellt sicher, dass nur Sicherungen ausgewählt werden, die für die Wiederherstellung auf diesen Zeitpunkt benötigt werden. Die ausgewählten Sicherungen machen den empfohlenen Wiederherstellungsplan für die Wiederherstellung aus. Sie sollten nur die ausgewählten Sicherungen verwenden. Informationen zum Datenbankwiederherstellungsberater finden Sie unter [Übersicht über Wiederherstellungsvorgänge &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).  
  
## <a name="restore-to"></a>Wiederherstellen in  
 Standardmäßig ist**Letzte Sicherung** ausgewählt. [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] wählt die entsprechenden Sicherungen zum Wiederherstellen der Datenbank aus und stellt die Datenbank entsprechend dem Zeitpunkt der letzten Sicherung wieder her. Klicken Sie auf **Bestimmtes Datum und bestimmte Uhrzeit** , um das Datum und die Uhrzeit manuell festzulegen (und so einen bestimmten Zeitpunkt auszuwählen).  
  
 Mit**Bestimmtes Datum und bestimmte Uhrzeit** können Sie die Wiederherstellung zu einem bestimmten ausgewählten Datum und einer bestimmten Uhrzeit beenden. Die Zeitachse zeigt die Sicherungsvorgänge in den 24 Stunden um das ausgewählte Datum und die Uhrzeit an.  
  
 **Datum**  
 Wählen Sie in der Dropdownliste ein Datum aus, oder geben Sie ein Datum ein.  
  
 **Zeit**  
 Geben Sie ein Datum ein, oder wählen Sein ein Datum aus, um den bestimmten Zeitpunkt anzugeben, bis zu dem die Wiederherstellung durchgeführt werden soll.  
  
 **Zeitachsenintervall**  
 Zeigt die Optionen für die Intervalltypen an, die auf der Zeitachse angezeigt werden können.  
  
## <a name="timeline-and-legend"></a>Zeitachse und Legende  
 Verwenden Sie die Bildlaufleiste unter der Zeitachse, um den Cursor auf der Zeitachse vorwärts und rückwärts zu bewegen. Klicken Sie auf eine Sicherung, um die Bildlaufleiste an das Ende dieser Sicherung zu verschieben. Zeigen Sie mit der Maus auf einen Marker, um eine QuickInfo mit Informationen zum ausgewählten Sicherungssatz anzuzeigen. Die Sicherungsinformationen werden mit den folgenden Markern auf der Zeitachse angezeigt:  
  
 Größeres Dreieck  
 Stellt die für die Datenbank ausgeführten vollständigen Sicherungen dar und bezeichnet den jeweiligen Ausführungszeitpunkt der einzelnen vollständigen Sicherungen.  
  
 Kleineres Dreieck  
 Stellt die für die Datenbank ausgeführten differenziellen Sicherungen dar und bezeichnet den jeweiligen Ausführungszeitpunkt der einzelnen differenziellen Sicherungen.  
  
 Grün schattierte Bereiche  
 Stellen den Sicherungsumfang des Transaktionsprotokolls dar.  
  
 Rote Linie  
 Kann nur an Stellen auf der Zeitachse positioniert werden, für die eine Wiederherstellung möglich ist. Wenn Sie die rote Linie entlang der Zeitachse verschieben, werden die oben angezeigten Felder **Datum** und **Uhrzeit** angepasst.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbank wiederherstellen &#40;Seite „Allgemein“&#41;](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
  
