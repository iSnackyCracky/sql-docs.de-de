---
title: Löschen eines oder mehrerer Aufträge | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, deleting
- dropping jobs
- jobs [SQL Server Agent], deleting
- deleting jobs
- removing jobs
ms.assetid: 67dcdad0-57b2-431c-b77f-4ffc926af93d
caps.latest.revision: 29
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 426bd1d1320b638cba22076d62d99edc008dd728
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37170133"
---
# <a name="delete-one-or-more-jobs"></a>Löschen eines oder mehrerer Aufträge
  In diesem Thema wird beschrieben, wie Sie [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Aufträge in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]oder SQL Server Management Objects löschen können.  
  
 
  
##  <a name="BeforeYouBegin"></a> Vorbereitungsmaßnahmen  
  
###  <a name="Security"></a> Sicherheit  
 Sie können nur Aufträge löschen, die in Ihrem Besitz sind, es sei denn, Sie sind ein Mitglied der festen Serverrolle **sysadmin** .  
  
 
  
##  <a name="SSMS"></a> Verwenden von SQL Server Management Studio  
  
#### <a name="to-delete-a-job"></a>So löschen Sie einen Auftrag  
  
1.  Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.  
  
2.  Erweitern Sie **SQL Server-Agent**, und erweitern Sie **Aufträge**. Klicken Sie mit der rechten Maustaste auf den Auftrag, den Sie löschen möchten, und klicken Sie dann auf **Löschen**.  
  
3.  Bestätigen Sie im Dialogfeld **Objekt löschen** , dass der Auftrag tatsächlich gelöscht werden soll.  
  
4.  Klicken Sie auf **OK**.  
  
#### <a name="to-delete-multiple-jobs"></a>So löschen Sie mehrere Aufträge  
  
1.  Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.  
  
2.  Erweitern Sie **SQL Server-Agent**.  
  
3.  Klicken Sie mit der rechten Maustaste auf **Auftragsaktivitätsmonitor**, und klicken Sie dann auf **Auftragsaktivitäten anzeigen**.  
  
4.  Wählen Sie im Auftragsaktivitätsmonitor die Aufträge aus, die Sie löschen möchten. Klicken Sie mit der rechten Maustaste auf die Auswahl, und klicken Sie auf **Aufträge löschen**.  
  

  
##  <a name="TSQL"></a> Verwenden von Transact-SQL  
  
#### <a name="to-delete-a-job"></a>So löschen Sie einen Auftrag  
  
1.  Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.  
  
2.  Klicken Sie in der Standardleiste auf **Neue Abfrage**.  
  
3.  Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.  
  
    ```  
    USE msdb ;  
    GO  
  
    EXEC sp_delete_job  
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
 Weitere Informationen finden Sie unter [Sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql).  
  

  
##  <a name="SMO"></a> Verwendung von SQL Server Management Objects  
 **So löschen Sie mehrere Aufträge**  
  
 Verwenden der `JobCollection` Klasse, indem Sie eine Programmiersprache, die Sie, wie z. B. Visual Basic, Visual c# oder PowerShell auswählen. Weitere Informationen finden Sie unter [SQL Server Management Objects (SMO)](http://msdn.microsoft.com/library/ms162169.aspx).  
  

  
  
