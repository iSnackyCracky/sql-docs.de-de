---
title: Verwenden von Datenbank-E-Mail anstelle von SQL Mail | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: b08df7be-d8be-4184-a661-38ec0ac85cd1
caps.latest.revision: 9
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: fd07bbe2e2703413efc62613a0bfc7a9607aca26
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37188377"
---
# <a name="use-database-mail-instead-of-sql-mail"></a>Verwenden von Datenbank-E-Mail anstelle von SQL Mail
  Diese Regel überprüft die sys.configurations-Katalogsicht, um zu bestimmen, ob die serverweite Konfigurationoption von SQL Mail XPs auf ON festgelegt ist.  
  
## <a name="best-practices-recommendations"></a>Empfehlungen zu Best Practices  
 SQL Mail wird in einer zukünftigen Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]entfernt. Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktion zurzeit verwenden. Verwenden Sie zum Versenden von E-Mail-Nachrichten Datenbank-E-Mail.  
  
 SQL Mail wird prozessintern zum [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst ausgeführt. Wenn SQL Mail beendet wird, wird der Server ebenfalls beendet. Datenbank-E-Mail wird in einem separaten Prozess außerhalb von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt. Sie ist skalierbar und benötigt keine Extended MAPI-Clientkomponenten auf dem Produktionsserver.  
  
## <a name="for-more-information"></a>Weitere Informationen  
 [Datenbank-E-Mail](../database-mail/database-mail.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
