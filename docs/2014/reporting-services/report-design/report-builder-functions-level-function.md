---
title: Dimensionsfunktion (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 41235402-bb9e-4cb7-b91e-431e77db19cf
caps.latest.revision: 7
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: 027ccec12f08efddc9b48c56ad7ed2f22ec5b15b
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37155751"
---
# <a name="level-function-report-builder-and-ssrs"></a>Level-Funktion (Berichts-Generator und SSRS)
  Gibt die aktuelle Ebene in einer rekursiven Hierarchie zurück.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a>Syntax  
  
```  
  
Level(scope)  
```  
  
#### <a name="parameters"></a>Parameter  
 *Bereich*  
 (`String`) (optional). Der Name eines Datasets, einer Gruppe oder eines Datenbereichs mit den Berichtselementen, auf die die Aggregatfunktion anzuwenden ist. Wenn *scope* nicht angegeben ist, wird der aktuelle Bereich verwendet.  
  
## <a name="return-type"></a>Rückgabetyp  
 Gibt eine `Integer`. Wenn *Bereich* gibt eine Dataset oder einem Datenbereich oder eine nicht rekursive Gruppierung (d. h. eine Gruppierung ohne `Parent` Element), `Level` gibt 0 zurück. Wenn *scope* weggelassen wird, wird die Ebene des aktuellen Bereichs zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Der von der `Level`-Funktion zurückgegebene Wert ist nullbasiert, d. h., die erste Ebene in einer Hierarchie hat den Wert 0.  
  
 Die `Level`-Funktion kann verwendet werden, um den Einzug in einer rekursiven Hierarchie, z. B. einer Mitarbeiterliste, bereitzustellen.  
  
 Weitere Informationen zu rekursiven Hierarchien finden Sie unter [Erstellen von rekursiven Hierarchiegruppen (Berichts-Generator und SSRS)](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Codebeispiel wird die Zeilenebene in der Employees-Gruppe bereitgestellt:  
  
```  
=Level("Employees")  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md)   
 [Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md)   
 [Datentypen in Ausdrücken (Berichts-Generator und SSRS)](expressions-report-builder-and-ssrs.md)   
 [Ausdrucksbereich für Gesamtwerte, Aggregate und integrierte Auflistungen &#40;Berichts-Generator und SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
