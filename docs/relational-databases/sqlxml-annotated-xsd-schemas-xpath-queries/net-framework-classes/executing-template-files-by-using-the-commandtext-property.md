---
title: Ausführen von Vorlagendateien mit der CommandText-Eigenschaft | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: sqlxml
ms.reviewer: ''
ms.suite: sql
ms.technology: xml
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], executing template files
- SQLXML Managed Classes, executing template files
- templates [SQLXML], SQLXML Managed Classes
- executing template files [SQLXML]
- CommandText property
ms.assetid: f1b1278d-252d-4a06-836e-4ef77f338ef9
caps.latest.revision: 21
author: douglaslMS
ms.author: douglasl
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: 5a6079aa56a74b85eddb9b9fa1135be008015cce
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39563984"
---
# <a name="executing-template-files-by-using-the-commandtext-property"></a>Ausführen von Vorlagendateien mit der 'CommandText'-Eigenschaft
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  In diesem Beispiel wird veranschaulicht, wie die Vorlagendateien, die aus SQL- oder XPath-Abfragen bestehende Vorlagendateien mithilfe der CommandTextproperty angegeben werden können. Statt die SQL- oder XPath-Abfrage als der Wert der CommandText-Eigenschaft anzugeben, können Sie einen Dateinamen als Wert angeben. Im folgenden Beispiel wird die CommandType-Eigenschaft als SqlXmlCommandType.TemplateFile angegeben.  
  
 Diese Vorlage wird von der Beispielanwendung ausgeführt:  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
    SELECT TOP 2 ContactID, FirstName, LastName   
    FROM   Person.Contact  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 Dies ist der C#-beispielanwendung. Um die Anwendung zu testen, speichern Sie die Vorlage (TemplateFile.xml), und führen Sie dann die Anwendung aus.  
  
> [!NOTE]  
>  Im Code müssen Sie den Namen der Instanz von Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
  
      public static int testParams()  
      {  
         //Stream strm;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandType = SqlXmlCommandType.TemplateFile;  
         cmd.CommandText = "TemplateFile.xml";  
         using (Stream strm = cmd.ExecuteStream()){  
            using (StreamReader sr = new StreamReader(strm)){  
                Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
  
         return 0;        
      }  
      public static int Main(String[] args)  
      {  
         testParams();     
         return 0;  
      }  
   }  
```  
  
### <a name="to-test-the-application"></a>So testen Sie die Anwendung  
  
1.  Stellen Sie sicher, dass [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework auf dem Computer installiert ist.  
  
2.  Speichern Sie die in diesem Beispiel bereitgestellte XML-Vorlage in einem Ordner.  
  
3.  Speichern Sie die c#-Code (DocSample.cs), der bereitgestellt wird, in diesem Beispiel im selben Ordner, in dem das Schema gespeichert ist. (Wenn Sie die Dateien in einem anderen Ordner speichern, müssen Sie den Code bearbeiten und den entsprechenden Verzeichnispfad für das Zuordnungsschema angeben.)  
  
4.  Kompilieren Sie den Code. Verwenden Sie zur Kompilierung des Codes an der Eingabeaufforderung die folgende Zeichenfolge:  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     Dadurch wird eine ausführbare Datei (DocSample.exe) erstellt.  
  
5.  Führen Sie DocSample.exe an der Eingabeaufforderung aus.  
  
 Wenn Sie einen Parameter in eine Vorlage übergeben, muss der Name des Parameters mit at-Zeichen beginnen (@); z. B. p.Name= "\@ContactID", wobei p ein SqlXmlParameter-Objekt.  
  
 Dies ist die aktualisierte Vorlage, die einen Parameter annimmt.  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:header>  
     <sql:param name='ContactID'>1</sql:param>    
  </sql:header>  
  <sql:query>  
    SELECT ContactID, FirstName, LastName  
    FROM   Person.Contact  
    WHERE  ContactID=@ContactID  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 Dies ist der aktualisierte Code, in dem ein Parameter übergeben wird, um die Vorlage auszuführen.  
  
```  
public static int testParams()  
{  
  
   Stream strm;  
   SqlXmlParameter p;  
  
   SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
   cmd.CommandType = SqlXmlCommandType.TemplateFile;  
   cmd.CommandText = "TemplateFile.xml";  
   p = cmd.CreateParameter();  
   p.Name="@ContactID";  
   p.Value = "1";  
   strm = cmd.ExecuteStream();  
   StreamReader sw = new StreamReader(strm);  
   Console.WriteLine(sw.ReadToEnd());  
   return 0;        
}  
```  
  
  
