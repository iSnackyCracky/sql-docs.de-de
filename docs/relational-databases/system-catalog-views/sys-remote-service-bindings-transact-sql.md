---
title: Sys. remote_service_bindings (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.remote_service_bindings_TSQL
- remote_service_bindings_TSQL
- remote_service_bindings
- sys.remote_service_bindings
dev_langs:
- TSQL
helpviewer_keywords:
- sys.remote_service_bindings catalog view
ms.assetid: 4e1a885d-eed1-4993-9c87-e6fd781f437d
caps.latest.revision: 20
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: b51b1ad09e3b1dd3252178e45934fafa46d4e688
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33181516"
---
# <a name="sysremoteservicebindings-transact-sql"></a>sys.remote_service_bindings (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Diese Katalogsicht enthält eine Zeile pro Remotedienstbindung. 
  
|Spaltenname|Datentyp|Description|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|Name dieser Remotedienstbindung. Lässt keine NULL-Werte zu.|  
|**remote_service_binding_id**|**int**|ID dieser Remotedienstbindung. Lässt keine NULL-Werte zu.|  
|**principal_id**|**int**|ID des Datenbankprinzipals, der diese Remotedienstbindung besitzt. Lässt NULL-Werte zu.|  
|**remote_service_name**|**nvarchar(256)**|Name des Remotediensts, auf den sich diese Bindung bezieht. Lässt NULL-Werte zu.|  
|**service_contract_id**|**int**|ID des Vertrags, auf den sich diese Bindung bezieht. Der Wert 0 ist ein Platzhalter, der darauf hinweist, dass diese Bindung für alle Verträge des Diensts wirksam ist. Lässt keine NULL-Werte zu.|  
|**remote_principal_id**|**int**|ID des in der Remotedienstbindung angegebenen Benutzers. Service Broker verwendet ein Zertifikat im Besitz dieses Benutzers, um mit dem angegebenen Dienst über die angegebenen Verträge zu kommunizieren. Lässt NULL-Werte zu.|  
|**is_anonymous_on**|**bit**|Diese Remotedienstbindung verwendet die ANONYMOUS-Sicherheit. Die Identität des Benutzers, der die Konversation beginnt, wird dem Zieldienst nicht zur Verfügung gestellt. Lässt keine NULL-Werte zu.|  
  
## <a name="permissions"></a>Berechtigungen  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Weitere Informationen finden Sie unter [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
  
