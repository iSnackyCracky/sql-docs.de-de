---
title: Verwalten von SQLServer unter Linux | Microsoft-Dokumentation
description: Dieser Artikel enthält Links zu allgemeinen Verwaltungsaufgaben und Tools für SQL Server unter Linux ausgeführt wird.
author: rothja
ms.author: jroth
manager: craigg
ms.date: 03/17/2017
ms.topic: conceptual
ms.prod: sql
ms.component: ''
ms.suite: sql
ms.technology: linux
ms.assetid: 6bd8eb0b-593d-467e-87ea-ab1c4dbcd1ea
ms.custom: sql-linux
ms.openlocfilehash: d537c4ef2bb84833b4676acebdaf0906ee7a85c9
ms.sourcegitcommit: 79d4dc820767f7836720ce26a61097ba5a5f23f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2018
ms.locfileid: "40392989"
---
# <a name="choose-the-right-tool-to-manage-sql-server-on-linux"></a>Auswählen des richtigen Tools zum Verwalten von SQL Server unter Linux

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-linuxonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-linuxonly.md)]

Es gibt verschiedene Methoden zum Verwalten von SQL Server 2017 unter Linux. Der folgende Abschnitt enthält eine kurze Übersicht über verschiedene Tools und Techniken mit Zeigern auf Weitere Ressourcen.

## <a name="mssql-conf"></a>mssql-conf 

Die **Mssql-Conf** Tool konfiguriert die SQL Server unter Linux. Weitere Informationen finden Sie unter [Konfigurieren von SQL Server unter Linux mit Mssql-Conf](sql-server-linux-configure-mssql-conf.md).

## <a name="transact-sql"></a>Transact-SQL

Fast alles, was in einem Clienttool Maßnahme kann auch mit Transact-SQL-Anweisungen ausgeführt werden. SQL Server bietet [Dynamic Management Views (DMVs)](../relational-databases/system-dynamic-management-views/system-dynamic-management-views.md) Abfrage den Status und die Konfiguration von SQL Server. Es gibt auch [Transact-SQL-Befehle](../t-sql/language-reference.md) für Aufgaben der datenbankverwaltung. Sie können diese Befehle ausführen, in jedem Clienttool, die eine Verbindung mit SQL Server herstellen und Ausführen von Transact-SQL-Abfragen, z. B. unterstützt [Sqlcmd](sql-server-linux-setup-tools.md) oder [Visual Studio Code](sql-server-linux-develop-use-vscode.md).

## <a name="sql-server-operations-studio-preview"></a>SQL Server Operations Studio (Vorschau)

Die neue Microsoft SQL Operations Studio (preview) ist eine plattformübergreifende-Tool zum Verwalten von SQL Server. Weitere Informationen finden Sie unter [Microsoft SQL Operations Studio (preview)](../sql-operations-studio/what-is.md).

## <a name="sql-server-management-studio-on-windows"></a>SQL Server Management Studio unter Windows

SQL Server Management Studio (SSMS) ist eine Windows-Anwendung, die eine grafische Benutzeroberfläche bereitstellt, für die Verwaltung von SQL Server. Obwohl es derzeit nur unter Windows ausgeführt wird, können sie Sie eine Remoteverbindung mit Ihrem virtuellen SQL Server-Instanzen herstellen. Weitere Informationen zur Verwendung von SSMS zum Verwalten von SQL Server finden Sie unter [SSMS verwenden, um die Verwaltung von SQL Server unter Linux](sql-server-linux-manage-ssms.md).

## <a name="mssql-cli-preview"></a>MSSQL-Cli (Vorschau)

Microsoft hat ein neues Skriptingtools Cross-Platform-Tool für SQL Server [Mssql-Cli](https://blogs.technet.microsoft.com/dataplatforminsider/2017/12/12/try-mssql-cli-a-new-interactive-command-line-tool-for-sql-server/). Dieses Tool befindet sich derzeit in der Vorschau.

## <a name="powershell"></a>PowerShell

PowerShell bietet eine umfassende befehlszeilenumgebung zum Verwalten von SQL Server unter Linux. Weitere Informationen finden Sie unter [Verwenden von PowerShell zum Verwalten von SQL Server unter Linux](sql-server-linux-manage-powershell.md).

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu SQL Server unter Linux finden Sie unter [SQL Server unter Linux](sql-server-linux-overview.md).
