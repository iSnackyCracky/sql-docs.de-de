---
title: Ändern des Schemas einer temporalen Tabelle mit Systemversionsverwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/28/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: table-view-index
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 9dbe5a21-9335-4f8b-85fd-9da83df79946
caps.latest.revision: 13
author: CarlRabeler
ms.author: carlrab
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: ec5c8a524ed985e33a2105154d223d2bf649d1d3
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39544390"
---
# <a name="changing-the-schema-of-a-system-versioned-temporal-table"></a>Ändern vom Schema einer versionsverwalteten temporalen Tabelle
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  Verwenden Sie die **ALTER TABLE** -Anweisung, um eine Spalte hinzuzufügen, zu ändern oder zu entfernen.  
  
## <a name="examples"></a>Beispiele  
 Hier sind einige Beispiele, mit denen das Schema einer temporalen Tabelle geändert werden kann.  
  
```  
ALTER TABLE dbo.Department   
   ALTER COLUMN  DeptName varchar(100);   
  
ALTER TABLE dbo.Department   
   ADD WebAddress nvarchar(255) NOT NULL    
   CONSTRAINT DF_WebAddress DEFAULT 'www.mycompany.com';   
  
ALTER TABLE dbo.Department   
   ADD TempColumn INT;   
  
GO   
  
ALTER TABLE dbo.Department   
   DROP COLUMN TempColumn;  
  
/* Setting IsHidden property for period columns.   
Use ALTER COLUMN <period_column> DROP HIDDEN to clear IsHidden flag */  
  
ALTER TABLE dbo.Department   
   ALTER COLUMN SysStartTime ADD HIDDEN;   
  
ALTER TABLE dbo.Department   
   ALTER COLUMN SysEndTime ADD HIDDEN;  
  
```  
  
### <a name="important-remarks"></a>Wichtige Hinweise  
  
-   Um das Schema der temporalen Tabelle zu ändern, ist die**CONTROL** -Berechtigung für aktuelle Tabellen und Verlaufstabellen erforderlich.  
  
-   Während eines **ALTER TABLE** -Vorgangs richtet das System eine Schemasperre auf beide Tabellen ein.  
  
-   Die angegebene Schemaänderung wird an die Verlaufstabelle in einer passenden Art weitergegeben (je nach Art der Änderung)  
  
-   Falls Sie eine nicht nullierbare Spalte hinzufügen oder eine vorhandene Spalte dahingehend ändern, dass sie nicht nullierbar wird, müssen Sie Standardwerte für die vorhandenen Zeilen angeben. Das System generiert einen zusätzlichen Standardwert mit demselben Wert und wendet ihn auf die Verlaufstabelle an. Das Hinzufügen von **DEFAULT** zu einer nicht leeren Tabelle ist in allen Editionen außer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise Edition (dort ist es ein Metadatenvorgang) ein Vorgang, der die Datengröße betrifft.  
  
-   Das Hinzufügen von varchar(max)-, nvarchar(max)-, varbinary(max)- oder XML-Spalten mit Standardwerten ist in allen Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ein Datenaktualisierungsvorgang.  
  
-   Falls die Zeilengröße nach dem Hinzufügen von Spalten die Zeilengrößenbeschränkung überschreitet, können keine neuen Spalten mehr online hinzugefügt werden.  
  
-   Ziehen Sie das Entfernen von Standardeinschränkungen für die Verlaufstabelle in Betracht, sobald Sie eine Tabelle mit einer neuen NOT NULL-Spalte erweitert haben, da alle Spalten in dieser Tabelle automatisch durch das System befüllt werden.  
  
-   Die Onlineoption (**WITH (ONLINE = ON**) hat keine Auswirkungen auf **ALTER TABLE ALTER COLUMN** , wenn es sich um eine temporale Tabelle mit Systemversionsverwaltung handelt. Die Operation ALTER COLUMN wird nicht im Modus „online“ durchgeführt. Dies gilt unabhängig vom Wert, der für die Option ONLINE festgelegt wurde.  
  
-   Sie können **ALTER COLUMN** verwenden, um die **IsHidden** -Eigenschaft für Zeitraumspalten zu ändern.  
  
-   Sie können keine direkte **ALTER** -Anweisung für die folgenden Schemaänderungen verwenden. Legen Sie für diese Art von Änderungen **SYSTEM_VERSIONING = OFF**fest.  
  
    -   Hinzufügen einer berechneten Spalte  
  
    -   Hinzufügen einer **IDENTITY** -Spalte  
  
    -   Hinzufügen einer **SPARSE** -Spalte oder Ändern einer vorhandene Spalte in **SPARSE**, wenn die Verlaufstabelle auf **DATA_COMPRESSION = PAGE** oder **DATA_COMPRESSION = ROW**festgelegt ist (dies ist standardmäßig für Verlaufstabellen der Fall)  
  
    -   Hinzufügen von **COLUMN_SET**  
  
    -   Hinzufügen einer **ROWGUIDCOL** -Spalte oder Ändern einer vorhandenen Spalte in **ROWGUIDCOL**  
  
         Das folgende Beispiel zeigt die Änderung des Schemas, bei dem die Einstellung **SYSTEM_VERSIONING = OFF** noch erforderlich ist (Hinzufügen einer **IDENTITY** -Spalte).   
        Beachten Sie, dass in diesem Beispiel die Datenkonsistenzprüfung deaktiviert wird. Diese Überprüfung ist nicht erforderlich, wenn die Schemaänderung innerhalb einer Transaktion durchgeführt wird, da keine gleichzeitigen Datenänderungen auftreten können.  
  
        ```  
        BEGIN TRAN   
        ALTER TABLE [dbo].[CompanyLocation] SET (SYSTEM_VERSIONING = OFF);   
        ALTER TABLE [CompanyLocation] ADD Cntr INT IDENTITY (1,1);   
        ALTER TABLE [dbo].[CompanyLocationHistory] ADD Cntr INT NOT NULL DEFAULT 0;   
        ALTER TABLE [dbo].[CompanyLocation]    
        SET    
        (   
        SYSTEM_VERSIONING = ON (HISTORY_TABLE = [dbo].[CompanyLocationHistory])   
        );   
        COMMIT ;  
  
        ```  
  
 
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Temporale Tabellen](../../relational-databases/tables/temporal-tables.md)   
 [Erste Schritte mit temporalen Tabellen mit Systemversionsverwaltung](../../relational-databases/tables/getting-started-with-system-versioned-temporal-tables.md)   
 [Verwalten der Beibehaltung von Verlaufsdaten in temporalen Tabellen mit Systemversionsverwaltung](../../relational-databases/tables/manage-retention-of-historical-data-in-system-versioned-temporal-tables.md)   
 [Temporale Tabellen mit Systemversionsverwaltung und speicheroptimierten Tabellen](../../relational-databases/tables/system-versioned-temporal-tables-with-memory-optimized-tables.md)   
 [ALTER TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-table-transact-sql.md)   
 [Erstellen einer temporalen Tabelle mit Systemversionsverwaltung](../../relational-databases/tables/creating-a-system-versioned-temporal-table.md)   
 [Ändern von Daten in einer temporalen Tabelle mit Systemversionsverwaltung](../../relational-databases/tables/modifying-data-in-a-system-versioned-temporal-table.md)   
 [Abfragen von Daten in einer temporalen Tabelle mit Systemversionsverwaltung](../../relational-databases/tables/querying-data-in-a-system-versioned-temporal-table.md)   
 [Beenden der Versionsverwaltung auf einer versionsverwalteten temporalen Tabelle](../../relational-databases/tables/stopping-system-versioning-on-a-system-versioned-temporal-table.md)  
  
  
