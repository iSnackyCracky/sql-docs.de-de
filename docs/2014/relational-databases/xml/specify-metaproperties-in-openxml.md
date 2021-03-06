---
title: Angeben von Metaeigenschaften in OPENXML | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-xml
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- overflow in XML document [SQL Server]
- metaproperties [XML in SQL Server]
- unconsumed data
- extracting information of XML nodes [SQL Server]
- OPENXML statement, metaproperties
ms.assetid: 29bfd1c6-3f9a-43c4-924a-53d438e442f4
caps.latest.revision: 22
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: d57525fb8ed9ca6718f072ef20c9e2cefe8e7ba9
ms.sourcegitcommit: c8f7e9f05043ac10af8a742153e81ab81aa6a3c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2018
ms.locfileid: "39084032"
---
# <a name="specify-metaproperties-in-openxml"></a>Angeben von Metaeigenschaften in OPENXML
  Metaeigenschaftsattribute in einem XML-Dokument sind Attribute, die die Eigenschaften eines XML-Objekts (z. B. Element, Attribut oder ein beliebiger anderer DOM-Knoten) beschreiben. Diese Attribute sind nicht physisch im Text des XML-Dokuments enthalten. Vielmehr stellt OPENXML diese Metaeigenschaften für alle XML-Objekte bereit. Die Metaeigenschaften ermöglichen es Ihnen, Informationen (wie etwa die relative Position oder Namespaceinformationen) über XML-Knoten zu extrahieren. Diese Informationen bieten Ihnen mehr Details, als in der Textdarstellung zu sehen sind.  
  
 Sie können diese Metaeigenschaften Rowsetspalten in einer OPENXML-Anweisung mithilfe des *ColPattern* -Parameters zuordnen. Die Spalten enthalten die Werte der Metaeigenschaften, denen sie zugeordnet werden. Weitere Informationen zur Syntax von OPENXML finden Sie unter [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).  
  
 Für den Zugriff auf die Metaeigenschaftsattribute wird ein für SQL Server spezifischer Namespace bereitgestellt. Dieser Namespace **urn:schemas-microsoft-com:xml-metaprop** ermöglicht dem Benutzer den Zugriff auf die Metaeigenschaftsattribute. Wird das Ergebnis einer OPENXML-Abfrage in einem Rahmentabellenformat zurückgegeben, enthält die Rahmentabelle eine Spalte für jedes Metaeigenschaftsattribut (außer für die **xmltext** -Metaeigenschaft).  
  
 Einige der Metaeigenschaftsattribute werden zu Verarbeitungszwecken eingesetzt. So wird z. B. das **xmltext** -Metaeigenschaftsattribut zur Bearbeitung von Überlaufdaten verwendet. Die Bearbeitung von Überlaufdaten bezieht sich auf nicht verbrauchte, unverarbeitete Daten im Dokument. Eine der Spalten im von OPENXML generierten Rowset kann als Überlaufspalte identifiziert werden. Dazu ordnen Sie diese Spalte mithilfe des **ColPattern** -Parameters der *xmltext* -Metaeigenschaft zu. Die Spalte nimmt dann die Überlaufdaten auf. Der *flags* -Parameter bestimmt, ob die Spalte ausschließlich nicht verbrauchte Daten oder alle Daten enthalten soll.  
  
 In der folgenden Tabelle werden die Metaeigenschaftsattribute für jedes analysierte XML-Element aufgeführt. Mithilfe des Namespaces **urn:schemas-microsoft-com:xml-sql**kann auf diese Metaeigenschaftsattribute zugegriffen werden. Jeder Wert, der direkt vom Benutzer im XML-Dokument mithilfe dieser Metaeigenschaften festgelegt wird, bleibt unberücksichtigt.  
  
> [!NOTE]  
>  Sie können in XPath-Navigationen nicht auf diese Metaeigenschaften verweisen.  
  
|Metaeigenschaftsattribut|Description|  
|----------------------------|-----------------|  
|**\@MP:ID**|Stellt einen systemgenerierten, dokumentweiten Bezeichner des DOM-Knotens bereit. Dieser Bezeichner verweist auf denselben XML-Knoten, solange das Dokument nicht erneut analysiert wird.<br /><br /> Eine XML-ID von **0** zeigt an, dass es sich bei dem Element um ein Stammelement handelt. Die übergeordnete XML-ID ist NULL.|  
|**\@MP:LocalName**|Speichert den lokalen Teil des Knotennamens. Die Metaeigenschaft wird mit einem Präfix und einem Namespace-URI (Uniform Resource Identifier) zur Benennung von Element- oder Attributknoten verwendet.|  
|**\@MP:NamespaceURI**|Gibt den Namespace-URI des aktuellen Elements an. Ist der Wert dieses Attributs NULL, ist kein Namespace vorhanden.|  
|**\@MP:prefix**|Speichert das Namespacepräfix des aktuellen Elementnamens.<br /><br /> Wenn kein Präfix vorhanden ist (NULL) und ein URI angegeben ist, zeigt dieses Attribut an, dass der angegebene Namespace der Standardnamespace ist. Ist kein URI angegeben, wird kein Namespace angefügt.|  
|**\@MP:Prev**|Speichert das vorhergehende gleichgeordnete Objekt eines Knotens. Dadurch werden Informationen über die Reihenfolge der Elemente im Dokument bereitgestellt.<br /><br /> **\@MP:Prev** enthält die XML-ID des vorhergehenden gleichgeordneten Objekts, das über dasselbe übergeordnete Element verfügt. Wenn ein Element am Anfang der Liste der gleichgeordneten Objekte aufgeführt, ist  **\@Mp:prev** ist NULL.|  
|**\@MP:xmltext**|Wird zu Verarbeitungszwecken genutzt. Legt die Textserialisierung des Elements und der zugehörigen Attribute und auch die Teilelemente fest, wie dies bei der Überlaufbearbeitung von OPENXML der Fall ist.|  
  
 In dieser Tabelle werden die zusätzlichen Eigenschaften übergeordneter Metaeigenschaftsattribute dargestellt, die Ihnen das Abrufen von Hierarchieinformationen ermöglichen.  
  
|Übergeordnetes Metaeigenschaftsattribut|Description|  
|-----------------------------------|-----------------|  
|**\@MP:parentId**|Entspricht **... /\@Mp:id**|  
|**\@MP:parentlocalname**|Entspricht **... /\@Mp:localname**|  
|**\@MP:parentnamespacerui**|Entspricht **... /\@Mp:namespaceuri**|  
|**\@MP:parentprefix**|Entspricht **... /\@Mp:prefix**|  
  
## <a name="examples"></a>Beispiele  
 In den folgenden Beispielen wird die Verwendung von OPENXML zum Erstellen unterschiedlicher Rowsetsichten veranschaulicht.  
  
### <a name="a-mapping-the-openxml-rowset-columns-to-the-metaproperties"></a>A. Zuordnen der OPENXML-Rowsetspalten zu den Metaeigenschaften  
 In diesem Beispiel wird OPENXML zum Erstellen einer Rowsetsicht des XML-Beispieldokuments verwendet. Es veranschaulicht das Zuordnen verschiedener Metaeigenschaftsattribute zu Rowsetspalten in der OPENXML-Anweisung mithilfe des *ColPattern* -Parameters.  
  
 Die OPENXML-Anweisung verdeutlicht Folgendes:  
  
-   Die **Id** Spalte zugeordnet ist die  **\@Mp:id** Metaeigenschaftsattribut und gibt an, dass die Spalte die systemgenerierte eindeutige XML-ID des Elements enthält.  
  
-   Die **übergeordneten** Spalte zugeordnet ist  **\@Mp:parentid** und gibt an, dass die Spalte die XML-ID des übergeordneten Elements des Elements enthält.  
  
-   Die **ParentLocalName** Spalte zugeordnet ist  **\@Mp:parentlocalname** und gibt an, dass die Spalte den lokalen Namen des übergeordneten Elements enthält.  
  
 Schließlich gibt die SELECT-Anweisung das von OPENXML bereitgestellte Rowset zurück.  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
-- Sample XML document  
SET @doc = N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/root/Customer/Order', 9)  
      WITH (id int '@mp:id',   
            oid char(5),   
            date datetime,   
            amount real,   
            parentIDNo int '@mp:parentid',   
            parentLocalName varchar(40) '@mp:parentlocalname')  
EXEC sp_xml_removedocument @idoc  
```  
  
 Dies ist das Ergebnis:  
  
```  
id   oid         date                amount    parentIDNo  parentLocalName    
--- ------- ---------------------- ---------- ------------ ---------------  
6    O1    1996-01-20 00:00:00.000     3.5         2        Customer  
10   O2    1997-04-30 00:00:00.000     13.4        2        Customer  
19   O3    1999-07-14 00:00:00.000     100.0       15       Customer  
25   O4    1996-01-20 00:00:00.000     10000.0     15       Customer  
```  
  
### <a name="b-retrieving-the-whole-xml-document"></a>B. Abrufen des gesamten XML-Dokuments  
 In diesem Beispiel wird mithilfe von OPENXML eine einspaltige Rowsetsicht des XML-Beispieldokuments erstellt. Diese Spalte **Col1**wird der **xmltext** -Metaeigenschaft zugeordnet und wird zu einer Überlaufspalte. Deshalb nimmt die Spalte die nicht verbrauchten Daten auf. In diesem Fall handelt es sich dabei um das gesamte Dokument.  
  
 Schließlich gibt die SELECT-Anweisung das vollständige Rowset zurück.  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
SET @doc = N'<?xml version="1.0"?>  
<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very   
             satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
     <MyTag>Testing to see if all the subelements are returned</MyTag>  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/')  
   WITH (Col1 ntext '@mp:xmltext')  
```  
  
 Um das gesamte Dokument ohne die XML-Deklaration abzurufen, kann die Abfrage wie folgt angegeben werden:  
  
```  
SELECT *  
FROM OPENXML (@idoc, '/root')  
   WITH (Col1 ntext '@mp:xmltext')  
EXEC sp_xml_removedocument @idoc  
```  
  
 Die Abfrage gibt das Stammelement mit dem Namensstammverzeichnis sowie die Daten des Stammelements zurück.  
  
### <a name="c-specifying-the-xmltext-metaproperty-to-retrieve-the-unconsumed-data-in-a-column"></a>C. Angeben der xmltext-Metaeigenschaft zur Abfrage der nicht verbrauchten Daten in einer Spalte  
 In diesem Beispiel wird OPENXML zum Erstellen einer Rowsetsicht des XML-Beispieldokuments verwendet. Das Beispiel veranschaulicht die Abfrage nicht verbrauchter XML-Daten durch Zuordnen des **xmltext** -Metaeigenschaftsattributs zu einer Rowsetspalte in OPENXML.  
  
 Die **Kommentar** Spalte wird als Überlaufspalte durch Zuordnen zur identifiziert die  **\@Mp:xmltext** Metaeigenschaften. Der *flags* -Parameter wird auf **9** festgelegt (XML_ATTRIBUTE and XML_NOCOPY). Dies zeigt die **attributzentrierte** Zuordnung an und dass ausschließlich nicht verbrauchte Daten in die Überlaufspalte kopiert werden sollten.  
  
 Schließlich gibt die SELECT-Anweisung das von OPENXML bereitgestellte Rowset zurück.  
  
 In diesem Beispiel die  **\@Mp:parentlocalname** Metaeigenschaft für eine Spalte festgelegt ist **ParentLocalName**, in dem von OPENXML generierten Rowset. Folglich enthält diese Spalte den lokalen Namen des übergeordneten Elements.  
  
 Es werden zwei zusätzliche Spalten im Rowset angegeben ( **parent** und **comment**). Die **übergeordneten** Spalte zugeordnet ist  **\@Mp:parentid** und gibt an, dass die Spalte die XML-ID des übergeordneten Elements des Elements enthält. Die Comment-Spalte wird als Überlaufspalte durch Zuordnen zur identifiziert die  **\@Mp:xmltext** Metaeigenschaften.  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
-- sample XML document  
SET @doc = N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>  
'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/root/Customer/Order', 9)  
      WITH (oid char(5),   
            date datetime,  
            comment ntext '@mp:xmltext')  
EXEC sp_xml_removedocument @idoc  
```  
  
 Dies ist das Ergebnis. Da die Spalten oid und date bereits verbraucht sind, werden sie nicht mehr in der Überlaufspalte angezeigt.  
  
```  
oid   date                        comment                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            
----- --------------------------- ----------------------------------------  
O1    1996-01-20 00:00:00.000     <Order amount="3.5"/>  
O2    1997-04-30 00:00:00.000     <Order amount="13.4">Customer was very   
                                   satisfied</Order>  
O3    1999-07-14 00:00:00.000     <Order amount="100" note="Wrap it blue   
                                   white red"><Urgency>   
                                   Important</Urgency></Order>  
O4    1996-01-20 00:00:00.000     <Order amount="10000"/>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql)   
 [OPENXML &#40;SQL Server&#41;](../xml/openxml-sql-server.md)  
  
  
