---
title: Mixed-Datentyp und Simple-Inhalt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-xml
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- mixed types [SQL Server]
ms.assetid: 6ea1f11d-e64b-4ebb-ab68-4eb6e4027665
caps.latest.revision: 8
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: e4aeec997ee728081f74028538c6939ff60a410a
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37268596"
---
# <a name="mixed-type-and-simple-content"></a>Mixed-Datentyp und Simple-Inhalt
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt das Beschränken eines mixed-Datentyps auf simple-Inhalt nicht.  
  
## <a name="example"></a>Beispiel  
 In der folgenden XML-Schemaauflistung ist `myComplexTypeA` ein complex-Datentyp, der leer sein kann. Das heißt, bei beiden Elementen wurde `minOccurs` auf 0 festgelegt. Der Versuch, dies wie in der `myComplexTypeB` -Deklaration auf einen einfachen Inhalt zu beschränken, wird nicht unterstützt. Daher schlägt die Erstellung der folgenden XML-Schemaauflistung fehl:  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ns" xmlns:ns="http://ns"  
xmlns:ns1="http://ns1">  
  
    <complexType name="myComplexTypeA" mixed="true">  
        <sequence>  
            <element name="a" type="string" minOccurs="0"/>  
            <element name="b" type="string" minOccurs="0" maxOccurs="23"/>  
        </sequence>  
    </complexType>  
  
    <complexType name="myComplexTypeB">  
        <simpleContent>  
            <restriction base="ns:myComplexTypeA">  
                <simpleType>  
                    <restriction base="int">  
                        <minExclusive value="25"/>  
                    </restriction>  
                </simpleType>  
            </restriction>  
        </simpleContent>  
    </complexType>  
</schema>  
'  
GO  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anforderungen und Einschränkungen für XML-Schemaauflistungen auf dem Server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
