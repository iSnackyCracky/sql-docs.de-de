---
title: Erweitern von OLAP-Funktionalität | Microsoft Docs
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: olap
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 06b73c0b9f8b4c2d93bb81762ebec442f94e7198
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
ms.locfileid: "34021417"
---
# <a name="extending-olap-functionality"></a>Erweiterte von OLAP-Funktionalität
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Als Programmierer können Sie Analysis Services erweitern, indem Sie Assemblys, personalisierte Erweiterungen und gespeicherten Prozeduren schreiben, die die Funktionalität bereitstellen, die Sie in mehreren Datenbankanwendungen verwenden oder wiederverwenden möchten. Assemblys werden verwendet, um durch Hinzufügen von neuen Prozeduren und Funktionen zur MDX-Sprache oder mittels des Personalisierungs-Add-Ins die mehrdimensionale Modelle-Funktionalität zu erweitern.  
  
 Gespeicherte Prozeduren können verwendet werden, um externe Routinen aufzurufen, und vereinfachen so die Entwicklung und Implementierung von Analysis Services-Datenbanken, da gemeinsamer Code nur einmal entwickelt werden muss und an einem einzelnen Ort gespeichert werden kann. Mit gespeicherten Prozeduren kann Anwendungen Geschäftsfunktionalität hinzugefügt werden, die von der systemeigenen Funktionalität von MDX nicht bereitgestellt wird.  
  
 Personalisierungen sind benutzerdefinierte Objekte, die Sie einem Cube hinzufügen, um ein Verhalten bereitzustellen, das sich je nach Benutzer ändert. Personalisierungen sind keine permanenten Objekte im Cube, sondern Objekte, die von der Clientanwendung während der Sitzung des Benutzers dynamisch angewendet werden. Beispiele umfassen das Ändern der Währung von einem Währungswert abhängig von der Person, die auf die Daten zugreift, Bereitstellen von individualisierten KPIs oder eine gezielte Vorschlagsliste für Stammkunden, die online kaufen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erweitern von OLAP durch personalisierungen](../../../analysis-services/multidimensional-models/extending-olap/extending-olap-through-personalizations.md)  
  
 [Personalisierungserweiterungen für Analysis Services](../../../analysis-services/multidimensional-models/extending-olap/analysis-services-personalization-extensions.md)  
  
 [Definieren von gespeicherten Prozeduren](../../../analysis-services/multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
