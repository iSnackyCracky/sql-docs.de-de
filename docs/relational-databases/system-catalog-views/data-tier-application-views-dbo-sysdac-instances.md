---
title: dbo.sysdac_instances (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- dbo.sysdac_instances_TSQL
- sysdac_instances
- sysdac_instances_TSQL
- dbo.sysdac_instances
dev_langs:
- TSQL
helpviewer_keywords:
- dbo.sysdac_instances
- sysdac_instances
ms.assetid: 28285f3d-3889-439f-8b24-3bdef08e46b4
caps.latest.revision: 9
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 813a786f68fe02431073033172d37ffe2c682ee0
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38031338"
---
# <a name="data-tier-application-views---dbosysdacinstances"></a>Sichten von datenebenenanwendungen - dbo.sysdac_instances
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  Zeigt eine Zeile für jede Instanz der Datenebenenanwendung (DAC) an, die für eine [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz bereitgestellt wird. Sysdac_instances gehört zum Dbo-Schema in der Msdb-Datenbank. In der folgende Tabelle werden die Spalten in der Ansicht Sysdac_instances beschrieben.  
  
|Spaltenname|Datentyp|Description|  
|-----------------|---------------|-----------------|  
|instance_id|**uniqueidentifier**|Der Bezeichner der DAC-Instanz.|  
|instance_name|**sysname**|Der Name der DAC-Instanz, die bei der Bereitstellung der DAC angegeben wurde.|  
|type_name|**sysname**|Der Name der DAC, die bei der Erstellung des DAC-Pakets angegeben wurde.|  
|type_version|**nvarchar(64)**|Die Version der DAC, die bei der Erstellung des DAC-Pakets angegeben wurde.|  
|description|**nvarchar(4000)**|Eine Beschreibung der DAC, die bei der Erstellung des DAC-Pakets geschrieben wurde.|  
|type_stream|**varbinary(max)**|Ein Bitdatenstrom, der eine codierte Darstellung der in der DAC enthaltenen logischen Objekte, z. B. Tabellen und Sichten, enthält.|  
|date_created|**datetime**|Datum und Uhrzeit der Erstellung der DAC-Instanz.|  
|created_by|**sysname**|Melden Sie sich, die die DAC-Instanz erstellt.|  
|database_name|**sysname**|Der Name der Datenbank, die für die DAC-Instanz erstellt wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Eine DAC umfasst einen DAC-Typ, der eine Definition der von einer Anwendung verwendeten logischen Datenebenenobjekte, z. B. Tabellen und Sichten, ist. Ein DAC-Paket ist eine Datei, die zur Bereitstellung einer DAC verwendet wird. Das DAC-Paket enthält eine Darstellung aller logischen Objekte, die im DAC-Typ enthalten sind. Das DAC-Paket kann dazu verwendet werden, eine oder mehrere Kopien bzw. Instanzen der DAC auf einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz bereitzustellen. Jede DAC-Instanz, die vom selben DAC-Paket bereitgestellt wird, verwendet den gleichen Typ; ihr wird jedoch ein eindeutiger Instanzname und Bezeichner zugewiesen.  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die Mitgliedschaft in der festen Serverrolle sysadmin, um alle Spalten anzuzeigen. Mitglieder der Rolle public können die Spalten instance_name, description und type_version anzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenebenenanwendungen](../../relational-databases/data-tier-applications/data-tier-applications.md)   
 [Sichten von datenebenenanwendungen &#40;Transact-SQL&#41;](http://msdn.microsoft.com/library/0de01328-d7a6-4677-b7a0-dcd3098c23d4)  
  
  
