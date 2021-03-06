---
title: Erstellen einer Ablaufverfolgungsvorlage (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.suite: sql
ms.technology: profiler
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
- saving trace template
ms.assetid: 025868b0-3790-4cda-8757-5a58327bfba0
caps.latest.revision: 24
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 80d968795e5201813f9f53f558b87f7ca2e3804b
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MTE75
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38063998"
---
# <a name="create-a-trace-template-sql-server-profiler"></a>Erstellen einer Ablaufverfolgungsvorlage (SQL Server Profiler)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  In diesem Thema wird beschrieben, wie Sie mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]eine neue Ablaufverfolgungsvorlage erstellen.  
  
### <a name="to-create-a-trace-template"></a>So erstellen Sie eine Ablaufverfolgungsvorlage  
  
1.  Zeigen Sie im Menü **Datei** auf **Vorlagen**, und klicken Sie dann auf **Neue Vorlage**.  
  
2.  Wählen Sie in der Liste **Servertyp auswählen** des Dialogfelds **Eigenschaften der Ablaufverfolgungsvorlage**einen Servertyp aus.  
  
3.  Geben Sie im Feld **Name der neuen Vorlage** den Vorlagennamen ein.  
  
4.  Wahlweise können Sie auch auf **Neue Vorlage auf vorhandener basieren**klicken und anschließend eine Vorlage aus der Liste auswählen.  
  
     Alle Ereignisse, Datenspalten und Filter werden anfänglich so festgelegt, wie in der ausgewählten Vorlage angegeben.  
  
5.  Wahlweise können Sie auch auf **Als Standardvorlage für den ausgewählten Servertyp verwenden**klicken.  
  
6.  Auf der Registerkarte **Ereignisauswahl** können Sie Ereignisse, Datenspalten und Filter hinzufügen, entfernen oder ändern.  
  
7.  Zeigen Sie im Menü **Ereignisauswahl**können Sie mit dem Rastersteuerelement Ereignisse und Datenspalten in der Ablaufverfolgungsdatei wie folgt hinzufügen oder entfernen.  
  
    -   Um ein Ereignis hinzuzufügen, erweitern Sie die entsprechende Ereigniskategorie in der **Ereignisse** -Spalte und wählen dann den Ereignisnamen aus.  
  
    -   Wenn Sie ein Ereignis hinzufügen, werden standardmäßig alle relevanten Datenspalten eingeschlossen. Um eine Datenspalte für ein Ereignis aus einer Ablaufverfolgung zu entfernen, deaktivieren Sie das Kontrollkästchen in der Datenspalte für das Ereignis.  
  
    -   Um Filter hinzuzufügen, klicken Sie auf den Namen der Datenspalte, und geben Sie die Filterkriterien im Dialogfeld **Filter bearbeiten** an. Sie können auch mit der rechten Maustaste auf den Namen der Datenspalte und anschließend auf **Spaltenfilter bearbeiten** klicken, um das Dialogfeld **Filter bearbeiten** zu öffnen. Klicken Sie auf **OK** , um den Filter hinzuzufügen.  
  
8.  Klicken Sie auf **Speichern.**  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Angeben von Ereignissen und Datenspalten für eine Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)   
 [Ableiten einer Vorlage von einer zurzeit ausgeführten Ablaufverfolgung &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md)   
 [Ableiten einer Vorlage von einer Ablaufverfolgungsdatei oder Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md)   
 [Vorlagen und Berechtigungen in SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md)   
 [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
