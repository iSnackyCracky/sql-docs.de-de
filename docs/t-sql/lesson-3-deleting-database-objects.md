---
title: 'T-SQL-Tutorial: Löschen von Datenbankobjekten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 07/30/2018
ms.prod: sql
ms.technology: t-sql
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- SQL Server 2016
helpviewer_keywords:
- deleting database objects
ms.assetid: ecf26dd5-4535-4ed6-86fc-c73f9d9dedec
caps.latest.revision: 12
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: f9b41982cf0d71ad138d6eb43462174633c8d2de
ms.sourcegitcommit: e02c28b0b59531bb2e4f361d7f4950b21904fb74
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39455544"
---
# <a name="lesson-3-delete-database-objects"></a>Lektion 3: Löschen von Datenbankobjekten
[!INCLUDE[tsql-appliesto-ss2008-all-md](../includes/tsql-appliesto-ss2008-all-md.md)]
In dieser kurzen Lektion werden die Objekte entfernt, die Sie in Lektion 1 und Lektion 2 erstellt haben, und dann die Datenbank gelöscht.  
  
Bevor Sie Objekte löschen, stellen Sie sicher, dass Sie sich in der richtigen Datenbank befinden:
  
  ```sql  
  USE TestData;  
  GO  
  ```  

## <a name="revoke-stored-procedure-permissions"></a>Widerrufen von Berechtigungen für gespeicherte Prozeduren
  
Führen Sie die `REVOKE` -Anweisung aus, um die Ausführungsberechtigung für `Mary` in der gespeicherten Prozedur zu entfernen:
  
  ```sql  
  REVOKE EXECUTE ON pr_Names FROM Mary;  
  GO  
  ```  
  
## <a name="drop-permissions"></a>Löschen von Berechtigungen

1. Führen Sie die `DROP` -Anweisung aus, um die Berechtigung für `Mary` zum Zugriff auf die `TestData` -Datenbank zu entfernen:
  
  ```sql  
  DROP USER Mary;  
  GO  
  ```  


2. Führen Sie die `DROP` -Anweisung aus, um die Berechtigung für `Mary` zum Zugriff auf die Instanz von [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]zu entfernen:
  
  ```sql  
    DROP LOGIN [<computer_name>\Mary];  
    GO   
  ```  
  
3.   Verwenden Sie die `DROP` -Anweisung zum Entfernen der gespeicherten Prozedur `pr_Names`:  
  
    ```sql  
    DROP PROC pr_Names;  
    GO  
    ```  
  
6.  Verwenden Sie die `DROP` -Anweisung zum Entfernen der `vw_Names`-Sicht:  
  
    ```sql  
    DROP VIEW vw_Names;  
    GO  
  
    ```  

## <a name="delete-table"></a>Tabelle löschen.
  
1. Verwenden Sie die `DELETE` -Anweisung zum Entfernen von Datenzeilen aus der `Products` -Tabelle:  
  
    ```sql  
    DELETE FROM Products;  
    GO  
    ```  
  
2.  Verwenden Sie die `DROP` -Anweisung zum Entfernen der `Products` -Tabelle:  
  
    ```sql  
    DROP TABLE Products;  
    GO    
    ```  

## <a name="remove-database"></a>Entfernen von Datenbanken
  
Es ist nicht möglich, die `TestData` -Datenbank zu entfernen, während Sie sich in der Datenbank befinden. Wechseln Sie daher den Kontext zu einer anderen Datenbank, und verwenden Sie dann die `DROP` -Anweisung, um die `TestData` -Datenbank zu entfernen.  
  
  ```sql  
  USE MASTER;  
  GO  
  DROP DATABASE TestData;  
  GO   
  ```  
  
Damit ist das Lernprogramm zum Schreiben von [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen beendet. Beachten Sie, dass dieses Lernprogramm nur eine kurze Übersicht bietet und darin nicht alle Optionen der verwendeten Anweisungen beschrieben werden. Das Entwerfen und Erstellen einer effizienten Datenbankstruktur und das Konfigurieren des sicheren Zugriffs auf die Daten erfordern eine komplexere Datenbank als in diesem Lernprogramm gezeigt.  

  
  
