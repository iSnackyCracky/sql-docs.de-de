---
title: STArea (geometry-Datentyp) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- STArea (geometry Data Type)
- STArea_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STArea (geometry Data Type)
ms.assetid: a7dd6083-c649-4ac3-885d-1234e0db62f1
caps.latest.revision: 25
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 60d79d40bfa4c7499c909e34c23604e378996f36
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38004892"
---
# <a name="starea-geometry-data-type"></a>STArea (geometry-Datentyp)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  Gibt die gesamte Oberfläche einer **geometry**-Instanz zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
.STArea ( )  
```  
  
## <a name="return-types"></a>Rückgabetypen  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Rückgabetyp: **float**  
  
 CLR-Rückgabetyp: **SqlDouble**  
  
## <a name="remarks"></a>Remarks  
 `STArea()` gibt 0 (null) zurück, wenn eine **geometry**-Instanz nur null- und eindimensionale Abbildungen enthält oder leer ist. `STArea()` gibt **NULL** zurück, wenn die **geometry**-Instanz nicht initialisiert wurde.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-computing-the-area-of-a-polygon-instance"></a>A. Berechnen der Fläche einer Polygoninstanz  
 Im folgenden Beispiel wird eine `Polygon``geometry`-Instanz erstellt, und die Fläche des Polygons wird berechnet.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POLYGON((0 0, 3 0, 3 3, 0 3, 0 0),(2 2, 2 1, 1 1, 1 2, 2 2))', 0);  
SELECT @g.STArea();  
```  
  
### <a name="b-computing-the-area-of-a-curvepolygon-instance"></a>B. Berechnen der Fläche einer CurvePolygon-Instanz  
 Im folgenden Beispiel wird die Fläche einer `CurvePolygon`-Instanz berechnet.  
  
```
 DECLARE @g geometry;  
 SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 2, 2 0, 4 2, 4 2, 0 2))');  
 SELECT @g.STArea() AS Area;
 ```  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [OGC-Methoden für geometry-Instanzen](../../t-sql/spatial-geometry/ogc-methods-on-geometry-instances.md)  
  
  
