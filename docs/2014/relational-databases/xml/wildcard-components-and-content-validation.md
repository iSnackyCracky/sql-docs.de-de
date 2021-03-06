---
title: Platzhalterkomponenten und Inhaltsüberprüfung | Microsoft-Dokumentation
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
- wildcard components [XML]
- content validation [XML]
ms.assetid: ffa7d974-3645-446c-8425-f0b22b6b060a
caps.latest.revision: 12
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 7977b2590d833f87cc7703d8424f1aacaac54546
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37189957"
---
# <a name="wildcard-components-and-content-validation"></a>Platzhalterkomponenten und Inhaltsüberprüfung
  Platzhalterkomponenten werden verwendet, um die Flexibilität der zulässigen Inhalte in einem Inhaltsmodell zu erhöhen. Diese Komponenten werden in der XSD-Sprache auf folgende Weise unterstützt:  
  
-   Elementplatzhalterkomponenten. Diese werden durch das **\<xsd:any>**-Element dargestellt.  
  
-   Attributplatzhalterkomponenten. Diese werden durch das **\<xsd:anyAttribute>**-Element dargestellt.  
  
 Beide Platzhalterzeichenelemente **\<xsd:any>** und **\<xsd: anyAttribute >** unterstützen die Verwendung eines **processContents** Attributs. Auf diese Weise können Sie einen Wert angeben, der angibt, wie XML-Anwendungen die Überprüfung des Dokumentinhalts durchführen, der diesen Platzhalterzeichenelementen zugeordnet ist. Die folgenden Werte und Auswirkungen werden bereitgestellt:  
  
-   Der **strict** -Wert gibt an, dass der Inhalt vollständig überprüft wird.  
  
-   Der **skip** -Wert gibt an, dass der Inhalt nicht überprüft wird.  
  
-   Der **lax** -Wert gibt an, dass nur Elemente und Attribute überprüft werden, für die Schemadefinitionen verfügbar sind.  
  
## <a name="lax-validation-and-xsanytype-elements"></a>Lax-Überprüfung und xs:anyType-Elemente  
 Die XML-Schemaspezifikation verwendet die **lax** -Überprüfung für Elemente des **anyType** -Datentyps. Da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] die "lax"-Überprüfung nicht unterstützte, wurde die strict-Überprüfung für Elemente des **anyType**-Datentyps verwendet. Ab [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]wird die lax-Überprüfung unterstützt. Inhalt der Elemente des Typs **anyType** wird mit lax-Überprüfung überprüft.  
  
 Das folgende Beispiel veranschaulicht die laxÜberprüfung. Das Schemaelement `e` weist den Typ **anyType** auf. Im Beispiel werden typisierte **xml** -Variablen erstellt und die **strict** -Überprüfung des Elements vom Typ anyType veranschaulicht.  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"   
        targetNamespace="http://ns">  
   <element name="e" type="anyType"/>  
   <element name="a" type="byte"/>  
   <element name="b" type="string"/>  
 </schema>'  
GO  
```  
  
 Das folgende Beispiel ist erfolgreich, weil die Überprüfung von `<e>` erfolgreich ist:  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>1</a><b>data</b></e>'  
GO  
```  
  
 Das folgende Beispiel ist erfolgreich. Die Instanz wird akzeptiert, obwohl kein `<c>` -Element im Schema definiert wird:  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>1</a><c>Wrong</c><b>data</b></e>'  
GO  
```  
  
 Die XML-Instanz im folgenden Beispiel wird abgelehnt, weil die Definition des `<a>` -Elements keinen Zeichenfolgenwert zulässt.  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>Wrong</a><b>data</b></e>'  
SELECT @var  
GO  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Anforderungen und Einschränkungen für XML-Schemaauflistungen auf dem Server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
