---
title: Eigenschaften von Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- report servers [Reporting Services], properties
- properties [Reporting Services], about properties
- reports [Reporting Services], properties
- Report Server Web service, properties
- report properties [Reporting Services]
- XML Web service [Reporting Services], properties
- Web service [Reporting Services], properties
- properties [Reporting Services]
ms.assetid: 8c855194-4c20-4ecc-a328-5137d54b560c
caps.latest.revision: 33
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 764d86808d2febf7ea2199c86cdebd7d7b021f5a
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37198430"
---
# <a name="reporting-services-properties"></a>Eigenschaften von Reporting Services
  Der Berichtsserver definiert eine Reihe von Systemeigenschaften, die global für den Berichtsserver gelten, und eine Reihe von Elementeigenschaften, die zu einem in der Berichtsserver-Datenbank gespeicherten Einzelelement gehören. Vom Berichtsserver definierte Eigenschaften können nicht gelöscht werden, und in einigen Fällen sind sie schreibgeschützt. In einer Anwendung können die System- und Elementeigenschaften erweitert werden, indem zusätzliche benutzerdefinierte Eigenschaften zu den System- und den Elementeigenschaften hinzugefügt werden.  
  
 Die folgenden Webdienstmethoden rufen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Eigenschaften ab und legen diese fest.  
  
|Methode|Aktion|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.GetProperties%2A>|Gibt die Werte von einer oder mehreren Eigenschaften eines Elements in der Berichtsserver-Datenbank zurück.|  
|<xref:ReportService2010.ReportingService2010.GetSystemProperties%2A>|Gibt eine oder mehrere Systemeigenschaften zurück.|  
|<xref:ReportService2010.ReportingService2010.SetProperties%2A>|Legt eine oder mehrere Eigenschaften eines Elements in der Berichtsserver-Datenbank fest.|  
|<xref:ReportService2010.ReportingService2010.SetSystemProperties%2A>|Legt eine oder mehrere Systemeigenschaften fest.|  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Thema|Description|  
|-----------|-----------------|  
|[Eigenschaften der Berichtsserverelemente](reporting-services-properties-report-server-item-properties.md)|Beschreibt die elementspezifischen Eigenschaften in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].|  
|[Berichtsserver-Systemeigenschaften](reporting-services-properties-report-server-system-properties.md)|Beschreibt die systemspezifischen Eigenschaften in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].|  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Anwendungen mit dem Webdienst und .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md)   
 [Berichtsserver-Webdienst](../report-server-web-service.md)   
 [Technische Referenz (SSRS)](../../technical-reference-ssrs.md)  
  
  
