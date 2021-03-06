---
title: CreateRecordset-Methode (RDS) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- DataControl::CreateRecordset
- RDS.DataControl::CreateRecordset
- CreateRecordset
- RDSServer.DataFactory::CreateRecordset
- DataFactory::CreateRecordset
helpviewer_keywords:
- CreateRecordset method [RDS]
ms.assetid: 6840b1e5-c04d-4d3e-9dcc-42128c83492f
caps.latest.revision: 17
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 61f918c7a7530ae504825182a1d6a1c4ced1d84c
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "35287619"
---
# <a name="createrecordset-method-rds"></a>CreateRecordset-Methode (RDS)
Erstellt ein leeres getrennt [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md).  
  
> [!IMPORTANT]
>  Ab Windows 8 und Windows Server 2012, sind nicht mehr RDS-Server-Komponenten in Windows-Betriebssystems enthalten (finden Sie unter Windows 8 und [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/en-us/download/details.aspx?id=27416) detailliertere). RDS-Clientkomponenten werden in einer zukünftigen Version von Windows entfernt werden. Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktion zurzeit verwenden. Anwendungen, die RDS verwenden sollten migrieren [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
object.CreateRecordset(ColumnInfos)  
```  
  
#### <a name="parameters"></a>Parameter  
 *Objekt*  
 Objektvariable stellt eine [RDSServer.DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md) oder [RDS. DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) Objekt.  
  
 *ColumnsInfos*  
 Ein **Variant** Array von Attributen, die jede Spalte definiert den **Recordset** erstellt. Jede Spaltendefinition enthält ein Array von vier erforderlichen Attribute und ein optionales Attribut.  
  
|attribute|Description|  
|---------------|-----------------|  
|Name|Name des den Spaltenüberschrift.|  
|Typ|Ganze Zahl des Datentyps.|  
|Größe|Ganze Zahl, der die Breite in Zeichen, unabhängig vom Datentyp.|  
|NULL-Zulässigkeit|Boolescher Wert.|  
|Skalierung (Optional)|Dieses optionale Attribut definiert die Dezimalstellen für numerische Felder. Wenn dieser Wert nicht angegeben wird, werden numerische Werte auf drei Dezimalstellen abgeschnitten. Genauigkeit ist nicht betroffen, aber die Anzahl von Ziffern hinter dem Dezimaltrennzeichen abgeschnitten auf drei.|  
  
 Der Satz von Spaltenarrays wird dann in ein Array, das definiert gruppiert die **Recordset**.  
  
## <a name="remarks"></a>Hinweise  
 Die serverseitige Geschäftsobjekt Auffüllen der resultierende **Recordset** mit Daten aus einer nicht - OLE DB-Datenanbieter, Datei ein älteres Betriebssystem wie z. B. enthaltenden Aktienkurse.  
  
 Die folgende Tabelle enthält die [DataTypeEnum](../../../ado/reference/ado-api/datatypeenum.md) Werte, die von unterstützt die **CreateRecordset** Methode. Die Anzahl aufgeführt ist die Verweisnummer verwendet, um Felder zu definieren.  
  
 Jede der Datentypen ist fester oder variabler Länge. Typen mit fester Länge werden mit einer Größe von – 1 ist, definiert, weil die Größe bestimmt wird, und eine Definition von Größe noch erforderlich wird. Datentypen mit variabler Länge können eine Größe zwischen 1 und 32767 an.  
  
 Für einige Variablen Datentypen kann der Typ in den Typ in der Ersetzung der Spalte umgewandelt werden. Sie werden feststellen, dass die substitutionen erst nach dem **Recordset** erstellt und gefüllt ist. Anschließend können Sie für den tatsächlichen Datentyp bei Bedarf überprüfen.  
  
|Länge|Konstante|Number|Ersetzung|  
|------------|--------------|------------|------------------|  
|Fest|**adTinyInt**|16||  
|Fest|**adSmallInt**|2||  
|Fest|**adInteger**|3||  
|Fest|**adBigInt**|20||  
|Fest|**adUnsignedTinyInt**|17||  
|Fest|**adUnsignedSmallInt**|18||  
|Fest|**adUnsignedInt**|19||  
|Fest|**adUnsignedBigInt**|21||  
|Fest|**adSingle**|4||  
|Fest|**adDouble**|5||  
|Fest|**adCurrency**|6||  
|Fest|**adDecimal**|14||  
|Fest|**adNumeric**|131||  
|Fest|**adBoolean**|11||  
|Fest|**adError**|10||  
|Fest|**adGuid**|72||  
|Fest|**adDate**|7||  
|Fest|**adDBDate**|133||  
|Fest|**adDBTime**|134||  
|Fest|**adDBTimestamp**|135|7|  
|Variable|**adBSTR**|8|130|  
|Variable|**adChar**|129|200|  
|Variable|**adVarChar**|200||  
|Variable|**adLongVarChar**|201|200|  
|Variable|**adWChar**|130||  
|Variable|**adVarWChar**|202|130|  
|Variable|**adLongVarWChar**|203|130|  
|Variable|**adBinary**|128||  
|Variable|**adVarBinary**|204||  
|Variable|**adLongVarBinary**|205|204|  
  
## <a name="applies-to"></a>Gilt für  
  
|||  
|-|-|  
|[DataControl-Objekt (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)|[DataFactory-Objekt (RDSServer)](../../../ado/reference/rds-api/datafactory-object-rdsserver.md)|  
  
## <a name="see-also"></a>Siehe auch  
 [CreateRecordset-Methode (Beispiel) (VB)](../../../ado/reference/ado-api/createrecordset-method-example-vb.md)   
 [CreateRecordset-Methode (Beispiel (VBScript)](../../../ado/reference/rds-api/createrecordset-method-example-vbscript.md)   
 [CreateObject-Methode (RDS)](../../../ado/reference/rds-api/createobject-method-rds.md)



