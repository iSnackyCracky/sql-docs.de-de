---
title: Sys. database_usage (Azure SQL-Datenbank) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/03/2017
ms.prod: ''
ms.prod_service: sql-database
ms.reviewer: ''
ms.service: sql-database
ms.component: system-catalog-views
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- database_usage
- database_usage_TSQL
- sys.database_usage_TSQL
- sys.database_usage
dev_langs:
- TSQL
helpviewer_keywords:
- database_usage
- sys.database_usage
ms.assetid: be6820de-60bf-4ddd-ace7-4077893d630f
caps.latest.revision: 13
author: edmacauley
ms.author: edmaca
manager: craigg
monikerRange: = azuresqldb-current || = sqlallproducts-allversions
ms.openlocfilehash: affdc08bb7ae507ca30edfa986cd68a81ba564f2
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38038818"
---
# <a name="sysdatabaseusage-azure-sql-database"></a>sys.database_usage (Azure SQL-Datenbank)
[!INCLUDE[tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md.md)]

  **Hinweis: Dies gilt nur für Azure SQL-Datenbank V11.**  
  
 Listet Anzahl, Typ und Dauer der Datenbanken auf dem [!INCLUDE[ssSDS](../../includes/sssds-md.md)] Server.  
  
 Die **Sys. database_usage** -Ansicht enthält die folgenden Spalten.  
  
|Spaltenname|Description|  
|-----------------|-----------------|  
|Uhrzeit|Das Datum, an dem die Verwendungsereignisse eingetreten sind.|  
|sku|Der Typ der Dienstebene für die Datenbank: **Web**, **Business**, **grundlegende**, **Standard**, **Premium**|  
|quantity|Die maximale Anzahl von Datenbanken eines SKU-Typs, der an diesem Tag vorhanden war.|  
  
## <a name="permissions"></a>Berechtigungen  
 Nur-Lese Zugriff auf diese Sicht wird für alle Benutzer mit Berechtigungen zum Herstellen einer Verbindung mit der **master** Datenbank.  
  
## <a name="remarks"></a>Hinweise  
 Die **Sys. database_usage** Sicht gibt eine Zeile für jeden Tag des Ihrem Abonnement zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Preisdetails – SQL-Datenbank](http://go.microsoft.com/fwlink/?LinkID=394978)   
 [Konten und Abrechnung in Windows Azure SQL-Datenbank](http://msdn.microsoft.com/library/windowsazure/ee621788.aspx)  
  
  
