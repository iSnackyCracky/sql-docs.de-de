---
title: Anzeigen der Daten und Protokolldateien in einem Sicherungssatz (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: backup-restore
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], viewing backup sets
- viewing backup set information
- backup sets [SQL Server], viewing files in
- displaying backup set information
- transaction log backups [SQL Server], viewing backup sets
- backing up [SQL Server], viewing backup sets
ms.assetid: abb6420c-f809-426e-aeb4-d0a74989cf39
caps.latest.revision: 22
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 3c548ee0a7c5c4c32fa789c15fabe9b99a9b94bb
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37205420"
---
# <a name="view-the-data-and-log-files-in-a-backup-set-sql-server"></a>Anzeigen der Daten und Protokolldateien in einem Sicherungssatz (SQL Server)
  In diesem Thema wird beschrieben, wie Sie Daten und Protokolldateien in einem Sicherungssatz in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]anzeigen können.  
  
 **In diesem Thema**  
  
-   **Vorbereitungen:**  
  
     [Security](#Security)  
  
-   **So zeigen Sie die Daten und Protokolldateien in einem Sicherungssatz an mit**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungsmaßnahmen  
  
###  <a name="Security"></a> Sicherheit  
 Weitere Informationen zur Sicherheit finden Sie unter [RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql).  
  
####  <a name="Permissions"></a> Berechtigungen  
 In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] und höheren Versionen benötigen Sie die CREATE DATABASE-Berechtigung, um Informationen zu Sicherungssätzen oder Sicherungsmedien abzurufen. Weitere Informationen finden Sie unter [GRANT (Datenbankberechtigungen) &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).  
  
##  <a name="SSMSProcedure"></a> Verwenden von SQL Server Management Studio  
  
#### <a name="to-view-the-data-and-log-files-in-a-backup-set"></a>So zeigen Sie die Daten und Protokolldateien in einem Sicherungssatz an  
  
1.  Klicken Sie im Objekt-Explorer nach dem Herstellen einer Verbindung mit der entsprechenden Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]auf den Servernamen, um die Serverstruktur zu erweitern.  
  
2.  Erweitern Sie **Datenbanken**, und wählen Sie je nach Datenbank eine Benutzerdatenbank aus, oder erweitern Sie **Systemdatenbanken** , und wählen Sie eine Systemdatenbank aus.  
  
3.  Klicken Sie mit der rechten Maustaste auf die Datenbank, und klicken Sie dann auf **Eigenschaften**. Das Dialogfeld **Datenbankeigenschaften** wird geöffnet.  
  
4.  Klicken Sie im Fensterbereich **Seite auswählen** auf **Dateien**.  
  
5.  Suchen Sie im Bereich **Datenbankdateien** nach einer Liste der Daten- und Protokolldateien und deren Eigenschaften.  
  
##  <a name="TsqlProcedure"></a> Verwenden von Transact-SQL  
  
#### <a name="to-view-the-data-and-log-files-in-a-backup-set"></a>So zeigen Sie die Daten und Protokolldateien in einem Sicherungssatz an  
  
1.  Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.  
  
2.  Klicken Sie in der Standardleiste auf **Neue Abfrage**.  
  
3.  Verwenden Sie die [RESTORE FILELISTONLY](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) -Anweisung. In diesem Beispiel werden Informationen zum sekundären Sicherungsmedium (`FILE=2`) auf dem `AdventureWorksBackups` -Sicherungsmedium zurückgegeben:  
  
```tsql  
USE AdventureWorks2012 ;  
RESTORE FILELISTONLY FROM AdventureWorksBackups   
   WITH FILE=2;  
GO  
```  
  
## <a name="see-also"></a>Siehe auch  
 [backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql)   
 [backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql)   
 [backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql)   
 [backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql)   
 [backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql)   
 [Sicherungsmedien &#40;SQL Server&#41;](backup-devices-sql-server.md)  
  
  
