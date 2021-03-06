---
title: Beispiele für Filtergleichungen (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- filtering data [Reporting Services], filter equation examples
ms.assetid: 66bec93d-7c3b-4d4a-8cb6-7a7bb2f34ec6
caps.latest.revision: 18
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: 5bcb1e50fbc615a95c202035e2e6c5d7320f5df9
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37317871"
---
# <a name="filter-equation-examples-report-builder-and-ssrs"></a>Beispiele für Filtergleichungen (Berichts-Generator und SSRS)
  Zum Erstellen eines Filters müssen Sie mindestens eine Filtergleichung angeben. Eine Filtergleichung schließt einen Ausdruck, einen Datentyp, einen Operator und einen Wert ein. Dieses Thema enthält Beispiele für häufig verwendete Filter.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="filter-examples"></a>Beispiele für Filter  
 In der folgenden Tabelle werden Beispiele für Filtergleichungen dargestellt, die andere Datentypen und andere Operatoren verwenden. Der Bereich für den Vergleich wird von dem Berichtselement bestimmt, für das ein Filter definiert wird. Beispiel: Bei einem für ein Dataset definierten Filter bezeichnet **Erste % 10** die ersten 10 Prozent der Werte im Dataset. Im Falle eines für eine Gruppe definierten Filters bedeutet **Erste % 10** die ersten 10 Prozent der Werte in der Gruppe.  
  
|Einfacher Ausdruck|Datentyp|Operator|value|Description|  
|-----------------------|---------------|--------------|-----------|-----------------|  
|`[SUM(Quantity)]`|`Integer`|`>`|`7`|Schließt Datenwerte ein, die größer als 7 sind.|  
|`[SUM(Quantity)]`|`Integer`|`TOP N`|`10`|Schließt die ersten 10 Datenwerte ein.|  
|`[SUM(Quantity)]`|`Integer`|`TOP %`|`20`|Schließt die ersten 20 % der Datenwerte ein.|  
|`[Sales]`|`Text`|`>`|`=CDec(100)`|Schließt alle Werte des Typs System.Decimal (SQL-Datentyp "money") größer als $100 ein.|  
|`[OrderDate]`|`DateTime`|`>`|`2008-01-01`|Schließt alle Datumsangaben vom 1. Januar 2008 bis zum gegenwärtigen Datum ein.|  
|`[OrderDate]`|`DateTime`|`BETWEEN`|`2008-01-01`<br /><br /> `2008-02-01`|Schließt Datumsangaben vom 1. Januar 2008 bis zum 1. Februar 2008 einschließlich ein.|  
|`[Territory]`|`Text`|`LIKE`|`*east`|Alle Gebietsnamen, die auf "east" enden.|  
|`[Territory]`|`Text`|`LIKE`|`%o%th*`|Alle Gebietsnamen, die mit "North" und "South" beginnen.|  
|`=LEFT(Fields!Subcat.Value,1)`|`Text`|`IN`|`B, C, T`|Alle Unterkategoriewerte, die mit B, C oder T beginnen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Berichtsparameter &#40;Berichts-Generator und Berichts-Designer&#41;](report-parameters-report-builder-and-report-designer.md)   
 [Hinzufügen von Datasetfiltern, Datenbereichsfiltern und Gruppenfiltern &#40;Berichts-Generator und SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md)   
 [Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md)   
 [Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md)   
 [Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md)  
  
  
