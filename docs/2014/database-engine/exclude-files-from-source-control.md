---
title: Ausschließen von Dateien aus der Quellcodeverwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- excluding files from source control
- source controls [SQL Server Management Studio], file exclusions
ms.assetid: 7dcb6514-db5c-49eb-8b5a-2c766ce39aa7
caps.latest.revision: 21
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: b3507f06db699e8e88de2fe2e22f870b97b896e7
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37330440"
---
# <a name="exclude-files-from-source-control"></a>Ausschließen von Dateien aus der Quellcodeverwaltung
  Wenn die Projektmappe, die Sie arbeiten an Dateien, die keine Quellcodeverwaltungsdienste erfordern enthält, können Sie mithilfe der **aus Quellcodeverwaltung ausschließen** Befehl aus, um die Datei aus quellcodeverwaltung ausschließen. Dabei bleibt die Datei zwar in der [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe-Datenbank, wird aber nicht mehr mit dem Projekt ein- oder ausgecheckt.  
  
 Verwenden Sie die **aus Quellcodeverwaltung ausschließen** Befehl nur auf die generierten Dateien. Eine generierte Datei handelt, die vollständig neu erstellen können [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] basierend auf dem Inhalt einer anderen Datei in der Projektmappe.  
  
### <a name="to-exclude-a-file-from-source-control"></a>So schließen Sie eine Datei aus der Quellcodeverwaltung aus  
  
1.  Wählen Sie die auszuschließende Datei im Projektmappen-Explorer aus.  
  
2.  Auf der **Datei** , zeigen Sie auf **Quellcodeverwaltung**, und klicken Sie dann auf **ausschließen**  *\<Dateiname >* **aus Datenquellen-Steuerelement**.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen der Versionskontrolle](../../2014/database-engine/source-control-basics.md)   
 [Festlegen von Quellcodeverwaltungsoptionen](../../2014/database-engine/set-source-control-options.md)   
 [Ändern von Quellcodeverwaltungsverbindungen](../../2014/database-engine/change-source-control-connections.md)  
  
  
