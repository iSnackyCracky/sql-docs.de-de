---
title: DROP EXTERNAL LIBRARY (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/05/2018
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- DROP EXTERNAL LIBRARY
- DROP_EXTERNAL_LIBRARY_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- DROP EXTERNAL LIBRARY
author: HeidiSteen
ms.author: heidist
manager: cgronlund
monikerRange: '>=sql-server-2017||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: f17e31aca14d38a6d8c124ce28f2936c1b28957c
ms.sourcegitcommit: e02c28b0b59531bb2e4f361d7f4950b21904fb74
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39453034"
---
# <a name="drop-external-library-transact-sql"></a>DROP EXTERNAL LIBRARY (Transact-SQL)  
[!INCLUDE[tsql-appliesto-ss2017-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2017-xxxx-xxxx-xxx-md.md)]

Löscht eine vorhandene Paketbibliothek. Paketbibliotheken werden von unterstützten externen Runtimes wie R oder Python verwendet.

## <a name="syntax"></a>Syntax

```sql
DROP EXTERNAL LIBRARY library_name
[ AUTHORIZATION owner_name ];
```

### <a name="arguments"></a>Argumente

**library_name**

Gibt den Namen einer vorhandenen Paketbibliothek an.

Bibliotheken umfassen nur den Benutzer. Bibliotheksnamen müssen innerhalb des Kontexts eines bestimmten Benutzers oder Besitzers eindeutig sein.

**owner_name**

Gibt den Namen eines Benutzers oder einer Rolle an, der oder die die externe Bibliothek besitzt.

Datenbankbesitzer können Bibliotheken löschen, die von anderen Benutzern erstellt wurden.

## <a name="permissions"></a>Berechtigungen

Zum Löschen einer Bibliothek ist die Berechtigung ALTER ANY EXTERNAL LIBRARY erforderlich. Standardmäßig kann jeder Datenbankbesitzer oder der Besitzer des Objekts auch eine externe Bibliothek löschen.

### <a name="return-values"></a>Rückgabewerte

Eine Informationsmeldung wird zurückgegeben, wenn die Anweisung erfolgreich war.

## <a name="remarks"></a>Remarks

Im Gegensatz zu anderen `DROP`-Anweisungen in SQL Server unterstützt diese Anweisung das Angeben einer optionalen Autorisierungsklausel. Dies ermöglicht einem **dbo** oder Benutzer mit der Rolle **db_owner**, eine Paketbibliothek zu löschen, die von einem normalen Benutzer in die Datenbank hochgeladen wurde.

## <a name="examples"></a>Beispiele

Hinzufügen des benutzerdefinierten R-Pakets `customPackage` zu einer Datenbank:

```sql
CREATE EXTERNAL LIBRARY customPackage 
FROM (CONTENT = 'C:\temp\customPackage_v1.1.zip')
WITH (LANGUAGE = 'R');
GO
```

Löschen der `customPackage`-Bibliothek:

```sql
DROP EXTERNAL LIBRARY customPackage;
```

## <a name="see-also"></a>Siehe auch

[CREATE EXTERNAL LIBRARY (Transact-SQL)](create-external-library-transact-sql.md)  
[ALTER EXTERNAL LIBRARY (Transact-SQL)](alter-external-library-transact-sql.md)  
[sys.external_library_files](../../relational-databases/system-catalog-views/sys-external-library-files-transact-sql.md)  
[sys.external_libraries](../../relational-databases/system-catalog-views/sys-external-libraries-transact-sql.md)  

