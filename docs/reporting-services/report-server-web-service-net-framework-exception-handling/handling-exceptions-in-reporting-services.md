---
title: Behandeln von Ausnahmen in Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.component: report-server-web-service-net-framework-exception-handling
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- SOAP [Reporting Services], exceptions
- .NET Framework [Reporting Services]
- exceptions [Reporting Services], about exception handling
- SoapException object
ms.assetid: 1a443432-2db5-48c5-bc29-433b4688082f
caps.latest.revision: 31
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 75bc7d7f057c9207a0f70525acf61072b82f3469
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "33024467"
---
# <a name="handling-exceptions-in-reporting-services"></a>Behandeln von Ausnahmen in Reporting Services
  Wenn eine Anforderung auf den Reporting Services-SOAP-API-Client nicht durchgeführt werden kann, gibt der Berichtsserver eine Fehlermeldung statt der erwarteten Ergebnisse des Aufrufs aus. Wenn ein Aufruf nicht durchgeführt werden kann, wird eine Fehlermeldung für den Berichtsserver-Webdienst als ein SOAP-**Fault**-XML-Element zurückgegeben. Das wichtigste Beschreibungselement des Fehlers ist das **detail**-Element, das alle vom Berichtsserver gelieferten Fehlerdaten sowie weitere Fehlerdaten des Webdiensts enthält. Die wichtigste Information im **detail**-Element ist der Fehlercode des Berichtsservers. Auf der Grundlage der Meldung und des Fehlercodes können Sie bestimmen, welche Aktion als Nächstes in Ihren Anwendungen vorgenommen werden muss. Weitere Informationen zu SOAP-Fehlern finden Sie im World Wide Web Consortium (W3C) auf der Website unter http://www.w3.org/TR/SOAP.  
  
## <a name="soap-faults-and-the-net-framework"></a>SOAP-Fehler und das .NET Framework  
 Falls in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] ein Fehler in einer Clientanforderung an einen Webdienst auftritt, kommuniziert der Berichtsserver den Fehler an den Clientcode, der den Webdienst aufruft, indem er ein **SoapException**-Objekt auslöst. Die **SoapException** umbricht die in einem SOAP-Fehler enthaltenen Informationen in die nächste Zeile. Die **Detail**-Eigenschaft in der **SoapException** entspricht dem **detail**-Element im SOAP-Fehler. Anwendungen sollten das **SoapException**-Objekt mit einem try/catch-Block erfassen und die **Detail**-Eigenschaft der **SoapException** verwenden, um die entsprechende Aktion vorzunehmen. Weitere Informationen zur **SoapException**-Klasse und der **Detail**-Eigenschaft in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] finden Sie unter [SoapException-Klasse von Reporting Services](../../reporting-services/report-server-web-service-net-framework-exception-handling/soapexception-class/reporting-services-soapexception-class.md). Weitere Informationen zur **SoapException**-Klasse finden Sie in der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK-Dokumentation.  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Detail-Eigenschaft](../../reporting-services/report-server-web-service-net-framework-exception-handling/soapexception-class/detail-property.md)   
 [Introducing Exception Handling in Reporting Services (Einführung in die Ausnahmebehandlung in Reporting Services)](../../reporting-services/report-server-web-service-net-framework-exception-handling/introducing-exception-handling-in-reporting-services.md)   
 [Reporting Services SoapException Class (Reporting Services-SoapException-Klasse)](../../reporting-services/report-server-web-service-net-framework-exception-handling/soapexception-class/reporting-services-soapexception-class.md)  
  
  
