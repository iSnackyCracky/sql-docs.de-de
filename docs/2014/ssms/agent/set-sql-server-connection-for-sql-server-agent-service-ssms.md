---
title: Festlegen der SQL Server-Verbindung für den SQL Server-Agent-Dienst (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, connections
- connections [SQL Server], SQL Server Agent service
ms.assetid: 28b6178b-0a9e-4f2c-8562-7a62d2d2a285
caps.latest.revision: 32
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: c07251ad2cb614e6524e2397deb92ab5dfaddaa4
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37212100"
---
# <a name="set-the-sql-server-connection-for-the-sql-server-agent-service-sql-server-management-studio"></a>Set the SQL Server Connection for the SQL Server Agent Service (SQL Server Management Studio)
  In diesem Thema wird beschrieben, wie Sie die Verbindung zwischen dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent und [!INCLUDE[ssDE](../../includes/ssde-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]festlegen. Mithilfe des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Diensts kann eine Verbindung mit einer lokalen Instanz von SQL Server mit der Windows-Authentifizierung hergestellt werden.  
  
 **In diesem Thema**  
  
-   **Vorbereitungen:**  
  
     [Einschränkungen](#Restrictions)  
  
     [Security](#Security)  
  
-   **Festlegen der SQL Server-Verbindung für den SQL Server-Agent mit:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungsmaßnahmen  
  
###  <a name="Restrictions"></a> Einschränkungen  
  
-   Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Knoten wird nur im Objekt-Explorer angezeigt, wenn Sie die Berechtigung besitzen, ihn zu verwenden.  
  
-   Seit [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]unterstützt der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent keine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung. Diese Option ist nur beim Verwalten früherer Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verfügbar.  
  
###  <a name="Security"></a> Sicherheit  
  
####  <a name="Permissions"></a> Berechtigungen  
 Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent muss zur Verwendung der Anmeldeinformationen eines Kontos konfiguriert werden, das Mitglied der festen Serverrolle **sysadmin** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist, um seine Funktionen ausführen zu können. Das Konto muss über die folgenden Windows-Berechtigungen verfügen:  
  
-   Anmelden als Dienst (SeServiceLogonRight)  
  
-   Ersetzen von Token auf Prozessebene (SeAssignPrimaryTokenPrivilege)  
  
-   Umgehen von durchsuchenden Prüfungen (SeChangeNotifyPrivilege)  
  
-   Anpassen des Arbeitsspeicherkontingents für einen Prozess (SeIncreaseQuotaPrivilege)  
  
 Weitere Informationen zu den Windows-Berechtigungen, die für die die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienstkonto finden Sie unter [Auswählen eines Kontos für den SQL Server-Agent-Dienst](select-an-account-for-the-sql-server-agent-service.md) und [Konfigurieren von Windows-Dienstkonten und Berechtigungen](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).  
  
##  <a name="SSMSProcedure"></a> Verwenden von SQL Server Management Studio  
  
#### <a name="to-set-the-sql-server-connection"></a>So legen Sie die SQL Server-Verbindung fest  
  
1.  Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, für den Sie eine Verbindung mit dem SQL Server-Agent-Dienst einrichten möchten.  
  
2.  Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent** , und wählen Sie **Eigenschaften**aus.  
  
3.  Klicken Sie im Dialogfeld **SQL Server-Agent-Eigenschaften***Servername* unter **Seite auswählen** auf **Verbindung**.  
  
4.  Wählen Sie unter **SQL Server-Verbindung**die Option **Windows-Authentifizierung verwenden** aus, damit der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent beim Herstellen einer Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] die [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Authentifizierung verwenden kann. Für Verbindungen mit [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höher muss die Windows-Authentifizierung verwendet werden.  
  
  
