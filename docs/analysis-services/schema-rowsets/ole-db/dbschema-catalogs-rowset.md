---
title: DBSCHEMA_CATALOGS-Rowset | Microsoft Docs
ms.date: 05/03/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: schema-rowsets
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 61e4de1591752919a5916d6044591bda49b14992
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
ms.locfileid: "34033311"
---
# <a name="dbschemacatalogs-rowset"></a>DBSCHEMA_CATALOGS-Rowset
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Gibt die physischen Attribute an, die Katalogen zugeordnet sind, auf die über das Datenbankverwaltungssystem (Database Management System, DBMS) zugegriffen werden kann.  
  
## <a name="rowset-columns"></a>Rowsetspalten  
 Das **DBSCHEMA_CATALOGS** -Rowset enthält die folgenden Spalten.  
  
|Spaltenname|Typindikator|Länge|Description|  
|-----------------|--------------------|------------|-----------------|  
|**CATALOG_NAME**|**DBTYPE_WSTR**|255|Der Katalogname. Lässt keine NULL-Werte zu.|  
|**DESCRIPTION**|**DBTYPE_WSTR**||Eine lesbare Beschreibung der Tabelle.|  
|**ROLLEN**|**DBTYPE_WSTR**||Eine durch Trennzeichen getrennte Liste von Rollen, zu der der aktuelle Benutzer gehört.<br /><br /> Ein Sternchen (\*) als eine Rolle enthalten ist, wenn der aktuelle Benutzer ein Server- oder Datenbankadministrator ist.<br /><br /> **Username** wird an **ROLES** angefügt, wenn eine der Rollen dynamische Sicherheit verwendet.|  
|**DATE_MODIFIED**|**DBTYPE_DBTIMESTAMP**||Das Datum, an dem der Katalog zuletzt geändert wurde.|  
  
 Das Rowset wird nach **CATALOG_NAME**sortiert.  
  
## <a name="restriction-columns"></a>Einschränkungsspalten  
 Das **DBSCHEMA_CATALOGS** -Rowset kann auf die in der folgenden Tabelle aufgeführten Spalten eingeschränkt werden.  
  
|Spaltenname|Typindikator|Einschränkungsstatus|  
|-----------------|--------------------|-----------------------|  
|**CATALOG_NAME**|**DBTYPE_WSTR**|Optional|  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Schemarowsets](../../../analysis-services/schema-rowsets/ole-db/ole-db-schema-rowsets.md)  
  
  
