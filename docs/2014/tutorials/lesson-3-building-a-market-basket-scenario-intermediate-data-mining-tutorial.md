---
title: 'Lektion 3: Erstellen eines Warenkorbszenarios (Datamining-Lernprogramm für fortgeschrittene) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- association algorithms [Analysis Services]
- nested tables
- tutorials [Data Mining]
ms.assetid: 651eef38-772e-4d97-af51-075b1b27fc5a
caps.latest.revision: 27
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 0c03f8b54859a960479d78f1d0de7a0a30836347
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37255122"
---
# <a name="lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial"></a>Lektion 3: Erstellen eines Warenkorbszenarios (Data Mining-Lernprogramm für Fortgeschrittene)
  Die marketingabteilung von [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] verbessern die Unternehmensportal-Website zum Heraufstufen Cross-Selling von nutzen möchte. Als Teil des Websiteupdates soll die Möglichkeit bestehen, anhand von Produkten, die sich bereits im Onlinewarenkorb eines Kunden befinden, Produkte vorherzusagen, die der Kunde möglicherweise noch kaufen möchte. Die Marketingabteilung möchte außerdem das Kaufverhalten von Kunden besser verstehen, um die Website so zu gestalten, dass Artikel, die tendenziell zusammen gekauft werden, auch zusammen angezeigt werden. Die Marketingabteilung hat erfahren, dass Data Mining besonders nützlich für diese Art von *Warenkorbanalyse* ist, und bittet Sie, ein Data Mining-Modell zu entwickeln.  
  
 Nach Abschluss der Aufgaben in dieser Lektion verfügen Sie über ein Miningmodell, das Gruppen von Artikeln aus vergangenen Kundentransaktionen anzeigt. Außerdem können Sie das Miningmodell verwenden, um weitere Artikel vorherzusagen, die ein Kunde möglicherweise kaufen möchte.  
  
 Zum Ausführen der Aufgaben in dieser Lektion verwenden Sie die Lösung und Datenquelle, die Sie in der ersten Lektion erstellt die [Data Mining Tutorial für fortgeschrittene &#40;Analysis Services – Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md). Sie ändern diese Lösung, indem Sie eine Datenquellensicht hinzufügen, die Tabellen über den Kunden enthält, einschließlich einer geschachtelten Tabelle von Kundenbestellungen.  Anschließend erstellen Sie ein Miningmodell, dass den Microsoft Association Rules-Algorithmus verwendet, der für Warenkorbszenarien geeignet ist.  
  
 Diese Lektion enthält die folgenden Themen:  
  
-   [Hinzufügen einer Datenquellensicht mit geschachtelten Tabellen &#40;Datamining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)  
  
-   [Erstellen einer Warenkorbstruktur und eines Modells &#40;Datamining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/creating-a-market-basket-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [Ändern und Verarbeiten der Market Basket-Modells &#40;Datamining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/modify-process-market-basket-model-intermediate-data-mining-tutorial.md)  
  
-   [Durchsuchen der Market Basket-Modellen &#40;Datamining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/exploring-the-market-basket-models-intermediate-data-mining-tutorial.md)  
  
-   [Filtern einer geschachtelten Tabelle in einem Miningmodell &#40;Datamining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/filtering-a-nested-table-in-a-mining-model-intermediate-data-mining-tutorial.md)  
  
-   [Vorhersagen von Zuordnungen &#40;Datamining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/predicting-associations-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a>Nächste Aufgabe in dieser Lektion  
 [Hinzufügen einer Datenquellensicht mit geschachtelten Tabellen &#40;Datamining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a>Alle Lektionen  
 [Lektion 1: Erstellen der mittleres Datamining-Lösung &#40;Datamining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [Lektion 2: Erstellen eines Planungserstellungsszenarios &#40;Datamining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 Lektion 3: Warenkorbszenario (Data Mining-Tutorial für Fortgeschrittene)  
  
 [Lektion 4: Erstellen eines Sequenzclusterszenarios &#40;Datamining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [Lektion 5: Erstellen von neuronalen Netzwerk- und logistischen Regressionsmodellen &#40;Datamining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Lernprogramm zu Datamining-Grundlagen](../../2014/tutorials/basic-data-mining-tutorial.md)   
 [Lektion 2: Erstellen eines Planungserstellungsszenarios &#40;Datamining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)   
 [Lektion 4: Erstellen eines Sequenzclusterszenarios &#40;Datamining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
  
