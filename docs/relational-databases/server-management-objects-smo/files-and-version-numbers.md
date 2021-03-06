---
title: Dateien und Versionsnummern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: smo
ms.reviewer: ''
ms.suite: sql
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, versions
- components [SMO]
- files [SMO], components
- SMO [SQL Server], versions
- versions [SMO]
ms.assetid: 510907b6-e7a9-41bd-b892-d6d99a5118e1
caps.latest.revision: 34
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: 871ce9d2aaded63b20965d4cd9ec2e1d53323d1f
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39540010"
---
# <a name="files-and-version-numbers"></a>Dateien und Versionsnummern
[!INCLUDE[appliesto-ss-asdb-asdw-xxx-md](../../includes/appliesto-ss-asdb-asdw-xxx-md.md)]

  Alle erforderlichen Komponenten für SQL Server Management Object (SMO) in das Microsoft.SqlServer.SqlManagementObjects NuGet-Paket enthalten sind. SMO ist in mehreren verwalteten Assemblys implementiert. Sie können SMO-Anwendungen entweder auf einem Client oder auf einem Server entwickeln.  

>>[!Important]
Die Dateiversion der SMO-Assemblys wird als wesentliche angezeigt. **0**. Build.Revision. Aber die eingebetteten Assemblyversion ist die Hauptversion. **100**. Build.Revision. Dadurch wird um die Version von SMO verwendet, die in jeder Anwendung getrennt zu halten, damit Updates für eine hat keine Auswirkungen auf alle anderen.
>>
>>Aus diesem Grund sollten Sie **nicht** installieren Sie diese Versionen der Assemblys zum globalen Assemblycache (GAC). Auf diese Weise kann dazu führen, dass andere Anwendungen, z. B. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio, unterbrochen. 
  
|File|Description|  
|-----------|-----------------|  
|Microsoft.SqlServer.ConnectionInfo.dll|Unterstützt das Herstellen von Verbindungen mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|  
|Microsoft.SqlServer.ServiceBrokerEnum.dll|Unterstützt die Programmierung des [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service Broker. Dies ist nur in Programmen erforderlich, die auf Service Broker zugreifen.|  
|Microsoft.SqlServer.Smo.dll|Enthält einen Großteil der SMO-Klassen.|  
|Microsoft.SqlServer.SmoExtended.dll<br /><br /> Microsoft.SqlServer.Management.Sdk.Sfc.dll<br /><br /> Microsoft.SqlServer.SqlEnum.dll|Unterstützt die SMO-Klassen.|  
|Microsoft.SqlServer.WmiEnum.dll|Enthält die WMI-Anbieterklassen (Windows Management Instrumentation, Windows-Verwaltungsinstrumentation). Dies ist nur für Programme erforderlich, die die WMI-Anbieterklassen verwenden.|  
|Microsoft.SqlServer.RegSvrEnum.dll|Enthält die Klassen, die den registrierten Server darstellen. Dies ist nur für Programme erforderlich, die die Klassen für den registrierten Server enthalten.|  
  
  
