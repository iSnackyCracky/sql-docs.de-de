---
title: Verbinden mit dem Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: c251a239-e0bd-4f45-9207-b76651072dd0
caps.latest.revision: 44
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 03f3e44683ab329e67360be3992fb942c3799165
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MTE75
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38062473"
---
# <a name="connecting-to-the-server"></a>Verbinden mit dem Server
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Die Themen in diesem Abschnitt beschreiben die Optionen und Verfahren, um mithilfe von [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] eine Verbindung zu [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]herzustellen.  

Mittels der Windows-Authentifizierung oder der SQL Server-Authentifizierung können sich die [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] verbinden. Standardmäßig versuchen die [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] sich mit dem Server zu verbinden, in dem sie die Windows-Authentifizierung verwenden.  

## <a name="in-this-section"></a>In diesem Abschnitt  

|Thema|und Beschreibung|  
|---------|---------------|  
|[Vorgehensweise: Herstellen einer Verbindung mithilfe der Windows-Authentifizierung](../../connect/php/how-to-connect-using-windows-authentication.md)|Beschreibt, wie eine Verbindung mittels der Windows-Authentifizierung hergestellt wird|  
|[Vorgehensweise: Herstellen einer Verbindung mithilfe der SQL Server-Authentifizierung](../../connect/php/how-to-connect-using-sql-server-authentication.md)|Beschreibt wie eine Verbindung mittels der SQL Server-Authentifizierung hergestellt wird|  
|[Gewusst wie: Herstellen einer Verbindung mithilfe der Azure Active Directory-Authentifizierung](../../connect/php/azure-active-directory.md)|Beschreibt, wie Sie den Authentifizierungsmodus festlegen und das Herstellen einer Verbindung mit Azure Active Directory-Identitäten.|  
|[Gewusst wie: Verbinden über einen angegebenen Port](../../connect/php/how-to-connect-on-a-specified-port.md)|Beschreibt wie eine Verbindung zum Server über einen angegebenen Port hergestellt wird|  
|[Verbindungspooling](../../connect/php/connection-pooling-microsoft-drivers-for-php-for-sql-server.md)|Bietet Informationen zum Verbindungspooling im Treiber|  
|[Gewusst wie: Deaktivieren von Multiple Active Resultsets (MARS)](../../connect/php/how-to-disable-multiple-active-resultsets-mars.md)|Beschreibt wie die MARS-Funktion beim Herstellen einer Verbindung deaktiviert wird|  
|[Verbindungsoptionen](../../connect/php/connection-options.md)|Listet die erlaubten Optionen im assoziativen Array auf, das Verbindungsattribute enthält.|  
|[Unterstützung für LocalDB](../../connect/php/php-driver-for-sql-server-support-for-localdb.md)|Beschreibt [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] -Unterstützung für die „LocalDB“-Funktion die in [!INCLUDE[ssSQL11](../../includes/sssql11_md.md)]hinzugefügt wurde.|  
|[Unterstützung für Hochverfügbarkeit, Notfallwiederherstellung](../../connect/php/php-driver-for-sql-server-support-for-high-availability-disaster-recovery.md)|Erläutert, wie die Anwendung konfiguriert werden kann, um von den Features für Hochverfügbarkeit und Notfallwiederherstellung zu profitieren, die in [!INCLUDE[ssSQL11](../../includes/sssql11_md.md)] hinzugefügt wurden.|  
|[Herstellen einer Verbindung mit einer Microsoft Azure SQL-Datenbank](../../connect/php/connecting-to-microsoft-azure-sql-database.md)|In diesem Artikel wird das Herstellen einer Verbindung mit einer Azure SQL-Datenbank erläutert.|  
|[Verbindungsstabilität](../../connect/php/connection-resiliency.md)|Erläutert das verbindungsstabilitätsfeature, das unterbrochene Verbindungen erneut herstellt.|  

## <a name="see-also"></a>Weitere Informationen finden Sie unter  
[Programmierhandbuch für den Microsoft-Treiber für PHP für SQLServer](../../connect/php/programming-guide-for-php-sql-driver.md)

[Beispielanwendung &#40;SQLSRV-Treiber&#41;](../../connect/php/example-application-sqlsrv-driver.md)  
