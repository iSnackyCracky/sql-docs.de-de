---
title: Berechnungen (SSAS – tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 738816e3-0e1d-44a5-8d1b-81068dce8ac0
caps.latest.revision: 18
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 0628ad4360199ac1710ac9669e27c214287a0e9c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37261362"
---
# <a name="calculations-ssas-tabular"></a>Berechnungen (SSAS – tabellarisch)
  Nachdem Sie Daten in das Modell importiert haben, können Sie Berechnungen hinzufügen, um Daten zu aggregieren, filtern, erweitern, kombinieren und schützen. Tabellarische Modelle verwenden Data Analysis Expressions (DAX), eine neue Formelsprache zum Erstellen von benutzerdefinierten Berechnungen. In tabellarischen Modellen werden die Berechnungen, die Sie mit DAX-Formeln erstellen, in *berechneten Spalten*, *Measures*und *Zeilenfiltern*verwendet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Thema|Description|  
|-----------|-----------------|  
|[Grundlegendes zu DAX in tabellarischen Modellen &#40;SSAS – tabellarisch&#41;](understanding-dax-in-tabular-models-ssas-tabular.md)|Beschreibt die Data Analysis Expressions (DAX)-Formelsprache, die zum Erstellen von Berechnungen für berechnete Spalten, Measures und Zeilenfilter in tabellarischen Modellen verwendet wird.|  
|[Formelkompatibilität im DirectQuery-Modus](../dax-formula-compatibility-in-directquery-mode-ssas-2014.md)|Beschreibt die Unterschiede und listet die Funktionen auf, die nicht im DirectQuery-Modus unterstützt werden. Des Weiteren werden die Funktionen aufgelistet, die unterstützt werden, aber andere Ergebnisse zurückgeben können.|  
|[Data Analysis Expressions &#40;DAX&#41; Verweis](https://msdn.microsoft.com/library/gg413422(v=sql.120).aspx)|Dieser Abschnitt enthält ausführliche Beschreibungen der DAX-Syntax, -Operatoren und -Funktionen.|  
  
> [!NOTE]  
>  Dieser Abschnitt enthält keine Schritt-für-Schritt-Anweisungen zum Erstellen von Berechnungen. Da Berechnungen in berechneten Spalten, Measures und Zeilenfiltern (in Rollen) angegeben werden, werden die Anweisungen zum Erstellen von DAX-Formeln in Aufgaben für diese Funktionen bereitgestellt. Weitere Informationen finden Sie unter [Erstellen einer berechneten Spalte &#40;SSAS – tabellarisch&#41;](ssas-calculated-columns-create-a-calculated-column.md), [Erstellen und Verwalten von Measures &#40;SSAS – tabellarisch&#41;](measures-ssas-tabular.md) und [Erstellen und Verwalten von Rollen &#40;SSAS – tabellarisch&#41;](roles-ssas-tabular.md).  
  
> [!NOTE]  
>  Obwohl DAX auch zum Abfragen eines tabellarischen Modells verwendet werden kann, wird in den Themen dieses Abschnitts schwerpunktmäßig das Erstellen von Berechnungen mithilfe von DAX-Formeln behandelt.  
  
  
