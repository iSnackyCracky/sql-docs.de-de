---
title: 'Angeben des SQL: Inverse-Attributs für SQL: Relationship (SQLXML 4.0) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- sql:relationship
- bulk load [SQLXML]
- inverse attribute
- relationships [SQLXML], inverse orders
- relationship annotation
- XSD schemas [SQLXML], relationships
- annotated XSD schemas, relationships
- updategrams [SQLXML], relationships
- sql:inverse
ms.assetid: 08904cbd-9c86-493d-90c3-f5e1d13ce59d
caps.latest.revision: 26
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: ac3bf643dc5237b6bbdc819a170ae7b8f2435d00
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37194920"
---
# <a name="specifying-the-sqlinverse-attribute-on-sqlrelationship-sqlxml-40"></a>Angeben des sql:inverse-Attributs für sql:relationship (SQLXML 4.0)
  Das `sql:inverse`-Attribut ist nur dann nützlich, wenn das XSD-Schema zum Massenladen oder von einem Updategram verwendet wird. Die `sql:inverse` -Attribut angegeben werden, auf die  **\<SQL: Relationship >** Element. In Updategrams interpretiert die Updategramlogik das Schema beim Bestimmen der Tabellen und Spalten, die durch den Updategramvorgang aktualisiert werden. Die im Schema angegebenen Über-/Unterordnungsbeziehungen legen die Reihenfolge fest, in der die Datensätze modifiziert (eingefügt oder gelöscht) werden.  
  
 Wenn ein XSD-Schema gegeben ist, in dem die Über-/Unterordnungsbeziehung invers zur Primär-/Fremdschlüssel-Beziehung zwischen den zugehörigen Datenbankspalten angegeben ist, dann schlägt der Updategramvorgang zum Einfügen oder Löschen wegen der Primär-/Fremdschlüsselverletzung fehl. In solchen Fällen die `sql:inverse` -Attribut angegeben ist (`sql:inverse="true"`) in der  **\<SQL: Relationship >** -Element, und das Updategram Logik Gegenstücke die Interpretation der der angegebenen über-/ unterordnungsbeziehung im Schema.  
  
 Das `sql:inverse`-Attribut akzeptiert einen booleschen Wert (0 = false, 1 = true). Zulässig sind die Werte 0, 1, true und false.  
  
 Für eine funktionierende Beispiel mit der `sql:inverse` Anmerkung, finden Sie unter [angeben eines Zuordnungsschemas in einem Updategram](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Angeben von Beziehungen mithilfe von SQL: Relationship &#40;SQLXML 4.0&#41;](specifying-relationships-using-sql-relationship-sqlxml-4-0.md)  
  
  
