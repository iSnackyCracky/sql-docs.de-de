---
title: Ändern des Attributtyps (MDS-Add-In für Excel) | Microsoft-Dokumentation
ms.custom: microsoft-excel-add-in
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.suite: sql
ms.technology: master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 9d3001d9-8d0f-4e4a-8e04-4f666bf0df69
caps.latest.revision: 8
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 3ed7a1d150b785bb6cd87a33b74121d1b598e390
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38059062"
---
# <a name="change-the-attribute-type-mds-add-in-for-excel"></a>Ändern des Attributtyps (MDS-Add-in für Excel)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  Im [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]können Administratoren den Attributtyp ändern, wenn der Datentyp oder die Anzahl zulässiger Zeichen falsch ist.  
  
 Wenn Sie den Attributtyp ändern möchten, um eine eingeschränkte Liste (domänenbasiertes Attribut) zu erstellen, finden Sie weitere Informationen unter [Erstellen eines domänenbasierten Attributs &#40;MDS-Add-In für Excel&#41;](../../master-data-services/microsoft-excel-add-in/create-a-domain-based-attribute-mds-add-in-for-excel.md).  
  
> [!NOTE]  
>  Sie können den Typ oder die Länge der Spalten **Name** oder **Code** nicht aktualisieren.  
  
## <a name="prerequisites"></a>Voraussetzungen  
 So führen Sie diese Prozedur aus  
  
-   Sie müssen über die Berechtigung verfügen, auf die Funktionsbereiche **Systemverwaltung** und **Explorer** zuzugreifen.  
  
-   Sie müssen ein Modelladministrator sein. Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../../master-data-services/administrators-master-data-services.md).  
  
-   Modell, Entität und Attribut müssen vorhanden sein.  
  
### <a name="to-change-the-attribute-type"></a>So ändern Sie den Attributtyp  
  
1.  Laden Sie in Excel die Entität, die die Spalte (Attribut) enthält, die Sie ändern möchten. Weitere Informationen finden Sie unter [Export Data to Excel from Master Data Services](../../master-data-services/microsoft-excel-add-in/export-data-to-excel-from-master-data-services.md)(Exportieren von Daten nach Excel aus Master Data Services).  
  
2.  Klicken Sie in der Spalte, die Sie ändern möchten, auf eine beliebige Zelle.  
  
3.  Klicken Sie in der Gruppe **Modell erstellen** auf **Attributeigenschaften**.  
  
4.  Aktualisieren Sie im Dialogfeld **Attributeigenschaften** je nach Bedarf die Einstellungen.  
  
5.  Klicken Sie auf **OK**.  
  
## <a name="what-happens-when-you-change-the-attribute-type"></a>Was geschieht, wenn Sie den Attributtyp ändern?  
 Wenn eine Abhängigkeit von dem Attribut besteht, weil beispielsweise eine MDS-Geschäftsregel oder eine abgeleitete Hierarchie auf das Attribut verweist, können Sie den Datentyp des Attributs nicht ändern. Sie erhalten eine Fehlermeldung, dass der Typ des Attributs nicht geändert werden kann, da ein Objekt damit verknüpft ist.  
  
 Wenn während der Datentypkonvertierung für die Attributwerte ein Fehler auftritt, führt MDS Folgendes aus.  
  
-   Der Datentyp des Attributs wird geändert.  
  
-   Es wird eine Kopie des Attributs mit dem Suffix "_old" generiert, das die vorherigen Werte enthält. Dies wird als veraltetes Attribut bezeichnet.  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Attribute &#40;Master Data Services&#41;](../../master-data-services/attributes-master-data-services.md)   
 [Erstellen eines Modells &#40;MDS-Add-In für Excel&#41;](../../master-data-services/microsoft-excel-add-in/building-a-model-mds-add-in-for-excel.md)  
  
  
