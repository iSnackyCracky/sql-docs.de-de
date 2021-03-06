---
title: Konfigurieren für den sicheren bzw. uneingeschränkten DataFactory | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- DataFactory configuration in RDS [ADO]
ms.assetid: 8ff24805-dc7a-42ae-b600-5bad0e3f51b8
caps.latest.revision: 15
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 1b1356c61602d1383788263e4031f8059fe81bb2
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "35273755"
---
# <a name="configuring-datafactory-for-safe-or-unrestricted-modes"></a>Konfigurieren für den sicheren bzw. uneingeschränkten DataFactory
> [!IMPORTANT]
>  Ab Windows 8 und Windows Server 2012, sind nicht mehr RDS-Server-Komponenten in Windows-Betriebssystems enthalten (finden Sie unter Windows 8 und [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/en-us/download/details.aspx?id=27416) detailliertere). RDS-Clientkomponenten werden in einer zukünftigen Version von Windows entfernt werden. Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktion zurzeit verwenden. Anwendungen, die RDS verwenden sollten migrieren [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
 ADO wird standardmäßig mit einem "Safe" installiert [RDSServer.DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md) Konfiguration. Im Abgesicherter Modus für RDS-Serverkomponenten bedeutet, dass Folgendes zutrifft:  
  
1.  Ereignishandler ist mit der RDSServer.DataFactory (Dies ist eine Einstellung des Registrierungsschlüssels infosetspezifikation) erforderlich.  
  
2.  Der Standardhandler, msdfmap.handler, registrierten, in der Liste sicherer Handler vorhanden und als Standardhandler gekennzeichnet ist.  
  
3.  Datei "Msdfmap.ini" ist im Windows-Verzeichnis installiert. Sie müssen diese Datei vor der Verwendung von RDS in drei Ebenen Modus gemäß Ihren Anforderungen konfigurieren.  
  
 Optional können Sie eine uneingeschränkte konfigurieren **DataFactory** Installation. **DataFactory** können direkt ohne den benutzerdefinierten Handler verwendet werden. Benutzer können einen benutzerdefinierten Handler weiterhin verwenden, indem Sie die Verbindungszeichenfolgen ändern, aber es ist nicht erforderlich. Weitere Informationen zu den Auswirkungen der Verwendung der **RDSServer.DataFactory** Objekt, finden Sie unter [Securing RDS Applications](../../../ado/guide/remote-data-service/securing-rds-applications.md).  
  
 Die Registrierung Datei handsafe.reg wurde angegeben, um die Registrierungseinträge Handler für eine sichere Konfiguration einzurichten. Führen Sie zum Ausführen im abgesicherten Modus handsafe.reg.  
  
 Nach der Ausführung handsafe.reg, müssen beenden und Neustarten von der WWW-Publishingdienst auf dem Webserver durch die folgenden Befehle in einem Eingabeaufforderungsfenster eingeben: "NET STOP W3SVC" und "NET START W3SVC".  
  
## <a name="see-also"></a>Siehe auch  
 [DataFactory-Anpassung](../../../ado/guide/remote-data-service/datafactory-customization.md)   
 [Grundlegendes zu RDS](../../../ado/guide/remote-data-service/rds-fundamentals.md)



