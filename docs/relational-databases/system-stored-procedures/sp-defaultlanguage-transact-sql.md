---
title: Sp_defaultlanguage (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_defaultlanguage
- sp_defaultlanguage_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_defaultlanguage
ms.assetid: 908d01cc-e704-45d9-9e85-d2df6da3e6f5
caps.latest.revision: 15
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: a382ceab3491cfbcd1b8d6dad564f6d8826c2d13
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38049498"
---
# <a name="spdefaultlanguage-transact-sql"></a>sp_defaultlanguage (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Ändert die Standardsprache für einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldenamen.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Verwendung [ALTER LOGIN](../../t-sql/statements/alter-login-transact-sql.md) stattdessen.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sp_defaultlanguage [ @loginame = ] 'login'   
     [ , [ @language = ] 'language' ]   
```  
  
## <a name="arguments"></a>Argumente  
 [ **@loginame =** ] **'***login***'**  
 Der Anmeldename. *login* ist vom Datentyp **sysname**und hat keinen Standardwert. *Anmeldung* kann sein, eine vorhandene [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Anmeldung oder einen Windows-Benutzer oder eine Gruppe.  
  
 [  **@language =** ] **"***Sprache***"**  
 Die Standardsprache der Anmeldung. *language* ist vom Datentyp **sysname**und hat den Standardwert NULL. *Sprache* muss eine gültige Sprache auf dem Server sein. Wenn *Sprache* nicht angegeben ist, *Sprache* festgelegt ist, um die Standardsprache des Servers; Standardsprache wird definiert, indem die **Sp_configure** Konfigurationsvariable **Standardsprache**. Wird die Standardsprache des Servers geändert, ändert sich dadurch nicht die Standardsprache der vorhandenen Anmeldenamen.  
  
## <a name="return-code-values"></a>Rückgabecodewerte  
 0 (Erfolg) oder 1 (Fehler)  
  
## <a name="remarks"></a>Hinweise  
 **Sp_defaultlanguage** ruft ALTER LOGIN auf, wodurch zusätzliche Optionen unterstützt. Weitere Informationen zum Ändern anderer Standardwerte für Anmeldenamen, finden Sie unter [ALTER LOGIN &#40;Transact-SQL&#41;](../../t-sql/statements/alter-login-transact-sql.md).  
  
 Mit der SET LANGUAGE-Anweisung können Sie die Sprache der aktuellen Sitzung ändern. Verwenden der @@LANGUAGE Funktion, um die aktuelle Spracheinstellung anzeigen.  
  
 Wenn die Standardsprache eines Anmeldenamens vom Server gelöscht wird, übernimmt der Anmeldename die Standardsprache des Servers. **Sp_defaultlanguage** kann nicht innerhalb einer benutzerdefinierten Transaktion ausgeführt werden.  
  
 Informationen zu den Sprachen, die auf dem Server installiert werden in der **sys.syslanguages** -Katalogsicht angezeigt.  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die ALTER ANY LOGIN-Berechtigung.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird `ALTER LOGIN` zum Ändern der Standardsprache für den Anmeldenamen `Fathima` auf Arabisch geändert. Dies ist die bevorzugte Methode.  
  
```  
ALTER LOGIN Fathima WITH DEFAULT_LANGUAGE = Arabic;  
GO  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Security Stored Procedures &#40;Transact-SQL&#41; (Gespeicherte Sicherheitsprozeduren (Transact-SQL))](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [ALTER LOGIN &#40;Transact-SQL&#41;](../../t-sql/statements/alter-login-transact-sql.md)   
 [@@LANGUAGE &#40;Transact-SQL&#41;](../../t-sql/functions/language-transact-sql.md)   
 [SET-Anweisungen (Transact-SQL)](../../t-sql/statements/set-statements-transact-sql.md)   
 [Sys.syslanguages &#40;Transact-SQL&#41;](../../relational-databases/system-compatibility-views/sys-syslanguages-transact-sql.md)   
 [Gespeicherte Systemprozeduren &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
