---
title: SQL Operations Studio (Vorschau) SQL Server Profiler-Erweiterung | Microsoft-Dokumentation
description: SQL Server Profiler-Erweiterung für SQL Operations Studio (Vorschau)
ms.custom: tools|sos
ms.date: 07/19/2018
ms.reviewer: alayu; sstein
ms.prod: sql
ms.suite: sql
ms.prod_service: sql-tools
ms.component: sos
ms.tgt_pltfrm: ''
ms.topic: conceptual
author: yualan
ms.author: alayu
manager: craigg
ms.openlocfilehash: 190d54a4525a476b2c42c22d447264a1d95e7bc4
ms.sourcegitcommit: 4b21840f20195d70f255465666f7b409ba839d18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2018
ms.locfileid: "39147027"
---
# <a name="sql-server-profiler-extension"></a>SQL Server Profiler-Erweiterung

Die SQL Server Profiler, die Erweiterung eine einfache SQL Server-Ablaufverfolgung-Lösung, die für Sie ähnlich wie SQL Server Management Studio (SSMS) Profiler außer bietet erstellt, verwenden von XEvents. SQL Server Profiler ist sehr einfach zu verwenden und verfügt über gute Standardwerte für die am häufigsten verwendeten Konfigurationen für die Ablaufverfolgung. Die UX ist optimiert für Ereignisse durchsuchen und Anzeigen der zugehörigen Texts der Transact-SQL (T-SQL). Außerdem wird davon ausgegangen gute Standardwerte für das Sammeln von T-SQL-Ausführung-Aktivitäten mit eine benutzerfreundliche benutzererfahrung für die SQL Server Profiler für SQL Operations Studio

**Allgemeine SQL Profiler Anwendungsfälle:**

- Schrittweises Untersuchen problematischer Abfragen, um die Ursache des Problems zu ermitteln.
- Suchen und Diagnostizieren von Abfragen, die sehr langsam ausgeführt werden.
- Erfassen der Transact-SQL-Anweisungen, die zu einem Problem führen.
- Überwachen die Leistung des SQL Servers, arbeitsauslastungen zu optimieren.
- Korrelieren von Leistungsindikatoren zur Diagnose von Problemen.


## <a name="install-the-sql-server-profiler-extension"></a>Installieren Sie die SQL Server Profiler-Erweiterung

1. Um Erweiterungs-Manager öffnen und den Zugriff auf die verfügbaren Erweiterungen, wählen Sie das Symbol für Erweiterungen oder **Erweiterungen** in die **Ansicht** Menü.
2. Wählen Sie eine verfügbare Erweiterung, um seine Details anzuzeigen.

   ![Profiler-Erweiterungs-manager](media/extensions/sql-server-profiler-extension/profiler-extension.png)

1. Wählen Sie die gewünschte Erweiterung und **installieren** es.
2. Wählen Sie **Reload** zum Aktivieren der Erweiterung (nur beim ersten eine Erweiterung der Installation erforderlich).

## <a name="start-profiler"></a>Starten von Profiler

1. Um den Profiler zu starten, stellen Sie zunächst eine Verbindung mit einem Server, auf der Registerkarte "Server".
2. Nachdem Sie eine Verbindung herstellen, geben Sie **Alt + P** Profiler zu starten.
3. Geben Sie zum Starten von Profiler **Alt + S.** Nun können Sie erweiterte Ereignisse angezeigt.
    ![Profiler-Erweiterungs-manager](media/extensions/sql-server-profiler-extension/view-profiler.png)    
1. Um Profiler beenden möchten, geben **Alt + S.** Dieses Hotkeys ist eine Umschaltoption.

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zum Profiler und erweiterte Ereignisse finden Sie unter [erweiterte Ereignisse](https://docs.microsoft.com/sql/relational-databases/extended-events/extended-events).





