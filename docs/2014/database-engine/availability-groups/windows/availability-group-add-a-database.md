---
title: Hinzufügen einer Datenbank zu einer Verfügbarkeitsgruppe (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 2a54eef8-9e8e-4e04-909c-6970112d55cc
caps.latest.revision: 31
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: a7a3462cb59bd895433d5ea6b66f0b14099446ea
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37161051"
---
# <a name="add-a-database-to-an-availability-group-sql-server"></a>Hinzufügen einer Datenbank zu einer Verfügbarkeitsgruppe (SQL Server)
  In diesem Thema wird beschrieben, wie einer AlwaysOn-Verfügbarkeitsgruppe mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]eine Datenbank hinzugefügt wird.  
  
-   **Vorbereitungen:**  
  
     [Voraussetzungen und Einschränkungen](#Prerequisites)  
  
     [Berechtigungen](#Permissions)  
  
-   **Hinzufügen einer Datenbank zu einer Verfügbarkeitsgruppe mit:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
     [PowerShell](#PowerShellProcedure)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungsmaßnahmen  
  
###  <a name="Prerequisites"></a> Voraussetzungen und Einschränkungen  
  
-   Sie müssen mit der Serverinstanz verbunden sein, die das primäre Replikat hostet.  
  
-   Die Datenbank muss sich auf der Serverinstanz befinden, die das primäre Replikat hostet, und die Voraussetzungen und Einschränkungen für Verfügbarkeitsdatenbanken erfüllen. Weitere Informationen finden Sie unter [Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen&#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).  
  
###  <a name="Security"></a> Sicherheit  
  
###  <a name="Permissions"></a> Berechtigungen  
 Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.  
  
##  <a name="SSMSProcedure"></a> Verwenden von SQL Server Management Studio  
 **So fügen sie einer Verfügbarkeitsgruppe eine Datenbank hinzu**  
  
1.  Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das primäre Verfügbarkeitsreplikat hostet, und erweitern Sie die Serverstruktur.  
  
2.  Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .  
  
3.  Klicken Sie mit der rechten Maustaste auf die Verfügbarkeitsgruppe, und wählen Sie einen der folgenden Befehle aus:  
  
    -   Wählen Sie zum Starten des Assistenten zum Hinzufügen von Datenbanken zu Verfügbarkeitsgruppen den Befehl **Datenbank hinzufügen** aus. Weitere Informationen finden Sie unter [Verwenden des Assistenten zum Hinzufügen von Datenbanken zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;](availability-group-add-database-to-group-wizard.md).  
  
    -   Wählen Sie den Befehl **Eigenschaften** aus, um mindestens eine Datenbank durch Angabe im Dialogfeld für die **Eigenschaften der Verfügbarkeitsgruppe** hinzuzufügen. Folgende Schritte sind zum Hinzufügen einer Datenbank erforderlich:  
  
        1.  Klicken Sie im Bereich **Verfügbarkeitsdatenbanken** auf die Schaltfläche **Hinzufügen** . Dadurch wird ein leeres Datenbankfeld erstellt und ausgewählt.  
  
        2.  Geben Sie den Namen einer Datenbank ein, die die Voraussetzungen der Verfügbarkeitsdatenbanken erfüllt.  
  
         Wiederholen Sie zum Hinzufügen einer weiteren Datenbank die vorhergehenden Schritte. Wenn Sie alle Datenbanken angegeben haben, klicken Sie auf **OK** , um den Vorgang abzuschließen.  
  
         Nachdem Sie das Kontrollkästchen **Eigenschaften der Verfügbarkeitsgruppe** aktiviert haben, um einer Verfügbarkeitsgruppe eine Datenbank hinzuzufügen, müssen Sie die zugehörige zweite Datenbank auf jeder Serverinstanz konfigurieren, auf der das sekundäre Replikat gehostet wird. Weitere Informationen finden Sie unter [Starten der Datenverschiebung auf einer sekundären AlwaysOn-Datenbank &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).  
  
##  <a name="TsqlProcedure"></a> Verwenden von Transact-SQL  
 **So fügen sie einer Verfügbarkeitsgruppe eine Datenbank hinzu**  
  
1.  Stellen Sie eine Verbindung mit der Serverinstanz her, die die Serverinstanz mit dem primären Replikat hostet.  
  
2.  Verwenden Sie die [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) -Anweisung wie folgt:  
  
     ALTER AVAILABILITY GROUP *group_name* ADD DATABASE *database_name* [,...*n*]  
  
     Dabei ist *group_name* der Name der Verfügbarkeitsgruppe und *database_name* der Name einer zur Gruppe hinzuzufügenden Datenbank.  
  
     Im folgenden Beispiel wird die Datenbank *MyDb3* zur Verfügbarkeitsgruppe *MyAG* hinzugefügt.  
  
    ```  
    -- Connect to the server instance that hosts the primary replica.  
    -- Add an existing database to the availability group.  
    ALTER AVAILABILITY GROUP MyAG ADD DATABASE MyDb3;  
    GO  
    ```  
  
3.  Nachdem Sie einer Verfügbarkeitsgruppe eine Datenbank hinzugefügt haben, müssen Sie die zugehörige zweite Datenbank auf jeder Serverinstanz konfigurieren, auf der das sekundäre Replikat gehostet wird. Weitere Informationen finden Sie unter [Starten der Datenverschiebung auf einer sekundären AlwaysOn-Datenbank &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).  
  
##  <a name="PowerShellProcedure"></a> PowerShell  
 **So fügen sie einer Verfügbarkeitsgruppe eine Datenbank hinzu**  
  
1.  Ändern Sie das Verzeichnis (`cd`) zur Serverinstanz, die das primäre Replikat hostet.  
  
2.  Verwenden der `Add-SqlAvailabilityDatabase` Cmdlet.  
  
     Beispielsweise wird mit dem folgenden Befehl die sekundäre Datenbank `MyDd` der `MyAG` -Verfügbarkeitsgruppe hinzugefügt, deren primäres Replikat von `PrimaryServer\InstanceName`gehostet wird.  
  
    ```  
  
    Add-SqlAvailabilityDatabase `   
    -Path SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAG `   
    -Database "MyDb"  
    ```  
  
    > [!NOTE]  
    >  Um die Syntax eines Cmdlets anzuzeigen, verwenden die `Get-Help` -Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung. Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).  
  
3.  Nachdem Sie einer Verfügbarkeitsgruppe eine Datenbank hinzugefügt haben, müssen Sie die zugehörige zweite Datenbank auf jeder Serverinstanz konfigurieren, auf der das sekundäre Replikat gehostet wird. Weitere Informationen finden Sie unter [Starten der Datenverschiebung auf einer sekundären AlwaysOn-Datenbank &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).  
  
 **Einrichten und Verwenden des SQL Server PowerShell-Anbieters**  
  
-   [SQL Server PowerShell-Anbieter](../../../powershell/sql-server-powershell-provider.md)  
  
 Ein vollständiges Beispiel finden Sie unten unter [Beispiel (PowerShell)](#PSExample).  
  
###  <a name="PSExample"></a> Beispiel (PowerShell)  
 Im folgenden Beispiel wird der vollständige Vorbereitungsprozess veranschaulicht: Eine sekundäre Datenbank wird von einer Datenbank auf der Serverinstanz, von der das primäre Replikat einer Verfügbarkeitsgruppe gehostet wird, vorbereitet. Anschließend wird die Datenbank einer Verfügbarkeitsgruppe (als primäre Datenbank) hinzugefügt, und dann wird die sekundäre Datenbank mit der Verfügbarkeitsgruppe verknüpft. Zunächst werden die Datenbank und das zugehörige Transaktionsprotokoll gesichert. Anschließend werden die Datenbank- und Protokollsicherungen in den Serverinstanzen wiederhergestellt, von denen ein sekundäres Replikat gehostet wird.  
  
 `Add-SqlAvailabilityDatabase` wird im Beispiel zweimal aufgerufen: zuerst für das primäre Replikat, um die Datenbank der Verfügbarkeitsgruppe hinzuzufügen, und anschließend für das sekundäre Replikat, um die sekundäre Datenbank auf diesem Replikat mit der Verfügbarkeitsgruppe zu verknüpfen. Wenn Sie über mehr als ein sekundäres Replikat verfügen, muss die sekundäre Datenbank auf jedem einzelnen Replikat wiederhergestellt und verknüpft werden.  
  
```  
$DatabaseBackupFile = "\\share\backups\MyDatabase.bak"  
$LogBackupFile = "\\share\backups\MyDatabase.trn"  
$MyAgPrimaryPath = "SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAg"  
$MyAgSecondaryPath = "SQLSERVER:\SQL\SecondaryServer\InstanceName\AvailabilityGroups\MyAg"  
  
Backup-SqlDatabase -Database "MyDatabase" -BackupFile $DatabaseBackupFile -ServerInstance "PrimaryServer\InstanceName"  
Backup-SqlDatabase -Database "MyDatabase" -BackupFile $LogBackupFile -ServerInstance "PrimaryServer\InstanceName" -BackupAction 'Log'  
  
Restore-SqlDatabase -Database "MyDatabase" -BackupFile $DatabaseBackupFile -ServerInstance "SecondaryServer\InstanceName" -NoRecovery  
Restore-SqlDatabase -Database "MyDatabase" -BackupFile $LogBackupFile -ServerInstance "SecondaryServer\InstanceName" -RestoreAction 'Log' -NoRecovery  
  
Add-SqlAvailabilityDatabase -Path $MyAgPrimaryPath -Database "MyDatabase"  
Add-SqlAvailabilityDatabase -Path $MyAgSecondaryPath -Database "MyDatabase"  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQLServer&#41;](overview-of-always-on-availability-groups-sql-server.md)   
 [Erstellung und Konfiguration von Verfügbarkeitsgruppen &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md)   
 [Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md)   
 [Überwachen von Verfügbarkeitsgruppen &#40;Transact-SQL&#41;](monitor-availability-groups-transact-sql.md)  
  
  
