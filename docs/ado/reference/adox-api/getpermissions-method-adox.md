---
title: GetPermissions-Methode (ADOX) | Microsoft Docs
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
- _User25::GetPermissions
- _Group25::raw_GetPermissions
- _Group25::GetPermissions
- _User25::raw_GetPermissions
helpviewer_keywords:
- GetPermissions method [ADOX]
ms.assetid: df201c1f-c76a-465d-98f0-83b7fc36e6e3
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 55a5d4f9096d5a75855d4b612a202afd034b11da
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "35286039"
---
# <a name="getpermissions-method-adox"></a>GetPermissions-Methode (ADOX)
Gibt die Berechtigungen für eine [Gruppe](../../../ado/reference/adox-api/group-object-adox.md) oder [Benutzer](../../../ado/reference/adox-api/user-object-adox.md) auf ein Objekt oder ein Objektcontainer.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
ReturnValue=GroupOrUser.GetPermissions(Name, ObjectType    [,ObjectTypeId])  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt eine **lange** Wert, der angibt, eine Bitmaske, die mit den Berechtigungen, die Gruppe bzw. des Benutzers für das Objekt besitzt. Mögliche Werte sind mindestens die [RightsEnum](../../../ado/reference/adox-api/rightsenum.md) Konstanten.  
  
#### <a name="parameters"></a>Parameter  
 *Name*  
 Ein **Variant** Wert, der den Namen des Objekts, für das zum Festlegen von Berechtigungen angibt. Legen Sie *Namen* auf einen null-Wert, wenn die Berechtigungen für den Container des Objekts abgerufen werden soll.  
  
 *ObjectType*  
 Ein **lange** Wert sein kann von der [ObjectTypeEnum](../../../ado/reference/adox-api/objecttypeenum.md) Konstanten, die angibt, den Typ des Objekts, für das Berechtigungen zu erhalten.  
  
 *ObjectTypeId*  
 Optional. Ein **Variant** Wert, der angibt, die GUID für einen Anbietertyp für das Objekt nicht vom OLE DB-Spezifikation definiert. Dieser Parameter ist erforderlich, wenn *ObjectType* festgelegt ist, um **AdPermObjProviderSpecific**ist, andernfalls ist er nicht verwendet.  
  
## <a name="applies-to"></a>Gilt für  
  
|||  
|-|-|  
|[Group-Objekt (ADOX)](../../../ado/reference/adox-api/group-object-adox.md)|[User-Objekt (ADOX)](../../../ado/reference/adox-api/user-object-adox.md)|  
  
## <a name="see-also"></a>Siehe auch  
 [GetPermissions und SetPermissions-Methoden (Beispiel) (VB)](../../../ado/reference/adox-api/getpermissions-and-setpermissions-methods-example-vb.md)   
 [Name-Eigenschaft (ADOX)](../../../ado/reference/adox-api/name-property-adox.md)   
 [SetPermissions-Methode (ADOX)](../../../ado/reference/adox-api/setpermissions-method-adox.md)
