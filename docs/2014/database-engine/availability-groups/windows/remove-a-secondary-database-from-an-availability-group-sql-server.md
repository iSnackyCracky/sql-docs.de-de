---
title: Entfernen einer sekundären Datenbank aus einer Verfügbarkeitsgruppe (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.unjoindb.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], databases
ms.assetid: 4e51a570-58d7-4f01-9390-4198f3602576
caps.latest.revision: 21
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 4b03f73eda6a16aeac540c536dec864bbc426395
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37306130"
---
# <a name="remove-a-secondary-database-from-an-availability-group-sql-server"></a>Entfernen einer sekundären Datenbank aus einer Verfügbarkeitsgruppe (SQL Server)
  In diesem Thema wird beschrieben, wie eine sekundäre Datenbank aus einer AlwaysOn-Verfügbarkeitsgruppe mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]entfernt wird.  
  
-   **Vorbereitungen:**  
  
     [Erforderliche Komponenten](#Prerequisites)  
  
     [Security](#Security)  
  
-   **So entfernen Sie eine sekundäre Datenbank mit**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
     [PowerShell](#PowerShellProcedure)  
  
-   **Nachverfolgung:**  [Nach dem Entfernen einer sekundären Datenbank aus einer Verfügbarkeitsgruppe](#FollowUp)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungsmaßnahmen  
  
###  <a name="Restrictions"></a>   
###  <a name="Prerequisites"></a> Voraussetzungen und Einschränkungen  
  
-   Dieser Task wird nur für sekundäre Replikate unterstützt. Sie müssen mit der Serverinstanz verbunden sein, auf der das sekundäre Replikat gehostet wird, aus dem die Datenbank entfernt werden soll.  
  
###  <a name="Security"></a> Sicherheit  
  
####  <a name="Permissions"></a> Berechtigungen  
 Erfordert die ALTER-Berechtigung für die Datenbank.  
  
##  <a name="SSMSProcedure"></a> Verwenden von SQL Server Management Studio  
 **So entfernen Sie eine sekundäre Datenbank aus einer Verfügbarkeitsgruppe**  
  
1.  Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, auf der das sekundäre Replikat gehostet wird, aus dem Sie mindestens eine sekundäre Datenbanken entfernen möchten, und erweitern Sie die Serverstruktur.  
  
2.  Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .  
  
3.  Wählen Sie die Verfügbarkeitsgruppe aus, und erweitern Sie den Knoten **Verfügbarkeitsdatenbanken** .  
  
4.  Dieser Schritt hängt davon ab, ob Sie mehrere Datenbankgruppen oder nur eine Datenbank entfernen möchten:  
  
    -   Verwenden Sie zum Entfernen mehrerer Datenbanken den Bereich **Details zum Objekt-Explorer** , um alle zu entfernenden Datenbanken anzuzeigen und auszuwählen. Weitere Informationen finden Sie unter [Verwenden der Details zum Objekt-Explorer zum Überwachen von Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).  
  
    -   Wählen Sie zum Entfernen einer einzelnen Datenbank diese im Bereich **Objekt-Explorer** oder **Details zum Objekt-Explorer** aus.  
  
5.  Klicken Sie mit der rechten Maustaste auf die ausgewählten Datenbanken, und wählen Sie im Befehlsmenü **Sekundäre Datenbank entfernen** aus.  
  
6.  Klicken Sie zum Entfernen aller aufgelisteten Datenbanken im Dialogfeld **Datenbank aus Verfügbarkeitsgruppe entfernen** auf **OK**. Wenn Sie nicht alle aufgelisteten Datenbanken entfernen wollen, klicken Sie auf **Abbrechen**.  
  
##  <a name="TsqlProcedure"></a> Verwenden von Transact-SQL  
 **So entfernen Sie eine sekundäre Datenbank aus einer Verfügbarkeitsgruppe**  
  
1.  Stellen Sie eine Verbindung mit der Serverinstanz her, die das sekundäre Replikat hostet.  
  
2.  Verwenden Sie die [SET HADR-Klausel der ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) -Anweisung wie folgt:  
  
     ALTER DATABASE *Name der Datenbank* SET HADR OFF  
  
     Dabei steht *Name der Datenbank* für den Namen einer sekundären Datenbank, die aus der Verfügbarkeitsgruppe entfernt werden soll, zu der sie gehört.  
  
     Im folgenden Beispiel wird die sekundäre Datenbank *MyDb2* aus ihrer Verfügbarkeitsgruppe entfernt.  
  
    ```  
    ALTER DATABASE MyDb2 SET HADR OFF;  
    GO  
    ```  
  
##  <a name="PowerShellProcedure"></a> PowerShell  
 **So entfernen Sie eine sekundäre Datenbank aus einer Verfügbarkeitsgruppe**  
  
1.  Ändern Sie das Verzeichnis (`cd`) mit der Serverinstanz her, die das sekundäre Replikat hostet.  
  
2.  Verwenden Sie das **Remove-SqlAvailabilityDatabase** -Cmdlet, und geben Sie dabei den Namen der Verfügbarkeitsdatenbank an, die aus der Verfügbarkeitsgruppe entfernt werden soll. Wenn Sie mit einer Serverinstanz verbunden sind, auf der ein sekundäres Replikat gehostet wird, wird nur die lokale sekundäre Datenbank aus der Verfügbarkeitsgruppe entfernt.  
  
     Beispielsweise wird durch den folgenden Befehl die sekundäre Datenbank `MyDb8` aus dem sekundären Replikat entfernt, das von der Serverinstanz `SecondaryComputer\Instance`gehostet wird. Die Daten der entfernten sekundären Datenbanken werden nicht mehr synchronisiert. Dieser Befehl wirkt sich nicht auf die primäre Datenbank oder andere sekundäre Datenbanken aus.  
  
    ```  
    Remove-SqlAvailabilityDatabase `  
    -Path SQLSERVER:\Sql\SecondaryComputer\InstanceName\AvailabilityGroups\MyAg\Databases\MyDb8  
    ```  
  
    > [!NOTE]  
    >  Um die Syntax eines Cmdlets anzuzeigen, verwenden die `Get-Help` -Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung. Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).  
  
 **Einrichten und Verwenden des SQL Server PowerShell-Anbieters**  
  
-   [SQL Server PowerShell-Anbieter](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="FollowUp"></a> Nachverfolgung: Nach dem Entfernen einer sekundären Datenbank aus einer Verfügbarkeitsgruppe  
 Wenn eine sekundäre Datenbank entfernt wird, wird sie nicht mehr der Verfügbarkeitsgruppe hinzugefügt, und alle Informationen zur entfernten sekundären Datenbank werden von der Verfügbarkeitsgruppe verworfen. Die entfernte sekundäre Datenbank wechselt in den Status RESTORING.  
  
> [!TIP]  
>  Für eine kurze Zeit, nachdem Sie die sekundäre Datenbank entfernt haben, sind Sie möglicherweise in der Lage, die AlwaysOn-Datensynchronisierung für die Datenbank neu zu starten, indem Sie sie mit der Verfügbarkeitsgruppe verknüpfen. Weitere Informationen finden Sie unter [Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md)aktiviert sind, eine Always On-Verfügbarkeitsgruppe zu erstellen.  
  
 Zu diesem Zeitpunkt stehen alternative Methoden zum Umgang mit einer entfernten sekundären Datenbank zur Verfügung:  
  
-   Wenn Sie die sekundäre Datenbank nicht mehr benötigen, können Sie sie löschen.  
  
     Weitere Informationen finden Sie unter [DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) oder [Löschen einer Datenbank](../../../relational-databases/databases/delete-a-database.md).  
  
-   Wenn Sie auf eine entfernte sekundäre Datenbank zugreifen möchten, nachdem sie aus der Verfügbarkeitsgruppe entfernt wurde, können Sie die Datenbank wiederherstellen. Wenn Sie jedoch eine entfernte sekundäre Datenbank wiederherstellen, sind zwei voneinander abweichende, unabhängige Datenbanken mit demselben Namen online. Sie müssen sicherstellen, dass Clients auf nur die aktuelle primäre Datenbank zugreifen können.  
  
     Weitere Informationen finden Sie unter [Wiederherstellen einer Datenbank ohne Wiederherstellung von Daten &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQLServer&#41;](overview-of-always-on-availability-groups-sql-server.md)   
 [Entfernen einer primären Datenbank aus einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](remove-a-primary-database-from-an-availability-group-sql-server.md)  
  
  
