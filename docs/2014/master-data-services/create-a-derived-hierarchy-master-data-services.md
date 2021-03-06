---
title: Erstellen einer abgeleiteten Hierarchie (Master Data Services) | Microsoft-Dokumentation
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
- derived hierarchies, creating
- creating derived hierarchies [Master Data Services]
ms.assetid: fec653c4-11cc-46a2-8dd8-b605341ebb40
caps.latest.revision: 5
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 696b4bc98f4feb47ae7db6cae99d1ba9ae8a6628
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37217640"
---
# <a name="create-a-derived-hierarchy-master-data-services"></a>Erstellen einer abgeleiteten Hierarchie (Master Data Services)
  Erstellen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eine abgeleitete Hierarchie, wenn Sie eine ebenenbasierte Hierarchie möchten, die sicherstellt, dass sich die Elemente auf der richtigen Ebene befinden. Abgeleitete Hierarchien basieren auf den domänenbasierten Attributbeziehungen, die in einem Modell vorhanden sind.  
  
> [!NOTE]  
>  Wenn ein domänenbasierter Attributwert für ein Element nicht vorhanden ist, ist das Element nicht in der abgeleiteten Hierarchie enthalten. Gehen Sie auf die Seite [Erfordern von Attributwerten &#40;Master Data Services&#41;](require-attribute-values-master-data-services.md), um einen domänenbasierten Attributwert für alle Mitglieder anzufordern.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 So führen Sie diese Prozedur aus  
  
-   Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Systemverwaltung** zuzugreifen.  
  
-   Sie müssen ein Modelladministrator sein. Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).  
  
### <a name="to-create-a-derived-hierarchy"></a>So erstellen Sie eine abgeleitete Hierarchie  
  
1.  Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.  
  
2.  Auf der **Modellansicht** Seite zeigen Sie auf der Menüleiste **verwalten** , und klicken Sie auf **abgeleitete Hierarchien**.  
  
3.  Wählen Sie auf der Seite **Verwaltung abgeleiteter Hierarchien** aus der Liste **Modell** ein Modell aus.  
  
4.  Klicken Sie auf **abgeleitete Hierarchie hinzufügen**.  
  
5.  Geben Sie auf der Seite **Abgeleitete Hierarchie hinzufügen** im Feld **Name der abgeleiteten Hierarchie** einen Namen für die Hierarchie ein.  
  
    > [!TIP]  
    >  Verwenden Sie einen Namen, der die Ebenen in der Hierarchie beschreibt, z.B. **Produkt-zu-Unterkategorie-zu-Kategorie**.  
  
6.  Klicken Sie auf **Abgeleitete Hierarchie speichern**.  
  
7.  Auf der **abgeleitete Hierarchie bearbeiten** auf der Seite die **verfügbare Entitäten und Hierarchien** Bereich, klicken Sie auf eine Entität oder eine Hierarchie, und ziehen Sie dann auf die **aktuelle Ebenen** Bereich.  
  
8.  Ziehen Sie Entitäten oder Hierarchien in diesen Bereich, bis die Hierarchie vollständig ist.  
  
9. Klicken Sie auf **Zurück**.  
  
## <a name="see-also"></a>Siehe auch  
 [Abgeleitete Hierarchien &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md)   
 [Abgeleitete Hierarchien mit expliziten Abschlüssen &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md)   
 [Domänenbasierte Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md)  
  
  
