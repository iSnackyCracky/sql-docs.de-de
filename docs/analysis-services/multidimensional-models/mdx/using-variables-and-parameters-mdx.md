---
title: Verwenden von Variablen und Parametern (MDX) | Microsoft Docs
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: deb1f7b4e641dd2347e8629e1e13ad3f4da7788c
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
ms.locfileid: "34027007"
---
# <a name="using-variables-and-parameters-mdx"></a>Verwenden von Variablen und Parametern (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] können Sie eine MDX-Anweisung (Multidimensional Expressions) parametrisieren. Eine parametrisierte Anweisung ermöglicht Ihnen das Erstellen von allgemeinen Anweisungen, die während der Laufzeit angepasst werden können.  
  
 Beim Erstellen einer parametrisierten Anweisung kennzeichnen Sie den Parameternamen, indem Sie dem Namen das @-Zeichen voranstellen. Beispielsweise @Year wäre ein gültiger Parametername  
  
 MDX unterstützt Parameter nur für Literal- oder skalare Werte. Zum Erstellen eines Parameters, der auf ein Element, eine Menge oder ein Tupel verweist, müssen Sie eine Funktion verwenden (z. B. [StrToMember](../../../mdx/strtomember-mdx.md) oder [StrToSet](../../../mdx/strtoset-mdx.md)).  
  
 In der folgenden XML for Analysis (XMLA) beispielsweise die @CountryName Parameter enthält das Land, für welche Kunden Daten abgerufen:  
  
```  
<Envelope xmlns="http://schemas.xmlsoap.org/soap/envelope/">  
  <Body>  
    <Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
      <Command>  
        <Statement>  
select [Measures].members on 0,   
       Filter(Customer.[Customer Geography].Country.members,   
              Customer.[Customer Geography].CurrentMember.Name =  
              @CountryName) on 1  
from [Adventure Works]  
</Statement>  
      </Command>  
      <Properties />  
      <Parameters>  
        <Parameter>  
          <Name>CountryName</Name>  
          <Value>'United Kingdom'</Value>  
        </Parameter>  
      </Parameters>  
    </Execute>  
  </Body>  
</Envelope>  
```  
  
 Wenn Sie diese Funktionalität mit OLE DB verwenden möchten, verwenden Sie die **ICommandWithParameters** -Schnittstelle. Wenn Sie diese Funktionalität mit ADOMD.Net verwenden möchten, verwenden Sie die **AdomdCommand.Parameters** -Auflistung.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlegendes zu MDX-Skripts & #40; Analysis Services & #41;](../../../analysis-services/multidimensional-models/mdx/mdx-scripting-fundamentals-analysis-services.md)  
  
  
