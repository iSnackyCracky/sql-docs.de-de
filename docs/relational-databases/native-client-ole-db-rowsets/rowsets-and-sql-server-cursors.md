---
title: Rowsets und SQL Server-Cursor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB rowsets, cursors
- SQL Server Native Client OLE DB provider, rowsets
- rowsets [OLE DB], cursors
- properties [OLE DB]
- cursors [OLE DB]
ms.assetid: 26a11e26-2a3a-451e-8f78-fba51e330ecb
caps.latest.revision: 31
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017'
ms.openlocfilehash: 95e1b7b3d92c74b7e2a57fc311cd7ccb407fa4fc
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39551030"
---
# <a name="rowsets-and-sql-server-cursors"></a>Rowsets und SQL Server-Cursor
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gibt Consumern Resultsets mit zwei Methoden zurück:  
  
-   Standardresultsets mit folgenden Funktionen:  
  
    -   Minimierung der Verwaltung  
  
    -   Maximale Leistung beim Abrufen der Daten  
  
    -   Unterstützung der standardmäßigen schreibgeschützten Vorwärtscursorfunktion  
  
    -   Zeilenweise Rückgabe an den Consumer  
  
    -   Unterstützung von nur jeweils einer aktiven Anweisung für eine Verbindung  
  
         Nachdem eine Anweisung ausgeführt wurde, kann die nächste Anweisung über diese Verbindung erst ausgeführt werden, wenn alle Ergebnisse vom Consumer abgerufen wurden oder die Anweisung abgebrochen wurde.  
  
    -   Unterstützung aller [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen  
  
-   Servercursor mit folgenden Funktionen:  
  
    -   Unterstützung aller Cursorfunktionen  
  
    -   Mögliche Rückgabe von Zeilenblöcken an den Consumer  
  
    -   Unterstützung mehrerer aktiver Anweisungen über eine einzelne Verbindung  
  
    -   Abwägen von Cursorfunktionalität gegenüber der Leistung  
  
         Die Unterstützung der Cursorfunktionalität kann die Leistung in Bezug auf ein Standardresultset verringern. Dieser Nachteil kann ausgeglichen werden, wenn der Consumer die Cursorfunktionalität zum Abrufen einer kleineren Zeilenmenge verwenden kann.  
  
    -   Keine Unterstützung einer [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung, die mehr als ein einzelnes Resultset zurückgibt  
  
 Consumer können andere Cursorverhaltensweisen in einem Rowset anfordern, indem sie bestimmte Rowseteigenschaften festlegen. Wenn der Consumer nicht eines dieser Rowseteigenschaften festlegt oder sie alle auf ihre Standardwerte festgelegt die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter implementiert das Rowset mit einem Standardresultset. Wenn eine dieser Eigenschaften auf einen anderen Wert als den Standardwert festgelegt ist die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter implementiert das Rowset mit einem Servercursor.  
  
 Die folgenden Rowseteigenschaften weisen den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter an, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Cursor zu verwenden. Einige Eigenschaften können mit anderen problemlos kombiniert werden. Ein Rowset mit den Eigenschaften DBPROP_IRowsetScroll und DBPROP_IRowsetChange entspricht beispielsweise einem Lesezeichenrowset mit sofortigem Updateverhalten. Andere Eigenschaften schließen sich hingegen gegenseitig aus. Zum Beispiel kann ein Rowset, das DBPROP_OTHERINSERT aufweist, keine Lesezeichen enthalten.  
  
|Eigenschafts-ID|value|Rowsetverhalten|  
|-----------------|-----------|---------------------|  
|DBPROP_SERVERCURSOR|VARIANT_TRUE|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Daten können nicht über das Rowset aktualisiert werden. Das Rowset ist sequenziell und unterstützt nur den Bildlauf vorwärts und das Abrufen. Die relative Zeilenpositionierung wird unterstützt. Befehlstext kann eine ORDER BY-Klausel enthalten.|  
|DBPROP_CANSCROLLBACKWARDS oder DBPROP_CANFETCHBACKWARDS|VARIANT_TRUE|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Daten können nicht über das Rowset aktualisiert werden. Das Rowset unterstützt das Durchführen eines Bildlaufs und das Abrufen in beiden Richtungen. Die relative Zeilenpositionierung wird unterstützt. Befehlstext kann eine ORDER BY-Klausel enthalten.|  
|DBPROP_BOOKMARKS oder DBPROP_LITERALBOOKMARKS|VARIANT_TRUE|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Daten können nicht über das Rowset aktualisiert werden. Das Rowset ist sequenziell und unterstützt nur den Bildlauf vorwärts und das Abrufen. Die relative Zeilenpositionierung wird unterstützt. Befehlstext kann eine ORDER BY-Klausel enthalten.|  
|DBPROP_OWNUPDATEDELETE oder DBPROP_OWNINSERT oder DBPROP_OTHERUPDATEDELETE|VARIANT_TRUE|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Daten können nicht über das Rowset aktualisiert werden. Das Rowset unterstützt das Durchführen eines Bildlaufs und das Abrufen in beiden Richtungen. Die relative Zeilenpositionierung wird unterstützt. Befehlstext kann eine ORDER BY-Klausel enthalten.|  
|DBPROP_OTHERINSERT|VARIANT_TRUE|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Daten können nicht über das Rowset aktualisiert werden. Das Rowset unterstützt das Durchführen eines Bildlaufs und das Abrufen in beiden Richtungen. Die relative Zeilenpositionierung wird unterstützt. Befehlstext kann eine ORDER BY-Klausel enthalten, wenn ein Index für die Spalten vorhanden ist, auf die verwiesen wird.<br /><br /> DBPROP_OTHERINSERT kann nicht VARIANT_TRUE sein, wenn das Rowset Lesezeichen enthält. Wenn Sie versuchen, ein Rowset mit dieser Visibility-Eigenschaft und Lesezeichen zu erstellen, wird ein Fehler ausgegeben.|  
|DBPROP_IRowsetLocate oder DBPROP_IRowsetScroll|VARIANT_TRUE|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Daten können nicht über das Rowset aktualisiert werden. Das Rowset unterstützt das Durchführen eines Bildlaufs und das Abrufen in beiden Richtungen. Lesezeichen und die absolute Positionierung durch die **IRowsetLocate**-Schnittstelle werden im Rowset unterstützt. Befehlstext kann eine ORDER BY-Klausel enthalten.<br /><br /> DBPROP_IRowsetLocate und DBPROP_IRowsetScroll erfordern Lesezeichen im Rowset. Wenn Sie versuchen, ein Rowset mit Lesezeichen und der DBPROP_OTHERINSERT-Eigenschaft zu erstellen, die auf VARIANT_TRUE festgelegt ist, tritt ein Fehler auf.|  
|DBPROP_IRowsetChange oder DBPROP_IRowsetUpdate|VARIANT_TRUE|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Daten können über das Rowset aktualisiert werden. Das Rowset ist sequenziell und unterstützt nur den Bildlauf vorwärts und das Abrufen. Die relative Zeilenpositionierung wird unterstützt. Alle Befehle, die für aktualisierbare Cursor verfügbar sind, können diese Schnittstellen unterstützen.|  
|DBPROP_IRowsetLocate oder DBPROP_IRowsetScroll und DBPROP_IRowsetChange oder DBPROP_IRowsetUpdate|VARIANT_TRUE|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Daten können über das Rowset aktualisiert werden. Das Rowset unterstützt das Durchführen eines Bildlaufs und das Abrufen in beiden Richtungen. Lesezeichen und die absolute Positionierung durch **IRowsetLocate** werden im Rowset unterstützt. Befehlstext kann eine ORDER BY-Klausel enthalten.|  
|DBPROP_IMMOBILEROWS|VARIANT_FALSE|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Daten können nicht über das Rowset aktualisiert werden. Das Rowset unterstützt nur den Bildlauf vorwärts. Die relative Zeilenpositionierung wird unterstützt. Befehlstext kann eine ORDER BY-Klausel enthalten, wenn ein Index für die Spalten vorhanden ist, auf die verwiesen wird.<br /><br /> DBPROP_IMMOBILEROWS ist nur in Rowsets verfügbar, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Zeilen anzeigen können, die von Befehlen in anderen Sitzungen oder von anderen Benutzern eingefügt wurden. Wenn Sie versuchen, ein Rowset mit einer auf VARIANT_FALSE festgelegten Eigenschaft für ein Rowset zu öffnen, für das DBPROP_OTHERINSERT nicht VARIANT_TRUE sein kann, tritt ein Fehler auf.|  
|DBPROP_REMOVEDELETED|VARIANT_TRUE|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Daten können nicht über das Rowset aktualisiert werden. Das Rowset unterstützt nur den Bildlauf vorwärts. Die relative Zeilenpositionierung wird unterstützt. Befehlstext kann eine ORDER BY-Klausel enthalten, sofern keine Beschränkung durch eine andere Eigenschaft vorliegt.|  
  
 Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieterrowset unterstützt, die ein Servercursor kann problemlos erstellt werden, auf eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Basistabelle oder Sicht mithilfe der **IOpenRowset:: OPENROWSET** Methode. Geben Sie die Tabelle oder die Sicht mit Namen an, indem die erforderlichen Eigenschaftensätze für das Rowset im *rgPropertySets*-Parameter übergeben werden.  
  
 Befehlstext, der ein Rowset erstellt, ist eingeschränkt, wenn der Consumer erfordert, dass das Rowset von einem Servercursor unterstützt wird. Der Befehlstext ist insbesondere entweder auf eine einzelne SELECT-Anweisung, die ein einzelnes Rowsetergebnis zurückgibt, oder auf eine gespeicherte Prozedur beschränkt, die eine einzelne SELECT-Anweisung implementiert, mit der ein einzelnes Rowsetergebnis zurückgegeben wird.  
  
 Diese beiden Tabellen zeigen die Zuordnungen verschiedener OLE DB-Eigenschaften sowie die Cursormodelle an. Sie geben außerdem Aufschluss darüber, welche Rowseteigenschaften festgelegt werden sollen, um einen bestimmten Cursormodelltyp zu verwenden.  
  
 Jede Zelle in der Tabelle enthält einen Wert der Rowseteigenschaft für das bestimmte Cursormodell. Der Datentyp aller bereits in diesem Thema aufgeführten Rowseteigenschaft lautet VT_BOOL und der Standardwert ist VARIANT_FALSE. In der Tabelle werden die folgenden Symbole verwendet.  
  
 F = Standardwert (VARIANT_FALSE)  
  
 T = VARIANT_TRUE  
  
 \- = VARIANT_TRUE oder VARIANT_FALSE  
  
 Um ein bestimmtes Cursormodell zu verwenden, suchen Sie die dem Cursormodell entsprechende Spalte, und suchen Sie alle Rowseteigenschaften mit dem Wert "T" in der Spalte. Legen Sie diese Rowseteigenschaften auf VARIANT_TRUE fest, um das gewünschte Cursormodell zu verwenden. Die Rowseteigenschaften mit dem Wert "-" können entweder auf VARIANT_TRUE oder VARIANT_FALSE festgelegt werden.  
  
|Rowseteigenschaften/Cursormodelle|Default<br /><br /> result<br /><br /> Menge<br /><br /> (RO)|Schnell<br /><br /> forward-<br /><br /> nur<br /><br /> (RO)|STATIC-Cursor<br /><br /> (RO)|Keyset<br /><br /> driven<br /><br /> (RO)|  
|--------------------------------------|-------------------------------------------|--------------------------------------------|-----------------------|----------------------------------|  
|DBPROP_SERVERCURSOR|V|T|T|T|  
|DBPROP_DEFERRED|V|V|-|-|  
|DBPROP_IrowsetChange|V|V|V|V|  
|DBPROP_IrowsetLocate|V|V|-|-|  
|DBPROP_IrowsetScroll|V|V|-|-|  
|DBPROP_IrowsetUpdate|V|V|V|V|  
|DBPROP_BOOKMARKS|V|V|-|-|  
|DBPROP_CANFETCHBACKWARDS|V|V|-|-|  
|DBPROP_CANSRCOLLBACKWARDS|V|V|-|-|  
|DBPROP_CANHOLDROWS|V|V|-|-|  
|DBPROP_LITERALBOOKMARKS|V|V|-|-|  
|DBPROP_OTHERINSERT|V|T|V|V|  
|DBPROP_OTHERUPDATEDELETE|V|T|V|T|  
|DBPROP_OWNINSERT|V|T|V|T|  
|DBPROP_OWNUPDATEDELETE|V|T|V|T|  
|DBPROP_QUICKSTART|V|V|-|-|  
|DBPROP_REMOVEDELETED|V|V|V|-|  
|DBPROP_IrowsetResynch|V|V|V|-|  
|DBPROP_CHANGEINSERTEDROWS|V|V|V|V|  
|DBPROP_SERVERDATAONINSERT|V|V|V|-|  
|DBPROP_UNIQUEROWS|-|V|V|V|  
|DBPROP_IMMOBILEROWS|-|-|-|T|  
  
|Rowseteigenschaften/Cursormodelle|Dynamic (RO)|Keyset (R/W)|Dynamic (R/W)|  
|--------------------------------------|--------------------|---------------------|----------------------|  
|DBPROP_SERVERCURSOR|T|T|T|  
|DBPROP_DEFERRED|-|-|-|  
|DBPROP_IrowsetChange|V|-|-|  
|DBPROP_IrowsetLocate|V|-|V|  
|DBPROP_IrowsetScroll|V|-|V|  
|DBPROP_IrowsetUpdate|V|-|-|  
|DBPROP_BOOKMARKS|V|-|V|  
|DBPROP_CANFETCHBACKWARDS|-|-|-|  
|DBPROP_CANSRCOLLBACKWARDS|-|-|-|  
|DBPROP_CANHOLDROWS|V|-|V|  
|DBPROP_LITERALBOOKMARKS|V|-|V|  
|DBPROP_OTHERINSERT|T|V|T|  
|DBPROP_OTHERUPDATEDELETE|T|T|T|  
|DBPROP_OWNINSERT|T|T|T|  
|DBPROP_OWNUPDATEDELETE|T|T|T|  
|DBPROP_QUICKSTART|-|-|-|  
|DBPROP_REMOVEDELETED|T|-|T|  
|DBPROP_IrowsetResynch|-|-|-|  
|DBPROP_CHANGEINSERTEDROWS|V|-|V|  
|DBPROP_SERVERDATAONINSERT|V|-|V|  
|DBPROP_UNIQUEROWS|V|V|V|  
|DBPROP_IMMOBILEROWS|V|T|V|  
  
 Für einen spezifischen Satz von Rowseteigenschaften wird das Cursormodell, das ausgewählt wird, wie folgt bestimmt.  
  
 Rufen Sie von der angegebenen Auflistung von Rowseteigenschaften eine Teilmenge von den in den vorherigen Tabellen aufgelisteten Eigenschaften ab. Teilen Sie diese Eigenschaften abhängig vom Flagwert – erforderlich (T, F) oder optional (-) – der jeweiligen Rowseteigenschaften in zwei Untergruppen auf. Beginnen Sie für jedes Cursormodell in der ersten Tabelle, und gehen Sie von links nach rechts vor. Vergleichen Sie die Werte der Eigenschaften in den beiden Untergruppen mit den Werten der entsprechenden Eigenschaften in dieser Spalte. Das Cursormodell, für das keine fehlende Übereinstimmung mit den erforderlichen Eigenschaften und die geringste Zahl fehlender Übereinstimmungen mit den optionalen Eigenschaften gefunden wird, wird ausgewählt. Wenn dies auf mehr als ein Cursormodell zutrifft, wird das am weitesten links stehende Modell ausgewählt.  
  
## <a name="sql-server-cursor-block-size"></a>Blockgröße des SQL Server-Cursors  
 Wenn eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Cursor unterstützt eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter-Rowset, die Anzahl der Elemente in der Zeile Arrayparameter des Zeilenhandles der **IRowset:: GetNextRows** oder **IRowsetLocate:: GetRowsAt**  Methoden definiert, die Blockgröße des Cursors. Die von den Handles im Array angegebenen Zeilen sind die Elemente des Cursorblocks.  
  
 Für Rowsets, die Lesezeichen unterstützen, werden die Elemente des Cursorblocks durch die mit der **IRowsetLocate::GetRowsByBookmark**-Methode abgerufenen Zeilenhandles definiert.  
  
 Der Cursorblock ist unabhängig von der Methode, die zum Auffüllen des Rowsets und zur Bildung des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Cursorblocks verwendet wird, aktiv, bis die nächste Methode zum Abrufen von Zeilen für das Rowset ausgeführt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md)  
  
  
