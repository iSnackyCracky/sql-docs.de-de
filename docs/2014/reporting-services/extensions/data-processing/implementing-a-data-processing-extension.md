---
title: Implementieren von Datenverarbeitungserweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- custom data processing extensions [Reporting Services]
- data sources [Reporting Services], data processing extensions
- data processing extensions [Reporting Services]
- extensions [Reporting Services], data processing
ms.assetid: 8dc2b44e-5ad9-411d-a29f-7213e29321a9
caps.latest.revision: 34
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 7d247becb7a50aa11ba1f42574938d441a627502
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37230773"
---
# <a name="implementing-a-data-processing-extension"></a>Implementieren von Datenverarbeitungserweiterungen
  Mithilfe von Datenverarbeitungserweiterungen in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] können Sie eine Verbindung zu einer Datenquelle herstellen und Daten abrufen. Sie dienen außerdem als Verbindung zwischen einer Datenquelle und einem Dataset. [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Datenverarbeitungserweiterungen sind einer Teilmenge der [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]-Datenanbieterschnittstellen nachgebildet.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Data Processing Extensions Overview (Übersicht über Datenverarbeitungserweiterungen)](data-processing-extensions-overview.md)  
 Erläutert, wie eine benutzerdefinierte Datenverarbeitungserweiterung für [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] geschrieben wird.  
  
 [Preparing to Implement a Data Processing Extension (Vorbereiten der Implementierung von Datenverarbeitungserweiterungen)](preparing-to-implement-a-data-processing-extension.md)  
 Beschreibt die verfügbaren Schnittstellen beim Implementieren einer [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Datenverarbeitungserweiterung sowie den Fall, in dem Sie eine bestimmte Schnittstelle implementieren müssen.  
  
 [Creating a Data Processing Extension Library (Erstellen einer Bibliothek für Datenverarbeitungserweiterungen)](creating-a-data-processing-extension-library.md)  
 Beschreibt die Zuordnung eines Namespace für Ihre [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Datenverarbeitungserweiterung und die Kompilierung Ihrer Datenverarbeitungserweiterung in eine DLL-Bibliothek.  
  
 [Implementing a Connection Class for a Data Processing Extension (Implementieren einer Connection-Klasse für Datenverarbeitungserweiterungen)](implementing-a-connection-class-for-a-data-processing-extension.md)  
 Beschreibt die Attribute einer Verbindung und die Implementierungsweise einer eigenen **Connection**-Klasse für Ihre Datenverarbeitungserweiterung  
  
 [Implementing a Command Class for a Data Processing Extension (Implementieren einer Command-Klasse für Datenverarbeitungserweiterungen)](implementing-a-command-class-for-a-data-processing-extension.md)  
 Beschreibt die Attribute eines Befehls und die Implementierungsweise einer eigenen **Command**-Klasse für Ihre Datenverarbeitungserweiterung  
  
 [Implementing a DataReader Class for a Data Processing Extension (Implementieren einer DataReader-Klasse für Datenverarbeitungserweiterungen)](implementing-a-datareader-class-for-a-data-processing-extension.md)  
 Beschreibt die Attribute eines Datenlesers und die Implementierungsweise einer eigenen **DataReader**-Klasse für Ihre Datenverarbeitungserweiterung  
  
 [Using an External Dataset with Reporting Services (Verwenden eines externen Datasets mit Reporting Services)](using-an-external-dataset-with-reporting-services.md)  
 Beschreibt, wie die benutzerdefinierten **Dataset**-Objekte für die Verwendung durch den Berichtsserver zur Verfügung gestellt werden  
  
 [Bereitstellen von Datenverarbeitungserweiterungen](deploying-a-data-processing-extension.md)  
 Beschreibt, wie Sie eine Datenverarbeitungserweiterung bereitstellen  
  
 [Debugging Data Processing Extension Code (Debuggen von Code für Datenverarbeitungserweiterungen)](debugging-data-processing-extension-code.md)  
 Beschreibt, wie Sie Code in Ihren Datenverarbeitungserweiterungen debuggen  
  
 [Removing a Data Processing Extension (Entfernen einer Datenverarbeitungserweiterung)](removing-a-data-processing-extension.md)  
 Beschreibt, wie Sie eine Datenverarbeitungserweiterung von einem Berichtsserver oder Berichts-Designer entfernen  
  
 Ein Beispiel für eine vollständig implementierte Datenverarbeitungserweiterung finden Sie unter [SQL Server Reporting Services-Produktbeispiele](http://go.microsoft.com/fwlink/?LinkId=177889).  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterungen für Reporting Services](../reporting-services-extensions.md)   
 [Reporting Services Extension Library (Reporting Services-Erweiterungsbibliothek)](../reporting-services-extension-library.md)  
  
  
