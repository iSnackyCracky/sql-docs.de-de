---
title: Verwenden von Auflistungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQL Server Management Objects, collections
- SMO [SQL Server], collections
- collections [SMO]
ms.assetid: 209eb175-2514-4de1-bc32-b2e6a469d945
caps.latest.revision: 47
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: e3a56d7b6335734f8ddc90ea1a4438e6b6ae1763
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37179617"
---
# <a name="using-collections"></a>Verwenden von Auflistungen
  Eine Auflistung ist eine Liste von Objekten, die aus der gleichen Objektklasse gebildet wurden und über dasselbe übergeordnete Objekt verfügen. Das Auflistungsobjekt enthält immer den Namen des Objekttyps mit dem Suffix „Collection“. Um beispielsweise auf die Spalten einer gegebenen Tabelle zuzugreifen, verwenden Sie den <xref:Microsoft.SqlServer.Management.Smo.ColumnCollection>-Objekttyp. Er enthält alle <xref:Microsoft.SqlServer.Management.Smo.Column>-Objekte, die zum gleichen <xref:Microsoft.SqlServer.Management.Smo.Table>-Objekt gehören.  
  
 Die [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `For...Each` Anweisung oder der [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] `foreach` Anweisung kann verwendet werden, um die einzelnen Elemente der Auflistung durchlaufen.  
  
## <a name="examples"></a>Beispiele  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="referencing-an-object-by-using-a-collection-in-visual-basic"></a>Verweisen auf ein Objekt mithilfe einer Auflistung in Visual Basic  
 In diesem Codebeispiel wird veranschaulicht, wie eine Spalteneigenschaft mithilfe Festlegen der <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A>, und <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A> Eigenschaften. Diese Eigenschaften repräsentieren Auflistungen, mit denen ein bestimmtes Objekt identifiziert werden kann, wenn sie mit einem Parameter verwendet werden, der den Namen des Objekts angibt. Der Name und das Schema sind erforderlich, damit die <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> auflistungsobjekteigenschaft.  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBCollections1](SMO How to#SMO_VBCollections1)]  -->  
  
## <a name="referencing-an-object-by-using-a-collection-in-visual-c"></a>Verweisen auf ein Objekt mithilfe einer Auflistung in Visual C#  
 In diesem Codebeispiel wird veranschaulicht, wie eine Spalteneigenschaft mithilfe Festlegen der <xref:Microsoft.SqlServer.Management.Smo.TableViewTableTypeBase.Columns%2A>, <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A>, und <xref:Microsoft.SqlServer.Management.Smo.Server.Databases%2A> Eigenschaften. Diese Eigenschaften repräsentieren Auflistungen, mit denen ein bestimmtes Objekt identifiziert werden kann, wenn sie mit einem Parameter verwendet werden, der den Namen des Objekts angibt. Der Name und das Schema sind erforderlich, damit die <xref:Microsoft.SqlServer.Management.Smo.Database.Tables%2A> auflistungsobjekteigenschaft.  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Modify a property using the Databases, Tables, and Columns collections to reference a column.   
srv.Databases("AdventureWorks2012").Tables("Person", "Person").Columns("LastName").Nullable = true;   
//Call the Alter method to make the change on the instance of SQL Server.   
srv.Databases("AdventureWorks2012").Tables("Person", "Person").Columns("LastName").Alter();   
}  
```  
  
## <a name="iterating-through-the-members-of-a-collection-in-visual-basic"></a>Durchlaufen der Elemente einer Auflistung in Visual Basic  
 Dieses Codebeispiel durchläuft die <xref:Microsoft.AnalysisServices.Server.Databases%2A> Sammlungseigenschaft und zeigt alle mit der Instanz von Datenbankverbindungen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBCollections2](SMO How to#SMO_VBCollections2)]  -->  
  
## <a name="iterating-through-the-members-of-a-collection-in-visual-c"></a>Durchlaufen der Elemente einer Auflistung in Visual C#  
 Dieses Codebeispiel durchläuft die <xref:Microsoft.AnalysisServices.Server.Databases%2A> Sammlungseigenschaft und zeigt alle mit der Instanz von Datenbankverbindungen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
int count = 0;   
int total = 0;   
//Iterate through the databases and call the GetActiveDBConnectionCount method.   
Database db = default(Database);   
foreach ( db in srv.Databases) {   
  count = srv.GetActiveDBConnectionCount(db.Name);   
  total = total + count;   
  //Display the number of connections for each database.   
  Console.WriteLine(count + " connections on " + db.Name);   
}   
//Display the total number of connections on the instance of SQL Server.   
Console.WriteLine("Total connections =" + total);   
}   
```  
  
  
