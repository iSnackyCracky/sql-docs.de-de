---
title: DATEDIFF (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/29/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- DATEDIFF_TSQL
- DATEDIFF
dev_langs:
- TSQL
helpviewer_keywords:
- dates [SQL Server], functions
- DATEDIFF function [SQL Server]
- time [SQL Server], crossed boundaries
- differences in date and time [SQL Server]
- counting crossed date time boundaries [SQL Server]
- date and time [SQL Server], DATEDIFF
- dates [SQL Server], crossed boundaries
- boundary differences date and time [SQL Server]
- functions [SQL Server], time
- functions [SQL Server], date and time
- interval dates [SQL Server]
- time [SQL Server], functions
- crossing date time boundaries [SQL Server]
- calculating dates times [SQL Server]
ms.assetid: eba979f2-1a8d-4cce-9d75-b74f9b519b37
caps.latest.revision: 52
author: MashaMSFT
ms.author: mathoma
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: 5082f8c97b0bf35534a02fd2b0690f43a99ebc81
ms.sourcegitcommit: e02c28b0b59531bb2e4f361d7f4950b21904fb74
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39459914"
---
# <a name="datediff-transact-sql"></a>DATEDIFF (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

Diese Funktion gibt die Anzahl (ganze Zahl mit Vorzeichen) der angegebenen „datepart“-Begrenzungen zurück, die zwischen den angegebenen Werten für *startdate* und *enddate* überschritten wurden.
  
Unter [DATEDIFF_BIG &#40;Transact-SQL&#41;](../../t-sql/functions/datediff-big-transact-sql.md) finden Sie eine Funktion, die größere Unterschiede zwischen den *startdate*- und *enddate*-Werten behandelt. Unter [Datums- und Uhrzeitdatentypen und zugehörige Funktionen &#40;Transact-SQL&#41;](../../t-sql/functions/date-and-time-data-types-and-functions-transact-sql.md) finden Sie eine Übersicht über alle [!INCLUDE[tsql](../../includes/tsql-md.md)] Datums- und Uhrzeitdatentypen und zugehörige Funktionen.
  
![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntax  
  
```sql
DATEDIFF ( datepart , startdate , enddate )  
```  
  
## <a name="arguments"></a>Argumente  
*datepart*  
Der Teil von *startdate* und *enddate*, der den Typ der überschrittenen Begrenzung angibt. `DATEDIFF` akzeptiert keine benutzerdefinierten Variablenentsprechungen. In der folgenden Tabelle werden alle gültigen *datepart*-Argumente aufgeführt.
  
|*datepart*|Abkürzungen|  
|---|---|
|**year**|**yy, yyyy**|  
|**quarter**|**qq, q**|  
|**month**|**mm, m**|  
|**dayofyear**|**dy, y**|  
|**day**|**dd, d**|  
|**week**|**wk, ww**|  
|**hour**|**hh**|  
|**minute**|**mi, n**|  
|**second**|**ss, s**|  
|**millisecond**|**ms**|  
|**microsecond**|**mcs**|  
|**nanosecond**|**ns**|  
  
*startdate*  
Ein Ausdruck, der in einen der folgenden Werte aufgelöst werden kann:

+ **Datum**
+ **datetime**
+ **datetimeoffset**
+ **datetime2** 
+ **smalldatetime**
+ **Uhrzeit**
  
Um Mehrdeutigkeiten zu vermeiden, sollten Sie vierstellige Jahreszahlen verwenden. Informationen zu zweistelligen Jahreszahlen finden Sie unter [Konfigurieren der Serverkonfigurationsoption „Umstellungsjahr für Angaben mit zwei Ziffern“](../../database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option.md).
  
*enddate*  
Weitere Informationen finden Sie unter *startdate*.
  
## <a name="return-type"></a>Rückgabetyp  
 **int**  
  
## <a name="return-value"></a>Rückgabewert  
  
-   Alle spezifischen *datepart*-Werte und die Abkürzungen für diese *datepart*-Werte geben den gleichen Wert zurück.  
  
Bei einem Rückgabewert, der sich außerhalb des gültigen Bereichs für **int** (-2,147,483,648 bis + 2,147,483,647) befindet, gibt `DATEDIFF` einen Fehler zurück.  Der maximale Unterschied zwischen *startdate* und *enddate* beträgt für **millisecond** 24 Tage, 20 Stunden, 31 Minuten und 23,647 Sekunden. Für **second** beträgt der maximale Unterschied 68 Jahre.
  
Wenn *startdate* und *enddate* jeweils nur ein Uhrzeitwert zugewiesen ist und *datepart* kein Zeit-*datepart* ist, gibt `DATEDIFF` 0 (null) zurück.
  
Beim Berechnen des Rückgabewerts verwendet `DATEDIFF` keine Komponente von *startdate* oder *enddate* für den Zeitzonenoffset.
  
Da [smalldatetime](../../t-sql/data-types/smalldatetime-transact-sql.md) nur auf die Minute genaue Werte zurückgibt, werden im Rückgabewert die Sekunden und Millisekunden immer auf 0 (null) festgelegt, wenn *startdate* oder *enddate* einen **smalldatetime**-Wert aufweist.
  
Wenn der Variablen eines Datumsdatentyps nur ein Uhrzeitwert zugewiesen ist, legt `DATEDIFF` den Wert für den fehlenden Datumsteil auf den Standardwert fest: 1900-01-01. Wenn der Variablen eines Uhrzeit- oder Datumsdatentyps nur ein Datumswert zugewiesen ist, legt `DATEDIFF` den Wert des fehlenden Uhrzeitteils auf den Standardwert fest: 00:00:00. Wenn entweder *startdate* oder *enddate* nur über einen Uhrzeitteil und der andere nur über einen Datumsteil verfügt, legt `DATEDIFF` für die fehlenden Uhrzeit- und Datumstypen die Standardwerte fest.
  
Wenn *startdate* und *enddate* unterschiedliche Datumsdatentypen aufweisen und ein Datentyp mehr Uhrzeitteile oder eine höhere Genauigkeit bezüglich der Bruchteile von Sekunden aufweist als der andere Teil, legt `DATEDIFF` für die fehlenden Teile des anderen Datentyps 0 (null) fest.
  
## <a name="datepart-boundaries"></a>datepart-Begrenzungen  
Die folgenden Anweisungen weisen bei *startdate* und *enddate* den gleichen Wert auf. Die Datumsangaben folgen aufeinander und unterscheiden sich in der Uhrzeit um 0,0000001 Sekunden. Der Unterschied zwischen *startdate* und *enddate* in jeder Anweisung überschreitet eine Kalender- oder Uhrzeitbegrenzung des zugehörigen *datepart*. Jede Anweisung gibt 1 zurück. Wenn *startdate* und *enddate* unterschiedliche Jahreswerte aufweisen, die Kalenderwochenwerte jedoch identisch sind, gibt `DATEDIFF` für den *datepart*-Wert **week** 0 (null) zurück.
  
```sql
SELECT DATEDIFF(year,        '2005-12-31 23:59:59.9999999', '2006-01-01 00:00:00.0000000');
SELECT DATEDIFF(quarter,     '2005-12-31 23:59:59.9999999', '2006-01-01 00:00:00.0000000');
SELECT DATEDIFF(month,       '2005-12-31 23:59:59.9999999', '2006-01-01 00:00:00.0000000');
SELECT DATEDIFF(dayofyear,   '2005-12-31 23:59:59.9999999', '2006-01-01 00:00:00.0000000');
SELECT DATEDIFF(day,         '2005-12-31 23:59:59.9999999', '2006-01-01 00:00:00.0000000');
SELECT DATEDIFF(week,        '2005-12-31 23:59:59.9999999', '2006-01-01 00:00:00.0000000');
SELECT DATEDIFF(hour,        '2005-12-31 23:59:59.9999999', '2006-01-01 00:00:00.0000000');
SELECT DATEDIFF(minute,      '2005-12-31 23:59:59.9999999', '2006-01-01 00:00:00.0000000');
SELECT DATEDIFF(second,      '2005-12-31 23:59:59.9999999', '2006-01-01 00:00:00.0000000');
SELECT DATEDIFF(millisecond, '2005-12-31 23:59:59.9999999', '2006-01-01 00:00:00.0000000');
```
  
## <a name="remarks"></a>Remarks  
`DATEDIFF` kann in den Klauseln SELECT <list>, WHERE, HAVING, GROUP BY und ORDER BY verwendet werden.
  
`DATEDIFF` wandelt Zeichenfolgenliterale implizit in den **datetime2**-Typ um. Daher unterstützt `DATEDIFF` das Format YDM nicht, wenn das Datum als Zeichenfolge übergeben wird. Sie müssen die Zeichenfolge explizit in den Typ **datetime** oder **smalldatetime** umwandeln, um das YDM-Format zu verwenden.
  
Die Angabe von SET DATEFIRST hat keine Auswirkungen auf `DATEDIFF`. `DATEDIFF` verwendet immer Sonntag als ersten Wochentag, um sicherzustellen, dass die Funktion deterministisch ist.
  
## <a name="examples"></a>Beispiele  
In diesen Beispielen werden verschiedene Typen von Ausdrücken als Argumente für die Parameter *startdate* und *enddate* verwendet.
  
### <a name="a-specifying-columns-for-startdate-and-enddate"></a>A. Angeben von Spalten für startdate und enddate  
In diesem Beispiel wird die Anzahl der Tagesbegrenzungen berechnet, die von den Datumsangaben in zwei Spalten in einer Tabelle überschritten wurden.
  
```sql
CREATE TABLE dbo.Duration  
    (startDate datetime2, endDate datetime2);  
    
INSERT INTO dbo.Duration(startDate, endDate)  
    VALUES ('2007-05-06 12:10:09', '2007-05-07 12:10:09');  
    
SELECT DATEDIFF(day, startDate, endDate) AS 'Duration'  
    FROM dbo.Duration;  
-- Returns: 1  
```  
  
### <a name="b-specifying-user-defined-variables-for-startdate-and-enddate"></a>B. Angeben von benutzerdefinierten Variablen für startdate und enddate  
In diesem Beispiel werden benutzerdefinierte Variablen als Argumente für *startdate* und *enddate* verwendet.
  
```sql
DECLARE @startdate datetime2 = '2007-05-05 12:10:09.3312722';  
DECLARE @enddate   datetime2 = '2007-05-04 12:10:09.3312722';   
SELECT DATEDIFF(day, @startdate, @enddate);  
```  
  
### <a name="c-specifying-scalar-system-functions-for-startdate-and-enddate"></a>C. Angeben von skalaren Systemfunktionen für startdate und enddate  
In diesem Beispiel werden skalare Systemfunktionen als Argumente für *startdate* und *enddate* verwendet.
  
```sql
SELECT DATEDIFF(millisecond, GETDATE(), SYSDATETIME());  
```  
  
### <a name="d-specifying-scalar-subqueries-and-scalar-functions-for-startdate-and-enddate"></a>D. Angeben von skalaren Unterabfragen und skalaren Funktionen für startdate und enddate  
In diesem Beispiel werden skalare Unterabfragen und skalare Funktionen als Argumente für *startdate* und *enddate* verwendet.
  
```sql
USE AdventureWorks2012;  
GO  
SELECT DATEDIFF(day,
    (SELECT MIN(OrderDate) FROM Sales.SalesOrderHeader),  
    (SELECT MAX(OrderDate) FROM Sales.SalesOrderHeader));  
```  
  
### <a name="e-specifying-constants-for-startdate-and-enddate"></a>E. Angeben von Konstanten für startdate und enddate  
In diesem Beispiel werden Zeichenkonstanten als Argumente für *startdate* und *enddate* verwendet.
  
```sql
SELECT DATEDIFF(day,
   '2007-05-07 09:53:01.0376635',
   '2007-05-08 09:53:01.0376635');  
```  
  
### <a name="f-specifying-numeric-expressions-and-scalar-system-functions-for-enddate"></a>F. Angeben von numerischen Ausdrücken und skalaren Systemfunktionen für enddate  
In diesem Beispiel werden ein numerischer Ausdruck, `(GETDATE() + 1)`, und skalare Systemfunktionen, `GETDATE` und `SYSDATETIME`, als Argumente für *enddate* verwendet.
  
```sql
USE AdventureWorks2012;  
GO  
SELECT DATEDIFF(day, '2007-05-07 09:53:01.0376635', GETDATE() + 1)   
    AS NumberOfDays  
    FROM Sales.SalesOrderHeader;  
GO  
USE AdventureWorks2012;  
GO  
SELECT DATEDIFF(day, '2007-05-07 09:53:01.0376635', DATEADD(day, 1, SYSDATETIME())) AS NumberOfDays  
    FROM Sales.SalesOrderHeader;  
GO  
```  
  
### <a name="g-specifying-ranking-functions-for-startdate"></a>G. Angeben von Rangfolgefunktionen für startdate  
In diesem Beispiel wird eine Rangfolgefunktion als Argument für *startdate* verwendet.
  
```sql
USE AdventureWorks2012;  
GO  
SELECT p.FirstName, p.LastName  
    ,DATEDIFF(day, ROW_NUMBER() OVER (ORDER BY   
        a.PostalCode), SYSDATETIME()) AS 'Row Number'  
FROM Sales.SalesPerson s   
    INNER JOIN Person.Person p   
        ON s.BusinessEntityID = p.BusinessEntityID  
    INNER JOIN Person.Address a   
        ON a.AddressID = p.BusinessEntityID  
WHERE TerritoryID IS NOT NULL   
    AND SalesYTD <> 0;  
```  
  
### <a name="h-specifying-an-aggregate-window-function-for-startdate"></a>H. Angeben einer Aggregatfensterfunktion für startdate  
In diesem Beispiel wird eine Aggregatfensterfunktion als Argument für *startdate* verwendet.
  
```sql
USE AdventureWorks2012;  
GO  
SELECT soh.SalesOrderID, sod.ProductID, sod.OrderQty, soh.OrderDate,
    DATEDIFF(day, MIN(soh.OrderDate)   
        OVER(PARTITION BY soh.SalesOrderID), SYSDATETIME()) AS 'Total'  
FROM Sales.SalesOrderDetail sod  
    INNER JOIN Sales.SalesOrderHeader soh  
        ON sod.SalesOrderID = soh.SalesOrderID  
WHERE soh.SalesOrderID IN(43659, 58918);  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Beispiele: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] und [!INCLUDE[ssPDW](../../includes/sspdw-md.md)].  
In diesen Beispielen werden verschiedene Typen von Ausdrücken als Argumente für die Parameter *startdate* und *enddate* verwendet.
  
### <a name="i-specifying-columns-for-startdate-and-enddate"></a>I. Angeben von Spalten für startdate und enddate  
In diesem Beispiel wird die Anzahl der Tagesbegrenzungen berechnet, die von den Datumsangaben in zwei Spalten in einer Tabelle überschritten wurden.
  
```sql
CREATE TABLE dbo.Duration 
    (startDate datetime2, endDate datetime2);
    
INSERT INTO dbo.Duration (startDate, endDate)  
    VALUES ('2007-05-06 12:10:09', '2007-05-07 12:10:09');  
    
SELECT TOP(1) DATEDIFF(day, startDate, endDate) AS Duration  
    FROM dbo.Duration;  
-- Returns: 1  
```  
  
### <a name="j-specifying-scalar-subqueries-and-scalar-functions-for-startdate-and-enddate"></a>J. Angeben von skalaren Unterabfragen und skalaren Funktionen für startdate und enddate  
In diesem Beispiel werden skalare Unterabfragen und skalare Funktionen als Argumente für *startdate* und *enddate* verwendet.
  
```sql
-- Uses AdventureWorks  
  
SELECT TOP(1) DATEDIFF(day, (SELECT MIN(HireDate) FROM dbo.DimEmployee),  
    (SELECT MAX(HireDate) FROM dbo.DimEmployee))   
FROM dbo.DimEmployee;  
  
```  
  
### <a name="k-specifying-constants-for-startdate-and-enddate"></a>K. Angeben von Konstanten für startdate und enddate  
In diesem Beispiel werden Zeichenkonstanten als Argumente für *startdate* und *enddate* verwendet.
  
```sql
-- Uses AdventureWorks  
  
SELECT TOP(1) DATEDIFF(day,
    '2007-05-07 09:53:01.0376635',
    '2007-05-08 09:53:01.0376635') FROM DimCustomer;  
```  
  
### <a name="l-specifying-ranking-functions-for-startdate"></a>L. Angeben von Rangfolgefunktionen für startdate  
In diesem Beispiel wird eine Rangfolgefunktion als Argument für *startdate* verwendet.
  
```sql
-- Uses AdventureWorks  
  
SELECT FirstName, LastName,
    DATEDIFF(day, ROW_NUMBER() OVER (ORDER BY   
        DepartmentName), SYSDATETIME()) AS RowNumber  
FROM dbo.DimEmployee;  
```  
  
### <a name="m-specifying-an-aggregate-window-function-for-startdate"></a>M. Angeben einer Aggregatfensterfunktion für startdate  
In diesem Beispiel wird eine Aggregatfensterfunktion als Argument für *startdate* verwendet.
  
```sql
-- Uses AdventureWorks  
  
SELECT FirstName, LastName, DepartmentName,
    DATEDIFF(year, MAX(HireDate)  
        OVER (PARTITION BY DepartmentName), SYSDATETIME()) AS SomeValue  
FROM dbo.DimEmployee  
```  
  
## <a name="see-also"></a>Siehe auch
[DATEDIFF_BIG &#40;Transact-SQL&#41;](../../t-sql/functions/datediff-big-transact-sql.md)  
[CAST und CONVERT &#40;Transact-SQL&#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)
  
  


