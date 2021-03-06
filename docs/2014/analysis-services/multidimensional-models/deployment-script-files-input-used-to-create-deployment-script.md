---
title: Grundlegendes zu den zum Erstellen des Bereitstellungsskripts verwendeten Eingabedateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- Analysis Services Deployment Wizard, scripts
- deploying [Analysis Services], input files
- Analysis Services Deployment Wizard, input files
- scripts [Analysis Services], deployment
- Analysis Services deployments, input files
- modifying input files
ms.assetid: 20e080cd-6a0e-4591-b022-ea4cd3638e36
caps.latest.revision: 32
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 8c9666014d613792c4c12f202ea5e0b790130b6e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37189037"
---
# <a name="understanding-the-input-files-used-to-create-the-deployment-script"></a>Grundlegendes zu den zum Erstellen des Bereitstellungsskripts verwendeten Eingabedateien
  Wenn Sie ein [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt erstellen, generiert [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] XML-Dateien für das Projekt. [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] legt diese XML-Dateien im Ausgabeordner des der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Projekt. Standardmäßig erfolgt die Ausgabe in den Ordner \Bin. In der folgenden Tabelle werden die von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] erstellten Dateien aufgeführt.  
  
|XMLA-Datei|Description|  
|---------------|-----------------|  
|\<*Projektname*> .asdatabase|Enthält die deklarativen Definitionen für alle [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Objekte im Projekt.|  
|\<*Projektname*> .deploymenttargets|Enthält den Namen der Instanz und der Datenbank von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , in der die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Objekte erstellt werden.|  
|\<*Projektname*> .configsettings gespeichert sind|Enthält umgebungsspezifische Einstellungen wie Verbindungsinformationen für die Datenquelle und Speicherorte für die Objektspeicherung. Einstellungen in dieser Datei überschreiben die Einstellungen in der \< *Projektname*> .asdatabase-Datei.|  
|\<*Projektname*> .deploymentoptions|Enthält Bereitstellungsoptionen, z. B. ob es sich um eine Transaktionsbereitstellung handelt und ob die bereitgestellten Objekte nach der Bereitstellung verarbeitet werden sollen.|  
  
> [!NOTE]  
>  In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] werden Kennwörter nie in den Projektdateien gespeichert.  
  
## <a name="modifying-the-input-files"></a>Ändern der Eingabedateien  
 Durch Ändern der Werte in den Eingabedateien bzw. der aus den Eingabedateien abgerufenen Werte kann so ändern Sie das Bereitstellungsziel, Konfigurationseinstellungen und Bereitstellungsoptionen, ohne die gesamte Bearbeitung \< *Projekt Namen*> .asdatabase-Datei (oder eine gesamte XMLA-Skriptdatei, wenn Sie ein Skript aus einem vorhandenen generieren [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank). Durch die Möglichkeit, einzelne Dateien zu ändern, können Sie auf einfache Weise verschiedene Bereitstellungsskripts für unterschiedliche Zwecke erstellen.  
  
 In den folgenden Themen wird erläutert, wie Sie Werte in den verschiedenen Eingabedateien ändern:  
  
-   [Angeben des Installationszieles](deployment-script-files-specifying-the-installation-target.md)  
  
-   [Angeben von Bereitstellungsoptionen für Partitionen und Rollen](deployment-script-files-partition-and-role-deployment-options.md)  
  
-   [Angeben der Konfigurationseinstellungen für die Lösungsbereitstellung](deployment-script-files-solution-deployment-config-settings.md)  
  
-   [Angeben von Verarbeitungsoptionen](deployment-script-files-specifying-processing-options.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Ausführen des Bereitstellungs-Assistenten für Analysis Services](running-the-analysis-services-deployment-wizard.md)   
 [Grundlegendes zum Analysis Services-Bereitstellungsskript](understanding-the-analysis-services-deployment-script.md)  
  
  
