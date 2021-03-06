---
title: Erweitern von Paketen mit Skripts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- integration-services
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Integration Services, scripting
- SSIS, scripting
- scripts [Integration Services], about scripting
ms.assetid: 67fe18ef-f3aa-41d4-9b9d-5defd4618c4b
caps.latest.revision: 38
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 06a199eebc0cde91c928f2099118996cf9d6bf50
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37158601"
---
# <a name="extending-packages-with-scripting"></a>Erweitern von Paketen mit Skripts
  Wenn die integrierten Komponenten in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Ihren Anforderungen nicht entsprechen, können Sie die Effektivität von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] durch Codieren eigener Erweiterungen erhöhen. Ihnen stehen zwei unterschiedliche Optionen zur Erweiterung der Pakete zur Verfügung: Sie können Code in die leistungsstarken Wrapper schreiben, die vom Skripttask und der Skriptkomponente bereitgestellt werden, oder benutzerdefinierte [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Erweiterungen durch Ableitung von den Basisklassen, die im [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Objektmodell zur Verfügung stehen, vollständig neu erstellen.  
  
 In diesem Abschnitt wird die einfachere der zwei Optionen beschrieben: das Erweitern von Paketen mit Skripts.  
  
 Mit dem Skripttask und der Skriptkomponente können Sie sowohl die Ablaufsteuerung als auch den Datenfluss eines [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Pakets mit minimaler Codierung erweitern. Für beide Objekte werden die Entwicklungsumgebung von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) und die Programmiersprachen [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic oder [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# verwendet sowie alle Funktionen der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Klassenbibliothek einschließlich benutzerdefinierter Assemblys. Mit dem Skripttask und der Skriptkomponente können Entwickler benutzerdefinierte Funktionen erstellen, ohne den kompletten Infrastrukturcode schreiben zu müssen, der normalerweise bei der Entwicklung einer benutzerdefinierten Aufgabe oder Datenflusskomponente erforderlich ist.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vergleich zwischen Skripttask und Skriptkomponente](../extending-packages-scripting/comparing-the-script-task-and-the-script-component.md)  
 Beschreibt die Gemeinsamkeiten und Unterschiede zwischen Skripttask und Skriptkomponente.  
  
 [Vergleichen von Skriptlösungen und benutzerdefinierten Objekten](comparing-scripting-solutions-and-custom-objects.md)  
 Veranschaulicht die Kriterien bei der Wahl zwischen einer Skripterstellungslösung und der Entwicklung eines benutzerdefinierten Objekts.  
  
 [Verweisen auf andere Assemblys in Skriptlösungen](referencing-other-assemblies-in-scripting-solutions.md)  
 Beschreibt die erforderlichen Schritte, um in einem Skriptprojekt auf externe Assemblys und Namespaces zu verweisen und diese zu verwenden.  
  
 [Erweitern von Paketen mithilfe des Skripttasks](../extending-packages-scripting/task/extending-the-package-with-the-script-task.md)  
 Erläutert die Erstellung benutzerdefinierter Tasks mit dem Skripttask. Ein Task wird normalerweise einmal pro Paketausführung aufgerufen oder einmal für jede Datenquelle, die ein Paket öffnet.  
  
 [Erweitern des Datenflusses mit der Skriptkomponente](data-flow-script-component/extending-the-data-flow-with-the-script-component.md)  
 Erläutert, wie mithilfe der Skriptkomponente benutzerdefinierte Datenflussquellen, Transformationen und Ziele erstellt werden. Eine Datenflusskomponente wird i. d. R. für jede verarbeitete Datenzeile einmal aufgerufen.  
  
## <a name="reference"></a>Verweis  
 [Fehler- und Meldungsreferenz von Integration Services](../integration-services-error-and-message-reference.md)  
 Listet die vordefinierten [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Fehlercodes mit ihren symbolischen Namen und Beschreibungen auf.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Erweitern von Paketen mit benutzerdefinierten Objekten](../extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
 Beschreibt, wie benutzerdefinierte Tasks, Datenflusskomponenten und andere Paketobjekte für die Verwendung in mehreren Paketen erstellt und programmiert werden.  
  
 [Programmgesteuertes Erstellen von Paketen](../building-packages-programmatically/building-packages-programmatically.md)  
 Erläutert, wie [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Pakete programmgesteuert erstellt, konfiguriert, ausgeführt, geladen, gespeichert und verwaltet werden.  
  
![Integration Services (kleines Symbol)](../media/dts-16.gif "Integration Services (kleines Symbol)")**bleiben oben, um das Datum mit Integration Services** <br /> Für die neuesten Downloads, Artikel, Beispiele und Videos von [!INCLUDE[msCoName](../../includes/msconame-md.md)]sowie ausgewählte Lösungen aus der Community finden Sie auf die [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite auf MSDN:<br /><br /> [Besuchen Sie die Integration Services-Seite auf MSDN](http://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server Integration Services](../sql-server-integration-services.md)  
  
  
