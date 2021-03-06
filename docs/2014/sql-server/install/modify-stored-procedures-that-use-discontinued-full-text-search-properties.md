---
title: Ändern von gespeicherten Prozeduren nicht mehr unterstützte Volltextsuche-Eigenschaften verwenden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- discontinued properties [Full-Text Search]
- stored procedures [Full-Text Search]
ms.assetid: 8d9392d9-a9ba-4378-84e4-59f516b67ddb
caps.latest.revision: 20
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: bd8fda3e9d1968d7dcc480931cf4ae8492bd4686
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37265806"
---
# <a name="modify-stored-procedures-that-use-discontinued-full-text-search-properties"></a>Ändern gespeicherter Prozeduren, die nicht mehr unterstützte Volltextsuche-Eigenschaften verwenden
  Um sicherzustellen, dass Ihre gespeicherten Prozeduren korrekt funktionieren, sollten Sie vorhandene Prozeduren bearbeiten und volltextbezogene Eigenschaften und Einstellungen entfernen, die entfernt wurden oder nicht mehr unterstützt werden.  
  
## <a name="component"></a>Komponente  
 Volltextsuche  
  
## <a name="description"></a>Description  
 Die folgenden Eigenschaften und Einstellungen der Volltextsuche wurden entfernt.  
  
-   **DataTimeout**  
  
-   **connecttimeout**  
  
-   **Clean_up**  
  
-   **LogSize**  
  
 Die folgenden Eigenschaften und Einstellungen der Volltextsuche wurden entfernt bzw. werden nicht mehr unterstützt.  
  
-   'Path' des Volltextkatalogs. Der Volltextkatalog ist ein logisches Objekt ohne einen spezifischen Dateipfad im System.  
  
-   Das Aktivieren/Deaktivieren von SP_FULLTEXT_DATABASE hat keine Wirkung mehr, da Datenbanken in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] jederzeit und standardmäßig für die Volltextsuche aktiviert sind.  
  
## <a name="corrective-action"></a>Korrekturmaßnahme  
 Ändern Sie die gespeicherten Prozeduren, um diese Eigenschaften zu entfernen.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit dem Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
