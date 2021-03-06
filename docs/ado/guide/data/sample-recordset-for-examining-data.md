---
title: Beispiel-Recordset zum Untersuchen von Daten | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- record location [ADO]
- current record [ADO]
ms.assetid: e770e626-68b1-4ddf-a217-d7b30311e2ee
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 8a6bb3eb784c3979dd136f237c5d153547d30027
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "35272489"
---
# <a name="sample-recordset-for-examining-data"></a>Beispiel-Recordset zum Untersuchen von Daten
Zunächst sehen wir uns die **Recordset** -Objekt zurückgegeben, mit der folgenden SQL-Abfrage, für die Northwind-Beispieldaten Basis in Microsoft SQL Server ausgeführt wird.  
  
```  
SELECT ProductID,ProductName,UnitPrice   
FROM Products   
WHERE CategoryID = 7    
```  
  
 Die resultierenden **Recordset** Objekt enthält alle erzeugt in der Datenbank, die in der folgenden Tabelle gezeigt.  
  
|ProductID|ProductName|UnitPrice|  
|---------------|-----------------|---------------|  
|7|Onkel Bobs Trockenbirnen|30.0000|  
|14|Tofu|23.2500|  
|28|Rssle Sauerkraut|45.6000|  
|51|Manjimup Dried Apples|53.0000|  
|74|Longlife Tofu|10.0000|  
  
 Wenn Sie interessiert, diese Ergebnisse selbst sind, versuchen Sie es im folgende JScript-Beispiel:  
  
-   [JScript-Beispiel zum Zurückgeben eines Recordsets](../../../ado/guide/data/jscript-code-example-to-return-a-recordset.md)
