---
title: Spalten von langsam veränderlichen Dimensionen (Assistent für langsam veränderliche Dimensionen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.dts.loaddimwizard.scdsupport.f1
ms.assetid: 36de99d5-5368-48e0-b876-17e9c6862c6c
caps.latest.revision: 23
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 2c0702def668f96848736b10c8543617f13ac07e
ms.sourcegitcommit: de5e726db2f287bb32b7910831a0c4649ccf3c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2018
ms.locfileid: "35334464"
---
# <a name="slowly-changing-dimension-columns-slowly-changing-dimension-wizard"></a>Spalten von langsam veränderlichen Dimensionen (Assistent für langsam veränderliche Dimensionen)
  Im Dialogfeld **Spalten von langsam veränderlichen Dimensionen** können Sie für jede Spalte einer langsam veränderlichen Dimension einen Änderungstyp auswählen.  
  
 Weitere Informationen zu diesem Assistenten finden Sie unter [Slowly Changing Dimension Transformation](../../../integration-services/data-flow/transformations/slowly-changing-dimension-transformation.md).  
  
## <a name="options"></a>Tastatur  
 **Dimensionsspalten**  
 Wählen Sie eine Dimensionsspalte aus der Liste aus.  
  
 **Änderungstyp**  
 Wählen Sie ein **Festes Attribut**oder einen der beiden Typen von veränderlichen Attributen aus. Verwenden Sie **Festes Attribut** , wenn sich der Wert in einer Spalte nicht ändern soll; [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] behandelt Änderungen dann als Fehler. Verwenden Sie **Veränderliches Attribut** , wenn vorhandene Werte von geänderten Werten überschrieben werden sollen. Verwenden Sie **Verlaufsattribut** , wenn geänderte Werte in neuen Datensätzen gespeichert werden sollen, während die vorigen Datensätze gleichzeitig als veraltet gekennzeichnet werden.  
  
 **Entfernen**  
 Wählen Sie eine Dimensionsspalte aus, und entfernen Sie sie aus der Liste der zugeordneten Spalten, indem Sie auf **Entfernen**klicken.  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Konfiguration von Ausgaben mithilfe des Assistenten für langsam veränderliche Dimensionen](../../../integration-services/data-flow/transformations/configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
