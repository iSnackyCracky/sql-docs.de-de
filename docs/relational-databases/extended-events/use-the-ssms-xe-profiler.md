---
title: Verwenden des SSMS XEvent Profilers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: genemi
ms.suite: sql
ms.technology: xevents
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], system health session
- extended events [SQL Server], system_health session
- system_health session [SQL Server extended events]
- system health session [SQL Server extended events]
ms.assetid: 1e1fad43-d747-4775-ac0d-c50648e56d78
author: yualan
ms.author: alayu
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: bcb53b0d9e6254d00ed313ba6df2774810eb9344
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39555470"
---
# <a name="use-the-ssms-xevent-profiler"></a>Verwenden des SSMS XEvent Profilers
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
Der XEvent Profiler ist ein Feature von SQL Server Management Studio (SSMS), das ein Liveanzeigefenster mit erweiterten Ereignissen anzeigt. In dieser Übersicht werden die Gründe für die Verwendung dieses Profilers, seine wichtigsten Funktionen sowie die ersten Schritte zum Anzeigen erweiterter Ereignisse beschrieben.

## <a name="why-would-i-use-the-xevent-profiler"></a>Warum sollte ich den XEvent-Profiler verwenden?
Im Gegensatz zum SQL Profiler ist der XEvent Profiler direkt in SSMS integriert und basiert auf der skalierbaren Technologie für erweiterte Ereignisse in der SQL-Engine. Dieses Feature ermöglicht einen schnellen Zugriff auf eine Livestreamingansicht für Diagnoseereignisse in SQL Server. Diese Ansicht kann angepasst werden, und entsprechende Anpassungen können in Form einer VIEWSETTINGS-Datei für andere SSMS-Benutzer freigegeben werden. Die vom XE Profiler erstellte Sitzung greift in geringerem Maße in die SQL Server-Ausführung ein als eine ähnliche SQL-Ablaufverfolgung bei Verwendung des SQL Profilers. Auch diese Sitzung kann über die vorhandene Benutzeroberfläche für XE-Sitzungseigenschaften oder über TSQL vom Benutzer angepasst werden.

## <a name="prerequisites"></a>Voraussetzungen
Dieses Feature ist nur in SQL Server Management Studio (SSMS) v17.3 oder höher verfügbar. Stellen Sie sicher, dass Sie die neueste Version verwenden. Die neueste Version ist [hier](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) zu finden.

## <a id="getting-started"></a>Erste Schritte
Um auf den XEvent Profiler zuzugreifen, gehen Sie folgendermaßen vor:

1. Öffnen Sie **SQL Server Management Studio**.

2. Stellen Sie eine Verbindung mit einer Instanz der SQL Server-Datenbank-Engine oder mit localhost her.

3. Suchen Sie im Objekt-Explorer das XE Profiler-Menüelement, und erweitern Sie es durch Klicken auf das Pluszeichen „+“.

   ![XEProfiler-Menü](media/xevents-xe-profiler-menu.png)

4. Doppelklicken Sie auf **Standard**, wenn Sie alle erweiterten Ereignisse in dieser Sitzung anzeigen möchten. Klicken Sie auf **T-SQL**, wenn Sie die protokollierten SQL-Anweisungen anzeigen möchten. Wenn noch keine Sitzung erstellt wurde, wird eine Sitzung für Sie erstellt.

   ![XEProfiler-Sitzung](media/xevents-xe-profiler-start-session.png)

5. Sie können jetzt Ihre erweiterten Ereignisse anzeigen.

   ![XEProfiler-Viewer](media/xevents-xe-profiler-start-viewer.png)

## <a name="see-also"></a>Weitere Informationen finden Sie unter
[Erweiterte Ereignisse](../../relational-databases/extended-events/extended-events.md)  
[Tools für erweiterte Ereignisse](../../relational-databases/extended-events/extended-events-tools.md)  
  
  
