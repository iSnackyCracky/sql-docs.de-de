---
title: Konfigurieren des Skripttasks im Skripttask-Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- integration-services
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], configuring
- Script Task Editor
- SSIS Script task, configuring
ms.assetid: 232de0c9-b24d-4c38-861d-6c1f4a75bdf3
caps.latest.revision: 33
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 827721e691e197faf0b786db5999b0061e42c516
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37263196"
---
# <a name="configuring-the-script-task-in-the-script-task-editor"></a>Konfigurieren des Skripttasks im Skripttask-Editor
  Bevor Sie benutzerdefinierten Code in den Skripttask schreiben, konfigurieren Sie auf den drei Seiten im **Skripttask-Editor** seine Prinzipaleigenschaften. Mithilfe des Eigenschaftsfensters können Sie zusätzliche Taskeigenschaften, die nicht nur für den Skripttask vorhanden sind, konfigurieren.  
  
> [!NOTE]  
>  Anders als in früheren Versionen, in denen Sie angeben konnten, ob die Skripts vorkompiliert sind, werden ab [!INCLUDE[ssISversion10](../../../includes/ssisversion10-md.md)] alle Skripts vorkompiliert.  
  
## <a name="general-page-of-the-script-task-editor"></a>Seite 'Allgemein' des Skripttask-Editors  
 Auf der Seite **Allgemein** im **Skripttask-Editor** können Sie dem Skripttask einen eindeutigen Namen und eine Beschreibung zuweisen.  
  
## <a name="script-page-of-the-script-task-editor"></a>Seite 'Skript' des Skripttask-Editors  
 Auf der Seite **Skript** im **Skripttask-Editor** werden die benutzerdefinierten Eigenschaften des Skripttasks angezeigt.  
  
### <a name="scriptlanguage-property"></a>ScriptLanguage-Eigenschaft  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) unterstützt die Programmiersprachen [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic oder [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#. Nach der Erstellung eines Skripts im Skripttask können Sie den Wert der **ScriptLanguage**-Eigenschaft nicht mehr ändern.  
  
 Um die Standardskriptsprache für Skripttasks und Skriptkomponenten festzulegen, verwenden Sie im Dialogfeld **Optionen** auf der Seite **Allgemein** die **ScriptLanguage**-Eigenschaft. Weitere Informationen finden Sie unter [General Page](../../general-page-of-integration-services-designers-options.md).  
  
### <a name="entrypoint-property"></a>EntryPoint-Eigenschaft  
 Die `EntryPoint`-Eigenschaft gibt die Methode für die `ScriptMain`-Klasse im VSTA-Projekt an, die die [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Laufzeit als Einstiegspunkt in den Code des Skripttasks aufruft. Die `ScriptMain`-Klasse ist die Standardklasse, die von den Skriptvorlagen generiert wird.  
  
 Wenn Sie den Namen der Methode im VSTA-Projekt ändern, müssen Sie den Wert der `EntryPoint`-Eigenschaft ändern.  
  
### <a name="readonlyvariables-and-readwritevariables-properties"></a>Eigenschaften 'ReadOnlyVariables' und 'ReadWriteVariables'  
 Sie können kommagetrennte Listen von vorhandenen Variablen als Werte dieser Eigenschaften eingeben, um die Variablen für schreibgeschützten oder Lese-/Schreibzugriff im Code des Skripttasks verfügbar zu machen. Auf Variablen beider Typen wird im Code über die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>-Eigenschaft des `Dts`-Objekts zugegriffen. Weitere Informationen finden Sie unter [Using Variables in the Script Task](../../extending-packages-scripting/task/using-variables-in-the-script-task.md).  
  
> [!NOTE]  
>  Bei Variablennamen wird nach Groß-/Kleinschreibung unterschieden.  
  
 Um die Variablen auszuwählen, klicken Sie auf die Schaltfläche mit den Auslassungspunkten (**…**) neben dem Eigenschaftenfeld. Weitere Informationen finden Sie unter [Select Variables Page](../../control-flow/select-variables-page.md) (Seite „Variablen auswählen“).  
  
### <a name="edit-script-button"></a>Schaltfläche 'Skript bearbeiten'  
 Über die Schaltfläche **Skript bearbeiten** wird die VSTA-Entwicklungsumgebung gestartet, in der Sie das benutzerdefinierte Skript schreiben. Weitere Informationen siehe [Coding and Debugging the Script Task](coding-and-debugging-the-script-task.md) (Codieren und Debuggen des Skripttasks).  
  
## <a name="expressions-page-of-the-script-task-editor"></a>Seite 'Ausdrücke' des Skripttask-Editors  
 Auf der Seite **Ausdrücke** im **Skripttask-Editor** können Sie Ausdrücke verwenden, um Werte für die Eigenschaften des oben aufgeführten Skripttasks und für viele weitere Taskeigenschaften bereitzustellen. Weitere Informationen finden Sie unter [Integration Services-Ausdrücke &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md).  
  
![Integration Services (kleines Symbol)](../../media/dts-16.gif "Integration Services (kleines Symbol)")**bleiben oben, um das Datum mit Integration Services** <br /> Für die neuesten Downloads, Artikel, Beispiele und Videos von [!INCLUDE[msCoName](../../../includes/msconame-md.md)]sowie ausgewählte Lösungen aus der Community finden Sie auf die [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite auf MSDN:<br /><br /> [Besuchen Sie die Integration Services-Seite auf MSDN](http://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Codieren und Debuggen des Skripttasks](coding-and-debugging-the-script-task.md)  
  
  
