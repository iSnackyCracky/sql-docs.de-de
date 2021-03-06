---
title: Sp_helpconstraint (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_helpconstraint
- sp_helpconstraint_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_helpconstraint
ms.assetid: 29d6cd36-535d-4765-bca8-62f9d9886ff5
caps.latest.revision: 33
author: edmacauley
ms.author: edmaca
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: 9d2b4e51dc08ba897145d689d5ea6a918e3e7afb
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39559450"
---
# <a name="sphelpconstraint-transact-sql"></a>sp_helpconstraint (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Gibt eine Liste aller Einschränkungstypen zurück, deren benutzerdefinierte oder vom System angegebenen Namen, die Spalten, für die sie definiert wurden, und den Ausdruck, der die Einschränkung definiert (nur bei DEFAULT- und CHECK-Einschränkungen).  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sp_helpconstraint [ @objname = ] 'table'   
     [ , [ @nomsg = ] 'no_message' ]   
```  
  
## <a name="arguments"></a>Argumente  
 [  **@objname=** ] **"***Tabelle***"**  
 Die Tabelle, zu der Einschränkungsinformationen zurückgegeben werden. Die angegebene Tabelle muss für die aktuelle Datenbank lokal sein. *Tabelle* ist **nvarchar(776)**, hat keinen Standardwert.  
  
 [  **@nomsg=**] **"***No_message***"**  
 Ein optionaler Parameter, der den Tabellennamen ausgibt. *No_message* ist **varchar(5)**, hat den Standardwert **msg**. **Nomsg** unterdrückt die Ausgabe.  
  
## <a name="return-code-values"></a>Rückgabecodewerte  
 0 (Erfolg) oder 1 (Fehler)  
  
## <a name="result-sets"></a>Resultsets  
 **Sp_helpconstraint** zeigt eine absteigende indizierte Spalte an, wenn sie in Primärschlüsseln teilgenommen haben. Die absteigend indizierte Spalte wird im Resultset mit einem Minuszeichen (-) hinter dem Namen aufgelistet. Standardmäßig werden Spalten aufsteigend indiziert, diese werden nur mit dem Namen aufgelistet.  
  
## <a name="remarks"></a>Hinweise  
 Ausführen von **Sp_help *** Tabelle* liefert alle Informationen über die angegebene Tabelle. Um nur Informationen zu den Einschränkungen anzuzeigen, verwenden Sie **Sp_helpconstraint**.  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die Mitgliedschaft in der **public** -Rolle.  
  
## <a name="examples"></a>Beispiele  
 Das folgende Beispiel zeigt alle Einschränkungen für die Tabelle `Product` an.  
  
```  
USE AdventureWorks2012;  
GO  
EXEC sp_helpconstraint 'Production.Product';  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbank-Engine gespeicherten Prozeduren &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/database-engine-stored-procedures-transact-sql.md)   
 [ALTER TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-table-transact-sql.md)   
 [CREATE TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/create-table-transact-sql.md)   
 [sp_help &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-help-transact-sql.md)   
 [Gespeicherte Systemprozeduren &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [sys.key_constraints &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-key-constraints-transact-sql.md)   
 [Sys. check_constraints &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-check-constraints-transact-sql.md)   
 [Sys. default_constraints &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-default-constraints-transact-sql.md)  
  
  
