---
title: Transformation für Datenkonvertierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataconversiontrans.f1
helpviewer_keywords:
- converting data types [Integration Services]
- Data Conversion transformation
- data types [Integration Services], converting
ms.assetid: fd515bbc-6f49-4d0c-ae7f-6ea3c3f24a1c
caps.latest.revision: 52
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 5b9bc5c7e4845adbc15d2e73d45ea85ff851084d
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37207540"
---
# <a name="data-conversion-transformation"></a>Transformation für Datenkonvertierung
  Die Transformation für Datenkonvertierung konvertiert die Daten in einer Eingabespalte in einen anderen Datentyp und kopiert sie dann in eine neue Ausgabespalte. Beispielsweise kann ein Paket Daten aus mehreren Quellen extrahieren und anschließend mithilfe dieser Transformation Spalten in den für den Zieldatenspeicher erforderlichen Datentyp konvertieren. Für eine einzelne Eingabespalte können mehrere Konvertierungen ausgeführt werden.  
  
 Mithilfe dieser Transformation kann ein Paket die folgenden Datenkonvertierungstypen ausführen:  
  
-   Ändern des Datentyps. Weitere Informationen finden Sie unter [Integration Services Datentypen](../integration-services-data-types.md).  
  
    > [!NOTE]  
    >  Falls Sie Daten in einen date- oder datetime-Datentyp konvertieren, weist das Datum in der Ausgabespalte das ISO-Format auf, auch wenn für das Gebietsschema ein anderes Format angegeben ist.  
  
-   Festlegen der Spaltenlänge der Zeichenfolgendaten sowie der Genauigkeit und der Dezimalstellenanzahl für numerische Daten. Weitere Informationen finden Sie unter [Genauigkeit, Dezimalstellen und Länge &#40;Transact-SQL&#41;](/sql/t-sql/data-types/precision-scale-and-length-transact-sql).  
  
-   Eingeben einer Codepage. Weitere Informationen finden Sie unter [Comparing String Data](../comparing-string-data.md).  
  
    > [!NOTE]  
    >  Beim Kopieren zwischen Spalten mit einem Zeichenfolgen-Datentyp müssen die beiden Spalten die gleiche Codepage verwenden.  
  
 Falls die Länge einer Ausgabespalte von Zeichenfolgendaten kürzer als die Länge der entsprechenden Eingabespalte ist, werden die Ausgabedaten abgeschnitten. Weitere Informationen finden Sie unter [Fehlerbehandlung in Daten](../error-handling-in-data.md).  
  
 Diese Transformation weist eine Eingabe, eine Ausgabe und eine Fehlerausgabe auf.  
  
## <a name="related-tasks"></a>Related Tasks  
 Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen. Weitere Informationen zum Verwenden der Transformation für Datenkonvertierung im SSIS-Designer finden Sie unter [Konvertieren von Daten in einen anderen Datentyp mithilfe der Transformation für Datenkonvertierung](data-conversion-transformation.md) und [Transformations-Editor für Datenkonvertierung](../../data-conversion-transformation-editor.md). Weitere Informationen zum programmgesteuerten Festlegen der Eigenschaften dieser Transformation finden Sie unter [Allgemeine Eigenschaften](../../common-properties.md) und [Benutzerdefinierte Eigenschaften von Transformationen](transformation-custom-properties.md).  
  
## <a name="related-content"></a>Verwandte Inhalte  
 Blogeintrag, [Performance Comparison between Data Type Conversion Techniques in SSIS 2008](http://go.microsoft.com/fwlink/?LinkId=220823), auf blogs.msdn.com.  
  
## <a name="see-also"></a>Siehe auch  
 [Die schnelle Analyse](../../fast-parse.md)   
 [Datenfluss](../data-flow.md)   
 [SQL Server Integration Services-Transformationen](integration-services-transformations.md)  
  
  
