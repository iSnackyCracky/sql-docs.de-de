---
title: Geben Sie die Objektanzahl (Aggregationsentwurfs-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.calculatingobjectcounts.f1
ms.assetid: 305d9d79-d1ab-4704-a7b5-3283842b3996
caps.latest.revision: 28
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 4a2040623e235b79a16c767062655deac81d6271
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37319320"
---
# <a name="specify-object-counts-aggregation-design-wizard"></a>Objektanzahl angeben (Aggregationsentwurfs-Assistent)
  Auf der Seite **Objektanzahl angeben** können Sie die Anzahl der Objekte im Cube automatisch berechnen lassen oder die geschätzte Anzahl manuell eingeben. Mithilfe dieser Objektanzahl ermittelt der Aggregationsentwurfs-Assistent die geschätzten Speicheranforderungen.  
  
## <a name="options"></a>Tastatur  
 **Cubeobjekte**  
 Zeigt die Dimensionen und Attribute im Cube an. Nur die Attribute, die nicht ihre `AggregationUsage` -Eigenschaftensatz auf `None` in die **Aggregationsverwendung überprüfen** Seite des Assistenten angezeigt werden, da dies die einzigen Attribute sind die Anzahl angegeben werden muss.  
  
 **Geschätzte Anzahl**  
 Zeigt die geschätzte Anzahl der Zeilen in der Measuregruppe sowie die geschätzte Anzahl der Attributelemente in den Datenbankdimensionen an. Sie können einen Wert eingeben, der als geschätzte Anzahl verwendet werden soll, oder die Werte für die geschätzte Anzahl berechnen. Um die Anzahlwerte zu berechnen, geben Sie `0` in das Feld und klicken Sie dann auf **Anzahl**. Felder, in denen bereits eine Anzahl angezeigt wird, werden nicht aktualisiert.  
  
 **Anzahl von Partitionen**  
 (Optional) Geben Sie die geschätzte Anzahl von Zeilen in der Measuregruppe sowie die geschätzte Anzahl von Attributelementen in den Partitionen ein.  
  
 **Count**  
 Berechnet und füllt für alle leeren Felder die Werte in der Spalte **Geschätzte Anzahl** neu. Felder, in denen bereits eine Anzahl angezeigt wird, werden nicht aktualisiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Aggregation Design-Assistent F1-Hilfe](aggregation-design-wizard-f1-help.md)   
 [Analysis Services-Assistenten &#40;mehrdimensionale Daten&#41;](analysis-services-wizards-multidimensional-data.md)  
  
  
