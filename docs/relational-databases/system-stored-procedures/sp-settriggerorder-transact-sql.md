---
title: Sp_settriggerorder (Transact-SQL) | Microsoft-Dokumentation
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
- sp_settriggerorder
- sp_settriggerorder_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_settriggerorder
ms.assetid: 8b75c906-7315-486c-bc59-293ef12078e8
caps.latest.revision: 54
author: edmacauley
ms.author: edmaca
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: 4045f8abefd08019f3b61fc2705f05f1bfa37f37
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39545580"
---
# <a name="spsettriggerorder-transact-sql"></a>sp_settriggerorder (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Gibt die AFTER-Trigger an, die zuerst oder zuletzt ausgelöst werden. Die AFTER-Trigger, die zwischen dem ersten und letzten Trigger ausgelöst werden, werden in einer nicht definierten Reihenfolge ausgeführt.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sp_settriggerorder [ @triggername = ] '[ triggerschema. ] triggername'   
    , [ @order = ] 'value'   
    , [ @stmttype = ] 'statement_type'   
    [ , [ @namespace = ] { 'DATABASE' | 'SERVER' | NULL } ]  
```  
  
## <a name="arguments"></a>Argumente  
 [  **@triggername=** ] **"**[ *Triggerschema ***.**] *Triggername *** "**  
 Der Name des Triggers, dessen Reihenfolge ggf. festgelegt oder geändert wird, und das Schema, zu dem er gehört. [*Triggerschema ***.**]* Triggername * ist **Sysname**. Wenn der Name keinem Trigger entspricht oder wenn der Name dem INSTEAD OF-Trigger entspricht, gibt die Prozedur einen Fehler zurück. *Triggerschema* kann nicht für DDL- oder Logon-Trigger angegeben werden.  
  
 [ **@order=** ] **'***Wert***'**  
 Die Einstellung für die neue Reihenfolge des Triggers. *Wert* ist **varchar(10)** und eine der folgenden Werte sind möglich.  
  
> [!IMPORTANT]  
>  Die **erste** und **letzten** Trigger müssen zwei unterschiedliche Trigger sein.  
  
|value|Description|  
|-----------|-----------------|  
|**Erster**|Trigger wird zuerst ausgelöst|  
|**Letzter**|Trigger wird zuletzt ausgelöst|  
|**Keine**|Trigger wird in nicht definierter Reihenfolge ausgelöst|  
  
 [  **@stmttype=** ] **"***Statement_type***"**  
 Gibt die SQL-Anweisung an, die den Trigger auslöst. *Statement_type* ist **varchar(50)-Spalte** möglich INSERT-, Update-, DELETE-, LOGON oder alle [!INCLUDE[tsql](../../includes/tsql-md.md)] Anweisungsereignis in aufgeführten [DDL-Ereignisse](../../relational-databases/triggers/ddl-events.md). Ereignisgruppen können nicht angegeben werden.  
  
 Ein Trigger kann gekennzeichnet werden, als die **erste** oder **letzten** Trigger für einen Anweisungstyp erst nach diesen Trigger als Trigger für diesen Anweisungstyp definiert wurde. Beispielsweise auslösen **TR1** kann festgelegt werden, **erste** Einfügung in Tabelle **T1** Wenn **TR1** als einen INSERT-Trigger definiert ist. Die [!INCLUDE[ssDE](../../includes/ssde-md.md)] gibt einen Fehler zurück, wenn **TR1**, die nur als INSERT-Trigger definiert wurde, wird als festgelegt ein **erste**, oder **letzten**,-Trigger für eine UPDATE-Anweisung. Weitere Informationen finden Sie im Abschnitt mit Hinweisen.  
  
 **@namespace=** { **'DATABASE'** | **'SERVER'** | NULL}  
 Wenn *Triggername* ein DDL-Triggers ist **@namespace** gibt an, ob *Triggername* mit Datenbankbereich oder dem Serverbereich erstellt wurde. Wenn *Triggername* ist ein Logon-Trigger muss SERVER angegeben werden. Weitere Informationen zu DDL-Triggerbereich, finden Sie unter [DDL-Trigger](../../relational-databases/triggers/ddl-triggers.md). Wenn nicht angegeben ist, oder wenn NULL angegeben wird, *Triggername* ein DML-Trigger.  
  
||  
|-|  
|SERVER gilt für: [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] bis [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].|  
  
## <a name="return-code-values"></a>Rückgabecodewerte  
 0 (Erfolg) oder 1 (Fehler)  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="dml-triggers"></a>DML-Trigger  
 Es kann nur eine **erste** eine **letzten** Trigger for each-Anweisung für eine einzelne Tabelle.  
  
 Wenn eine **erste** Trigger für die Tabelle, eine Datenbank oder ein Server bereits definiert ist, Sie können nicht bestimmen, einen neuen Trigger als **erste** für die gleiche Tabelle, eine Datenbank oder ein Server für den gleichen *Statement_type* . Diese Einschränkung gilt auch **letzten** Trigger.  
  
 Die Replikation generiert automatisch einen ersten Trigger für alle Tabellen, die in einem Abonnement mit sofortigem Update oder verzögertem Update über eine Warteschlange enthalten sind. Für die Replikation gilt, dass ihr Trigger der erste Trigger sein muss. Die Replikation meldet einen Fehler, wenn Sie versuchen, eine Tabelle, die einen ersten Trigger aufweist, in ein Abonnement mit sofortigem Update bzw. verzögertem Update über eine Warteschlange einzufügen. Wenn Sie versuchen, einen Trigger zum ersten Trigger zu erklären, nachdem eine Tabelle in ein Abonnement aufgenommen wurde, gibt **sp_settriggerorder** einen Fehler zurück. Wenn Sie ALTER TRIGGER für den Replikationstrigger verwenden oder **Sp_settriggerorder** so ändern Sie den Replikationstrigger in einen **letzten** oder **keine** Trigger, um das Abonnement ist nicht mehr ordnungsgemäß.  
  
## <a name="ddl-triggers"></a>DDL-Trigger  
 Wenn es sich bei einer DDL-Triggers mit Datenbankbereich und ein DDL-Trigger mit Serverbereich für das gleiche Ereignis vorhanden sind, können Sie angeben, dass beide Trigger eine **erste** Trigger oder eine **letzten** Trigger. Trigger mit einem Serverbereich werden jedoch immer zuerst ausgelöst. Im Allgemeinen ist die Reihenfolge der Auslösung von DDL-Triggern für das gleiche Ereignis Folgende:  
  
1.  Markiert der Trigger auf Serverebene **erste**.  
  
2.  Weitere Trigger auf Serverebene  
  
3.  Markiert der Trigger auf Serverebene **letzten**.  
  
4.  Markiert den Trigger auf Datenbankebene **erste**.  
  
5.  Weitere Trigger auf Datenbankebene  
  
6.  Markiert den Trigger auf Datenbankebene **letzten**.  
  
## <a name="general-trigger-considerations"></a>Allgemeine Überlegungen zu Triggern  
 Wenn eine ALTER TRIGGER-Anweisung einen ersten oder letzten Trigger ändert die **erste** oder **letzten** Attributgruppe, die ursprünglich für den Trigger gelöscht wird, und der Wert wird durch ersetzt **keine**. Der Reihenfolgewert muss mithilfe von **Sp_settriggerorder**.  
  
 Wenn derselbe Trigger muss, wie die ersten oder letzten Bestellung für mehr als einen Anweisungstyp festgelegt werden **Sp_settriggerorder** muss für jeden Anweisungstyp ausgeführt werden. Außerdem der Trigger muss zuerst definiert werden für einen Anweisungstyp, bevor es als bezeichnet werden, kann die **erste** oder **letzten** Trigger für den Anweisungstyp ausgelöst.  
  
## <a name="permissions"></a>Berechtigungen  
 Um die Reihenfolge eines DDL-Triggers mit Serverbereich (erstellt ON ALL SERVER) oder eines LOGON-Triggers festzulegen, ist die CONTROL SERVER-Berechtigung auf dem Server erforderlich.  
  
 Um die Reihenfolge eines DDL-Triggers mit Datenbankbereich (erstellt ON DATABASE) festzulegen, benötigen Sie die Berechtigung ALTER ANY DATABASE DDL TRIGGER.  
  
 Um die Reihenfolge eines DML-Triggers festzulegen, benötigen Sie die ALTER-Berechtigung für die Tabelle oder Sicht, in der der Trigger definiert wurde.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-setting-the-firing-order-for-a-dml-trigger"></a>A. Festlegen der Auslösungsreihenfolge für einen DML-Trigger  
 Im folgenden Beispiel wird angegeben, dass Trigger `uSalesOrderHeader` der erste Trigger ist, der nach Abschluss eines `UPDATE`-Vorgangs in der `Sales.SalesOrderHeader`-Tabelle ausgelöst wird.  
  
```  
USE AdventureWorks2012;  
GO  
sp_settriggerorder @triggername= 'Sales.uSalesOrderHeader', @order='First', @stmttype = 'UPDATE';  
```  
  
### <a name="b-setting-the-firing-order-for-a-ddl-trigger"></a>B. Festlegen der Auslösungsreihenfolge für einen DDL-Trigger  
 Im folgenden Beispiel wird angegeben, dass Trigger `ddlDatabaseTriggerLog` der erste Trigger ist, der nach einem `ALTER_TABLE`-Ereignis in der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]-Datenbank ausgelöst wird.  
  
```  
USE AdventureWorks2012;  
GO  
sp_settriggerorder @triggername= 'ddlDatabaseTriggerLog', @order='First', @stmttype = 'ALTER_TABLE', @namespace = 'DATABASE';  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Gespeicherte Systemprozeduren &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Datenbank-Engine gespeicherten Prozeduren &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/database-engine-stored-procedures-transact-sql.md)   
 [ALTER TRIGGER &#40;Transact-SQL&#41;](../../t-sql/statements/alter-trigger-transact-sql.md)  
  
  
