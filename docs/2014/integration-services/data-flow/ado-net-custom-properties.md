---
title: Benutzerdefinierte Eigenschaften von ADO.NET | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: e062a9ab-1e6b-4061-845a-4f8a0552b09d
caps.latest.revision: 8
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 177e0cda681e81082e5b52fc324880f04a5d608c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37195630"
---
# <a name="ado-net-custom-properties"></a>Benutzerdefinierte Eigenschaften von ADO.NET
  **Benutzerdefinierte Eigenschaften von Quellen**  
  
 Die ADO NET-Quelle verfügt sowohl über benutzerdefinierte Eigenschaften als auch über die Eigenschaften, die allen Datenflusskomponenten gemeinsam sind.  
  
 In der folgenden Tabelle werden die benutzerdefinierten Eigenschaften der ADO NET-Quelle beschrieben. Alle Eigenschaften weisen Lese-/Schreibzugriff auf.  
  
|Eigenschaftenname|Datentyp|Description|  
|-------------------|---------------|-----------------|  
|CommandTimeout|Zeichenfolge|Ein Wert, der die Anzahl der Sekunden angibt, bevor für den SQL-Befehl ein Timeout eintritt. Der Wert 0 gibt an, dass bei dem Befehl nie ein Timeout eintritt.|  
|SqlCommand|Zeichenfolge|Die SQL-Anweisung, die die ADO NET-Quelle zum Extrahieren von Daten verwendet.<br /><br /> Während das Paket geladen wird, können Sie diese Eigenschaft dynamisch mit der SQL-Anweisung aktualisieren, die die ADO NET-Quelle verwendet. Weitere Informationen finden Sie unter [Integration Services-Ausdrücke &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md) und [Verwenden von Eigenschaftsausdrücken in Paketen](../expressions/use-property-expressions-in-packages.md).|  
|AllowImplicitStringConversion|Boolean|Ein Wert, der angibt, ob Folgendes eintritt:<br /><br /> Es wird kein Validierungsfehler generiert, wenn eine Unstimmigkeit zwischen externen Metadatentypen und Ausgabespaltentypen in Form von Zeichenfolgen auftritt (DT_WSTR oder DT_NTEXT).<br /><br /> Implizite Konvertierung externer Metadatentypen in den string-Datentyp, den die Ausgabespalte verwendet.<br /><br /> <br /><br /> Der Standardwert ist TRUE.<br /><br /> Weitere Informationen finden Sie unter [ADO NET Source](ado-net-source.md).|  
  
 Die Ausgabe und die Ausgabespalten der ADO NET-Quelle verfügen nicht über benutzerdefinierte Eigenschaften.  
  
 Weitere Informationen finden Sie unter [ADO NET Source](ado-net-source.md).  
  
 **Benutzerdefinierte Eigenschaften von Zielen**  
  
 Das [!INCLUDE[vstecado](../../includes/vstecado-md.md)] -Ziel verfügt sowohl über benutzerdefinierte Eigenschaften als auch über die Eigenschaften, die allen Datenflusskomponenten gemeinsam sind.  
  
 In der folgenden Tabelle werden die benutzerdefinierten Eigenschaften des [!INCLUDE[vstecado](../../includes/vstecado-md.md)] -Ziels beschrieben. Alle Eigenschaften weisen Lese-/Schreibzugriff auf. Diese Eigenschaften sind nicht im **ADO.NET-Ziel-Editor**verfügbar, können jedoch mit dem **Erweiterten Editor**festgelegt werden.  
  
|Eigenschaft|Datentyp|Description|  
|--------------|---------------|-----------------|  
|BatchSize|Integer|Die Anzahl von Zeilen in einem Batch, die an den Server gesendet wurden. Der Wert **0** gibt an, dass die Batchgröße mit der internen Puffergröße übereinstimmt. Der Standardwert dieser Eigenschaft ist **0**.|  
|CommandTimeOut|Integer|Die maximale Ausführungsdauer in Sekunden, bevor ein Timeout für den SQL-Befehl eintritt. Der Wert **0** gibt einen unbegrenzten Zeitraum an. Der Standardwert dieser Eigenschaft ist **0**.|  
|TableOrViewName|Zeichenfolge|Name der Zieltabelle oder -sicht.|  
  
 Weitere Informationen finden Sie unter [ADO NET Destination](ado-net-destination.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Common Properties](../common-properties.md)  
  
  
