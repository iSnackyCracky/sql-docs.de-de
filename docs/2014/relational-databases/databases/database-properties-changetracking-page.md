---
title: Datenbankeigenschaften (Seite Änderungsnachverfolgung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.changetracking.f1
ms.assetid: 9b929640-bc62-449b-9b06-b5a77b8cf372
caps.latest.revision: 12
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: ff372309d1f9f5c7eda982b4c431c24556c6f073
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37225580"
---
# <a name="database-properties-changetracking-page"></a>Datenbankeigenschaften (Seite Änderungsnachverfolgung)
  Mithilfe dieser Seite können Sie die Einstellungen der Änderungsnachverfolgung für die ausgewählte Datenbank anzeigen und ändern. Informationen zu den auf dieser Seite verfügbaren Optionen finden Sie unter [Aktivieren und Deaktivieren der Änderungsnachverfolgung &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md).  
  
## <a name="options"></a>Tastatur  
 **Änderungsnachverfolgung**  
 Mithilfe dieser Option können Sie die Änderungsnachverfolgung für die Datenbank aktivieren und deaktivieren.  
  
 Um die Änderungsnachverfolgung aktivieren zu können, müssen Sie über die Berechtigung zur Änderung der Datenbank verfügen.  
  
 Durch Festlegen des Werts auf **True** wird eine Datenbankoption festgelegt, die eine Aktivierung der Änderungsnachverfolgung für einzelne Tabellen ermöglicht.  
  
 Sie können die Änderungsnachverfolgung mithilfe von [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql)konfigurieren.  
  
 **Beibehaltungsdauer**  
 Gibt die Mindestdauer für die Beibehaltung von Änderungsnachverfolgungsinformationen in der Datenbank an. Die Daten werden nur dann entfernt, wenn der Wert für **Automatisches Cleanup**auf **True**festgelegt ist.  
  
 Der Standardwert ist 2.  
  
 **Einheiten für die Beibehaltungsdauer**  
 Gibt die Einheiten für den Beibehaltungsdauerwert an. Sie können **Tage**, **Stunden**oder **Minuten**auswählen. Der Standardwert ist **Tage**.  
  
 Die Mindestbeibehaltungsdauer ist 1 Minute. Es gibt keine maximale Beibehaltungsdauer.  
  
 **Automatisches Cleanup**  
 Gibt an, ob Änderungsnachverfolgungsinformationen nach der angegebenen Beibehaltungsdauer automatisch entfernt werden.  
  
 Durch Aktivieren von **Automatisches Cleanup** wird eine vorhandene benutzerdefinierte Beibehaltungsdauer auf die Standardbeibehaltungsdauer von 2 Tagen zurückgesetzt.  
  
## <a name="see-also"></a>Siehe auch  
 [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql)   
 [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
