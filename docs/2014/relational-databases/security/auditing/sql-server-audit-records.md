---
title: SQL Server Audit-Datensätze | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: security
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- audit records [SQL Server]
ms.assetid: 7a291015-df15-44fe-8d53-c6d90a157118
caps.latest.revision: 19
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: a55513bbe857d1d3ea48371d1e147d54ce8d3326
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37253778"
---
# <a name="sql-server-audit-records"></a>SQL Server Audit-Datensätze
  Die Funktion [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit ermöglicht es, Ereignisgruppen und Ereignisse auf Serverebene und auf Datenbankebene zu überwachen. Weitere Informationen finden Sie unter [SQL Server Audit &amp;#40;Datenbank-Engine&amp;#41;](sql-server-audit-database-engine.md). [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]installiert haben.  
  
 Überwachungen bestehen aus null oder mehr Überwachungsaktionselementen, die in einem *Überwachungsziel*aufgezeichnet werden. Beim Überwachungsziel kann es sich um eine Binärdatei, das Windows-Sicherheitsereignisprotokoll oder das Windows-Anwendungsereignisprotokoll handeln. Die an das Ziel gesendeten Datensätze können die in der folgenden Tabelle beschriebenen Elemente enthalten.  
  
|Spaltenname|Description|Typ|Immer verfügbar|  
|-----------------|-----------------|----------|----------------------|  
|**event_time**|Datum und Uhrzeit der Auslösung des überwachbaren Vorgangs.|`datetime2`|ja|  
|**sequence_no**|Hält die Reihenfolge der Datensätze innerhalb eines einzelnen Überwachungsdatensatzes fest, der zu groß für den Schreibpuffer für Überwachungen ist.|`int`|ja|  
|**action_id**|ID der Aktion<br /><br /> Tipp: Damit **action_id** als Prädikat verwendet werden kann, muss eine Konvertierung von einer Zeichenfolge in einen numerischen Wert durchgeführt werden. Weitere Informationen finden Sie unter [Filtern von SQL Server Audit nach dem action_id-Prädikat oder class_type-Prädikat](http://blogs.msdn.com/b/sqlsecurity/archive/2012/10/03/filter-sql-server-audit-on-action-id-class-type-predicate.aspx).|`varchar(4)`|ja|  
|**succeeded**|Gibt an, ob die Aktion, die das Ereignis ausgelöst hat, erfolgreich war.|`bit` – 1 = Erfolg, 0 = Fehler|ja|  
|**permission_bitmask**|Zeigt, sofern anwendbar, die Berechtigungen an, die gewährt, verweigert oder widerrufen wurden.|`bigint`|nein|  
|**is_column_permission**|Flag, das eine Berechtigung auf Spaltenebene angibt.|`bit` – 1 = "true", 0 = False|nein|  
|**session_id**|Die ID der Sitzung, in der das Ereignis aufgetreten ist.|`int`|ja|  
|**server_principal_id**|ID des Anmeldekontexts, in dem die Aktion ausgeführt wird.|`int`|ja|  
|**database_principal_id**|ID des Datenbankbenutzerkontexts, in dem die Aktion ausgeführt wird.|`int`|nein|  
|**object_id**|Die primäre ID der Entität, bei der die Überwachung aufgetreten ist. Dies schließt Folgendes ein:<br /><br /> Serverobjekte<br /><br /> Datenbanken<br /><br /> Datenbankobjekte<br /><br /> Schemaobjekte|`int`|nein|  
|**target_server_principal_id**|Serverprinzipal, für den die überwachbare Aktion gilt.|`int`|ja|  
|**target_database_principal_id**|Datenbankprinzipal, für den die überwachbare Aktion gilt.|`int`|nein|  
|**class_type**|Typ der überwachbaren Entität, bei der die Überwachung auftritt.|`varchar(2)`|ja|  
|**session_server_principal_name**|Serverprinzipal für die Sitzung.|`sysname`|ja|  
|**server_principal_name**|Aktuelle Anmeldung.|`sysname`|ja|  
|**server_principal_sid**|Aktuelle Anmeldungs-SID.|`varbinary`|ja|  
|**database_principal_name**|Aktueller Benutzer.|`sysname`|nein|  
|**target_server_principal_name**|Zielanmeldung der Aktion.|`sysname`|nein|  
|**target_server_principal_sid**|SID der Zielanmeldung.|`varbinary`|nein|  
|**target_database_principal_name**|Zielbenutzer der Aktion.|`sysname`|nein|  
|**server_instance_name**|Der Name der Serverinstanz, in der die Überwachung aufgetreten ist. Verwendet das standardmäßige machine\instance-Format.|`nvarchar(120)`|ja|  
|**database_name**|Der Datenbankkontext, in dem die Aktion aufgetreten ist.|`sysname`|nein|  
|**schema_name**|Der Schemakontext, in dem die Aktion aufgetreten ist.|`sysname`|nein|  
|**object_name**|Der Name der Entität, bei der die Überwachung aufgetreten ist. Dies schließt Folgendes ein:<br /><br /> Serverobjekte<br /><br /> Datenbanken<br /><br /> Datenbankobjekte<br /><br /> Schemaobjekte<br /><br /> TSQL-Anweisung (falls vorhanden)|`sysname`|nein|  
|**statement**|TSQL-Anweisung (falls vorhanden)|`nvarchar(4000)`|nein|  
|**additional_information**|Zusätzliche Informationen über das als XML gespeicherte Ereignis.|`nvarchar(4000)`|nein|  
  
## <a name="remarks"></a>Hinweise  
 Einige Aktionen geben nicht den Wert einer Spalte ein, da er auf die Aktion nicht anwendbar sein könnte.  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit speichert 4000 Datenzeichen für Zeichenfelder in einem Überwachungsdatensatz. Wenn die Werte **additional_information** und **statement** , die von einer überwachbaren Aktion zurückgegeben wurden, mehr als 4000 Zeichen zurückgeben, wird die Spalte **sequence_no** dazu verwendet, mehrere Datensätze in einen Überwachungsbericht für eine einzelne Überwachungsaktion zu schreiben, um diese Daten aufzuzeichnen. Der Prozess sieht folgendermaßen aus:  
  
-   Die Spalte **statement** wird in 4000 Zeichen geteilt.  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit schreibt als erste Zeile für den Überwachungsdatensatz die partiellen Daten. Alle anderen Felder werden in jeder Zeile dupliziert.  
  
-   Der **sequence_no** -Wert wird inkrementiert.  
  
-   Dieser Prozess wird wiederholt, bis alle Daten aufgezeichnet wurden.  
  
 Sie können die Daten verbinden, indem Sie die Zeilen sequenziell mit dem Wert **sequence_no** und den Spalten **event_Time**, **action_id** sowie **session_id** lesen, um die Aktion zu identifizieren.  
  
## <a name="related-content"></a>Verwandte Inhalte  
 [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql)  
  
 [ALTER SERVER AUDIT  &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-server-audit-specification-transact-sql)  
  
 [DROP SERVER AUDIT  &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-server-audit-transact-sql)  
  
 [CREATE SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-specification-transact-sql)  
  
 [ALTER SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-server-audit-transact-sql)  
  
 [DROP SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-server-audit-specification-transact-sql)  
  
 [CREATE DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-audit-specification-transact-sql)  
  
 [ALTER DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-audit-specification-transact-sql)  
  
 [DROP DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-encryption-key-transact-sql)  
  
 [ALTER AUTHORIZATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-authorization-transact-sql)  
  
 [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql)  
  
 [sys.server_audits &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-audits-transact-sql)  
  
 [sys.server_file_audits &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-file-audits-transact-sql)  
  
 [sys.server_audit_specifications &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-audit-specifications-transact-sql)  
  
 [sys.server_audit_specification_details &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-audit-specification-details-transact-sql)  
  
 [sys.database_audit_specifications &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-audit-specifications-transact-sql)  
  
 [sys.database_audit_specification_details &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-audit-specification-details-transact-sql)  
  
 [sys.dm_server_audit_status &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-server-audit-status-transact-sql)  
  
 [sys.dm_audit_actions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-audit-actions-transact-sql)  
  
 [sys.dm_audit_class_type_map &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-audit-class-type-map-transact-sql)  
  
  
