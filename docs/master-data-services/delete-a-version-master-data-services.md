---
title: Löschen einer Version (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.suite: sql
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- versions [Master Data Services], deleting
- deleting versions [Master Data Services]
ms.assetid: 2a4eeffe-8379-4744-ad44-c27d8c8ac9a8
caps.latest.revision: 6
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: d5eccdabdeb0fb0bd84953d6d0c50d50a53da799
ms.sourcegitcommit: cc46afa12e890edbc1733febeec87438d6051bf9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2018
ms.locfileid: "35401752"
---
# <a name="delete-a-version-master-data-services"></a>Löschen einer Version (Master Data Services)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  Löschen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eine Version, wenn Sie sicher sind, dass Sie die der Version zugeordneten Masterdaten nicht mehr benötigen. Nachdem Sie eine Version gelöscht haben, können Sie die zugeordneten Masterdaten nicht abrufen.  
  
> [!WARNING]  
>  Wenn ein Modell nur über eine Version verfügt, und Sie diese löschen, wird das Modell unbrauchbar.  
  
## <a name="prerequisites"></a>Voraussetzungen  
 So führen Sie diese Prozedur aus  
  
-   Sie müssen berechtigt sein, die mdm.viw_SYSTEM_SCHEMA_VERSION-Sicht anzuzeigen und die gespeicherte Prozedur mds.udpVersionDelete in der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]-Datenbank auszuführen. Weitere Informationen finden Sie unter [Sicherheit von Datenbankobjekten &#40;Master Data Services&#41;](../master-data-services/database-object-security-master-data-services.md).  
  
### <a name="to-delete-a-version"></a>So löschen Sie eine Version  
  
1.  Öffnen Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , und stellen Sie eine Verbindung mit der [!INCLUDE[ssDE](../includes/ssde-md.md)] -Instanz für die [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank her.  
  
2.  Öffnen Sie die mdm.viw_SYSTEM_SCHEMA_VERSION-Sicht.  
  
3.  Suchen Sie die Version des Modells, die Sie löschen möchten, und kopieren Sie den Wert im Feld **ID** .  
  
4.  Erstellen Sie eine neue Abfrage.  
  
5.  Geben Sie den folgenden Text ein, indem Sie *version_ID* durch den in Schritt 2 kopierten Wert ersetzen.  
  
    ```  
    EXEC [mdm].[udpVersionDelete] @Version_ID='version_ID'  
    ```  
  
6.  Führen Sie die Abfrage aus.  
  
    > [!NOTE]  
    >  Es kann einige Minuten dauern, bis die Änderung in der Webanwendung angezeigt wird.  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Versionen &#40;Master Data Services&#41;](../master-data-services/versions-master-data-services.md)   
 [Kopieren einer Version &#40;Master Data Services&#41;](../master-data-services/copy-a-version-master-data-services.md)  
  
  
