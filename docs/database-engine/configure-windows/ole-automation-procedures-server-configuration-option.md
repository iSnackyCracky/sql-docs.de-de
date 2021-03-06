---
title: OLE-Automatisierungsprozeduren (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/02/2017
ms.prod: sql
ms.prod_service: high-availability
ms.reviewer: ''
ms.suite: sql
ms.technology: configuration
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Ole Automation Procedures option
ms.assetid: e8982e05-4984-4406-9760-285e8c028ddf
caps.latest.revision: 20
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 55e0cd91d46f560de2c5cee204158bc4076273ec
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32864265"
---
# <a name="ole-automation-procedures-server-configuration-option"></a>OLE-Automatisierungsprozeduren (Serverkonfigurationsoption)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  Verwenden Sie die **OLE-Automatisierungsprozeduren** -Option, um anzugeben, ob OLE-Automatisierungsobjekte in [!INCLUDE[tsql](../../includes/tsql-md.md)] -Batches instantiiert werden können. Diese Option kann auch mithilfe der richtlinienbasierten Verwaltung oder der gespeicherten Prozedur **sp_configure** konfiguriert werden. Weitere Informationen finden Sie unter [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).  
  
 Die **Ole Automation Procedures** -Option kann auf die folgenden Werte festgelegt werden.  
  
 0  
 OLE-Automatisierungsprozeduren sind deaktiviert. Standardeinstellung für neue Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 1  
 OLE-Automatisierungsprozeduren sind aktiviert.  
  
 Wenn OLE-Automatisierungsprozeduren aktiviert sind, startet ein Aufruf von **sp_OACreate** die freigegebene OLE-Ausführungsumgebung.  
  
 Der aktuelle Wert der **OLE-Automatisierungsprozeduren** -Option kann mithilfe der gespeicherten Systemprozedur **sp_configure** angezeigt und geändert werden.  
  
## <a name="examples"></a>Beispiele  
 Das folgende Beispiel zeigt, wie die aktuelle Einstellung von OLE-Automatisierungsprozeduren angezeigt werden kann.  
  
```  
EXEC sp_configure 'Ole Automation Procedures';  
GO  
```  
  
 Das folgende Beispiel zeigt, wie OLE-Automatisierungsprozeduren aktiviert werden.  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Ole Automation Procedures', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)   
 [RECONFIGURE &#40;Transact-SQL&#41;](../../t-sql/language-elements/reconfigure-transact-sql.md)   
 [Oberflächenkonfiguration](../../relational-databases/security/surface-area-configuration.md)   
 [Serverkonfigurationsoptionen &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md)  
  
  
