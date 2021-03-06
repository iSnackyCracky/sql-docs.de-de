---
title: 'Analysis Services-Tutorial – Lektion 5: Erstellen von berechneten Spalten | Microsoft-Dokumentation'
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: tutorial
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 476eca07ed1367141372586ca13bd2a93d9d8105
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "37973050"
---
# <a name="create-calculated-columns"></a>Erstellen von berechneten Spalten

[!INCLUDE[ssas-appliesto-sql2017-later-aas](../../includes/ssas-appliesto-sql2017-later-aas.md)]

In dieser Lektion erstellen Sie Daten in Ihrem Modell durch Hinzufügen von berechneten Spalten. Sie können berechnete Spalten (wie benutzerdefinierte Spalten) erstellen beim Abrufen von Daten verwenden, mit dem Abfrage-Editor oder einem späteren Zeitpunkt in der Modell-Designer, wie Sie in diesem Tutorial. Weitere Informationen finden Sie unter [berechnete Spalten](../tabular-models/ssas-calculated-columns.md).
  
Sie erstellen fünf neue berechnete Spalten in drei verschiedenen Tabellen. Die Schritte unterscheiden sich leicht für die einzelnen Aufgaben sehen, dass es verschiedene Möglichkeiten zum Erstellen von Spalten und benennen die Spalten an verschiedenen Positionen in einer Tabelle platzieren.  

Diese Lektion ist auch, wo Sie zuerst Data Analysis Expressions (DAX) verwenden. DAX ist eine spezielle Sprache zum Erstellen von extrem anpassbarer formelausdrücken für tabellarische Modelle. In diesem Tutorial verwenden Sie DAX zum Erstellen von berechneten Spalten, Measures und rollenfiltern. Weitere Informationen finden Sie unter [DAX in tabellarischen Modellen](../tabular-models/understanding-dax-in-tabular-models-ssas-tabular.md). 
  
Geschätzte Zeit zum Bearbeiten dieser Lektion: **15 Minuten**  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  

Dieser Artikel ist Teil einer Tutorials zur tabellenmodellierung, das in der Reihenfolge absolviert werden sollte. Vor dem Ausführen der Aufgaben in dieser Lektion an, Sie sollten die vorherige Lektion abgeschlossen haben: [Lektion 4: Erstellen von Beziehungen](../tutorial-tabular-1400/as-lesson-4-create-relationships.md). 
  
## <a name="create-calculated-columns"></a>Erstellen von berechneten Spalten  
  
#### <a name="create-a-monthcalendar-calculated-column-in-the-dimdate-table"></a>Erstellen einer berechneten MonthCalendar-Spalteninhalts in der DimDate-Tabelle  
  
1.  Klicken Sie auf die **Modell** Menü > **Modellansicht** > **Data Source View**.  
  
    Berechnete Spalten können nur mit dem Modell-Designer in der Datensicht erstellt werden.  
  
2.  Klicken Sie im Modell-Designer auf die **DimDate** Tabelle (Registerkarte).  
  
3.  Mit der rechten Maustaste die **"calendarquarter"** Spaltenüberschrift, und klicken Sie dann auf **Spalte einfügen**.  
  
    Eine neue Spalte mit dem Namen **Calculated Column 1** wird links von der Spalte **Calendar Quarter** eingefügt.  
  
4.  Geben Sie in der Bearbeitungsleiste über der Tabelle die folgende DAX-Formel: AutoVervollständigen unterstützt Sie beim Geben Sie den vollqualifizierten Namens von Spalten und Tabellen und listet die Funktionen, die verfügbar sind.  
  
    ```  
    =RIGHT(" " & FORMAT([MonthNumberOfYear],"#0"), 2) & " - " & [EnglishMonthName]  
    ``` 
  
    Werte werden dann für alle Zeilen in der berechneten Spalte eingetragen. Wenn Sie in der Tabelle nach unten scrollen, sehen Sie sich, dass Zeilen unterschiedliche Werte für diese Spalte basierend auf den Daten in den einzelnen Zeilen haben können.    
  
5.  Benennen Sie diese Spalte in **MonthCalendar**. 

    ![als lesson5 newcolumn](../tutorial-tabular-1400/media/as-lesson5-newcolumn.png) 
  
Das MonthCalendar berechnete Spalte einen sortierbaren Namen für den Monat.  
  
#### <a name="create-a-dayofweek-calculated-column-in-the-dimdate-table"></a>Erstellen Sie eine berechnete DayOfWeek-Spalte in der DimDate-Tabelle  
  
1.  Mit der **DimDate** Tabelle weiterhin aktiv ist, klicken Sie auf die **Spalte** , und klicken Sie dann auf **Add Column**.  
  
2.  Geben Sie in der Bearbeitungsleiste folgende Formel ein:  
    
    ```
    =RIGHT(" " & FORMAT([DayNumberOfWeek],"#0"), 2) & " - " & [EnglishDayNameOfWeek]  
    ```
    
    Wenn Sie mit dem Erstellen der Formel abgeschlossen haben, drücken Sie die EINGABETASTE. Die neue Spalte wird ganz rechts von der Tabelle hinzugefügt.  
  
3.  Benennen Sie die Spalte in **DayOfWeek**.  
  
4.  Klicken Sie auf die Spaltenüberschrift und ziehen Sie dann die Spalte zwischen die **EnglishDayNameOfWeek** Spalte und die **DayNumberOfMonth** Spalte.  
  
    > [!TIP]  
    > Durch das Verschieben von Spalten in der Tabelle wird die Navigation vereinfacht.  
  
Die DayOfWeek berechnete Spalte einen sortierbaren Namen für den Tag der Woche.  
  
#### <a name="create-a-productsubcategoryname-calculated-column-in-the-dimproduct-table"></a>Erstellen einer berechneten ProductSubcategoryName-Spalte in der DimProduct-Tabelle  
  
  
1.  In der **DimProduct** Tabelle einen Bildlauf zum rechten Rand der Tabelle. Beachten Sie, dass die ganz rechts stehende Spalte **Spalte hinzufügen** heißt (in Kursivschrift). Klicken Sie auf die Spaltenüberschrift.  
  
2.  Geben Sie in der Bearbeitungsleiste folgende Formel ein:  
    
    ```
    =RELATED('DimProductSubcategory'[EnglishProductSubcategoryName])  
    ```
  
3.  Benennen Sie die Spalte in **ProductSubcategoryName**.  
  
Die berechnete Spalte "productsubcategoryname" wird verwendet, um eine Hierarchie in der DimProduct-Tabelle zu erstellen, die Daten aus der EnglishProductSubcategoryName-Spalte in der Tabelle "DimProductSubcategory" enthält. Hierarchien können maximal eine Tabelle umfassen. Sie erstellen Hierarchien später in Lektion 9.  
  
#### <a name="create-a-productcategoryname-calculated-column-in-the-dimproduct-table"></a>Erstellen einer berechneten ProductCategoryName-Spalte in der DimProduct-Tabelle  
  
1.  Mit der **DimProduct** Tabelle weiterhin aktiv ist, klicken Sie auf die **Spalte** , und klicken Sie dann auf **Add Column**.  
  
2.  Geben Sie in der Bearbeitungsleiste folgende Formel ein:  
  
    ```
    =RELATED('DimProductCategory'[EnglishProductCategoryName]) 
    ```
    
3.  Benennen Sie die Spalte in **"productcategoryname"**.  
  
Die berechnete Spalte "productcategoryname" wird verwendet, um eine Hierarchie in der DimProduct-Tabelle zu erstellen, die Daten aus der EnglishProductCategoryName-Spalte in der Tabelle "DimProductCategory" enthält. Hierarchien können maximal eine Tabelle umfassen.  
  
#### <a name="create-a-margin-calculated-column-in-the-factinternetsales-table"></a>Erstellen einer berechneten Margin-Spalte in der Tabelle "factinternetsales"  
  
1.  Wählen Sie im Modell-Designer die **"factinternetsales"** Tabelle.  
  
2.  Erstellen Sie eine neue berechnete Spalte zwischen die **"SalesAmount"** Spalte und die **"taxamt"** Spalte.  
  
3.  Geben Sie in der Bearbeitungsleiste folgende Formel ein:  
  
    ```
    =[SalesAmount]-[TotalProductCost]
    ``` 

4.  Benennen Sie die Spalte in **Margin**um.  
 
      ![als lesson5 newmargin](../tutorial-tabular-1400/media/as-lesson5-newmargin.png)
      
    Die berechnete Margin-Spalte wird verwendet, um die Analyse von Gewinnspannen für jeden Verkauf.  
  
## <a name="whats-next"></a>Wie geht es weiter?

[Lektion 6: Erstellen von Measures](../tutorial-tabular-1400/as-lesson-6-create-measures.md).
  
  
  
