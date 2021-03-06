---
title: Anmeldeinformationen (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 02/27/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: security
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- principals [SQL Server], credentials
- schemas [SQL Server], credentials
- permissions [SQL Server], credentials
- groups [SQL Server], credentials
- ALTER ANY CREDENTIAL permission
- security [SQL Server], credentials
- authentication [SQL Server], credentials
- users [SQL Server], credentials
- credentials [SQL Server], about credentials
- credentials [SQL Server]
ms.assetid: c8df6022-e0b4-46b8-9670-3f86938d3177
caps.latest.revision: 31
author: CarlRabeler
ms.author: carlrab
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: f0c7eae9cfe6aff0c0a7012e19f5307042e4269a
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39564124"
---
# <a name="credentials-database-engine"></a>Anmeldeinformationen (Datenbank-Engine)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  Anmeldeinformationen sind in einem Datensatz gespeichert, in dem die Authentifizierungsinformationen (Anmeldeinformationen) enthalten sind, die zum Herstellen einer Verbindung mit einer Ressource außerhalb von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]erforderlich sind. Diese Informationen werden intern von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]verwendet. Die meisten Anmeldeinformationen enthalten einen Windows-Benutzernamen und ein Kennwort.  
  
 Die in Anmeldeinformationen gespeicherten Informationen ermöglichen einem Benutzer, der eine Verbindung mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] über die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Authentifizierung hergestellt hat, auf Ressourcen außerhalb der Serverinstanz zuzugreifen. Wenn es sich bei der externen Ressource um Windows handelt, wird der Benutzer als der in den Anmeldeinformationen angegebene Windows-Benutzer authentifiziert. Eine einzelne Anmeldung kann mehreren [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldungen zugeordnet werden. Eine [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Anmeldung kann allerdings nur einer Anmeldung zugeordnet werden.  
  
 Informationen zu Anmeldeinformationen, die in der Masterdatenbank gespeichert sind und in der gesamten Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verwendet werden können, finden Sie unter [CREATE CREDENTIAL &#40;Transact-SQL&#41;](../../../t-sql/statements/create-credential-transact-sql.md). Informationen zu Anmeldeinformationen, die von einer bestimmten Datenbank verwendet werden und mit dieser Datenbank portabel sind, finden Sie unter [CREATE DATABASE SCOPED CREDENTIAL &#40;Transact-SQL&#41;](../../../t-sql/statements/create-database-scoped-credential-transact-sql.md).  
  
 Systemanmeldeinformationen werden automatisch erstellt und mit bestimmten Endpunkten verbunden. Namen für Systemanmeldeinformationen beginnen mit zwei Nummernzeichen (##).  
  
 Weitere Informationen zu Anmeldeinformationen finden Sie in den Katalogansichten [sys.credentials](../../../relational-databases/system-catalog-views/sys-credentials-transact-sql.md) und [sys.database_scoped_credentials](../../../relational-databases/system-catalog-views/sys-database-scoped-credentials-transact-sql.md).  
  
## <a name="related-content"></a>Verwandte Inhalte  
 [Erstellen von Anmeldeinformationen](../../../relational-databases/security/authentication-access/create-a-credential.md)   
 [CREATE CREDENTIAL &#40;Transact-SQL&#41;](../../../t-sql/statements/create-credential-transact-sql.md)   
 [CREATE DATABASE SCOPED CREDENTIAL &#40;Transact-SQL&#41;](../../../t-sql/statements/create-database-scoped-credential-transact-sql.md)  
 [Sichern von SQL Server](../../../relational-databases/security/securing-sql-server.md)  
  
  
