---
title: Hinzufügen einer Anmerkung zu einer Transaktion (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- annotations [Master Data Services], for transactions
ms.assetid: f5a6b2ca-56de-4e42-9da8-fba0ac3e8d92
caps.latest.revision: 5
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 0f5de1290998e6129e94bc849278554121ed8a9e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37229320"
---
# <a name="annotate-a-transaction-master-data-services"></a>Hinzufügen einer Anmerkung zu einer Transaktion (Master Data Services)
  Versehen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eine Transaktion mit einer Anmerkung, wenn Sie unterstützende Details zur Transaktion zu historischen Zwecken bereitstellen möchten.  
  
> [!NOTE]  
>  Anmerkungen können nicht gelöscht werden.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
  
-   Um von Ihnen erstellte Transaktionen mit einer Anmerkung versehen zu können, müssen Sie über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** und mindestens über die Berechtigung **Aktualisieren** für das Modellobjekt verfügen, das Sie mit einer Anmerkung versehen möchten.  
  
-   Um Transaktionen für alle Benutzer mit einer Anmerkung zu versehen, müssen Sie über die Berechtigung für den Zugriff auf den Funktionsbereich **Versionsverwaltung** verfügen und Modelladministrator sein. Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).  
  
### <a name="to-annotate-a-transaction-in-explorer"></a>So versehen Sie im Explorer eine Transaktion mit einer Anmerkung  
  
1.  Wählen Sie auf der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Startseite aus der Liste **Modell** ein Modell aus.  
  
2.  Wählen Sie aus der Liste **Version** eine Version aus.  
  
3.  Klicken Sie auf **Explorer**.  
  
4.  Zeigen Sie in der Menüleiste auf **Entitäten** und klicken Sie auf die Entität mit dem Element mit einer Transaktion, die Sie mit einer Anmerkung versehen möchten.  
  
5.  Klicken Sie im Raster auf die Zeile des Elements.  
  
6.  Klicken Sie auf **Transaktionen anzeigen**.  
  
7.  Klicken Sie im Dialogfeld **Transaktionen anzeigen** auf die Transaktion, die Sie mit einer Anmerkung versehen möchten.  
  
8.  Geben Sie die Anmerkung im Feld am unteren Rand des Dialogfelds ein.  
  
9. Klicken Sie auf **Anmerkung hinzufügen**. Die Anmerkung wird im Bereich **Anmerkungen** angezeigt.  
  
### <a name="to-annotate-a-transaction-in-version-management-administrators-only"></a>So versehen Sie in der Versionsverwaltung eine Transaktion mit einer Anmerkung (nur Administratoren)  
  
1.  Klicken Sie auf der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Startseite auf **Versionsverwaltung**.  
  
2.  Klicken Sie in der Menüleiste auf **Transaktionen**.  
  
3.  Klicken Sie im Bereich **Transaktionen** auf die Zeile im Raster für die Transaktion, die Sie mit einer Anmerkung versehen möchten.  
  
4.  Geben Sie die Anmerkung im Bereich **Transaktionsanmerkungen** im Feld **Anmerkung** ein.  
  
5.  Klicken Sie auf **OK**.  
  
## <a name="see-also"></a>Siehe auch  
 [Anmerkungen &#40;Master Data Services&#41;](../../2014/master-data-services/annotations-master-data-services.md)   
 [Transaktionen &#40;Master Data Services&#41;](../../2014/master-data-services/transactions-master-data-services.md)  
  
  
